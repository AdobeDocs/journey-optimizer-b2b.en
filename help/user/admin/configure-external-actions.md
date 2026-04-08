---
title: External Actions Configuration
description: Learn how developers, administrators, and marketers work together to implement, configure, and use external actions that connect Journey Optimizer B2B Edition with external services in account journeys.
feature: Setup, Integrations
role: Admin, Developer
exl-id: 226fbf23-7df2-4fd7-b5a4-2057a417a261
---
# External actions configuration

External actions allow account journeys in Journey Optimizer B2B Edition to connect with external systems directly from the journey canvas. When an account audience reaches an external action node, the system makes an asynchronous outbound call to a configured external service, passing audience attribute data for accounts, people, or both. The external service processes the data and responds using a callback, returning audience data and metadata that can be used to guide journey execution.

This feature supports two journey node types:

* **External action** – Calls an external service and continues along a single outgoing path. Ideal for _fire-and-forget_ integrations, such as updating a CRM record or triggering a downstream notification.
* **External split paths** – Calls an external service and evaluates the response to route accounts along one of several defined paths.

>[!NOTE]
>
>External action services are supported only for account journeys. These node types are not available for person journeys.

## Implementation overview

Setting up external actions requires coordination across three roles in sequence:

| | Role | Task |
| ---- | ---- | ---- |
| 1 | Developer | [Implement and publish the external service](#implement-service) |
| 2 | Administrator | [Configure the action in Journey Optimizer B2B Edition](#configure-action) |
| 3 | Marketer | [Add an external node to an account journey](#add-journey-node) |

## Implement the external service {#implement-service}

The developer must create and publish a public-facing web service that complies with the [Adobe Journey Optimizer B2B Edition External Actions Service Provider Interface](https://developer.adobe.com/journey-optimizer-b2b-apis/).

>[!NOTE]
>
>The callback function requires a bearer token. Retrieve this by setting up [OAuth Server-to-Server credentials in Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation) for your IMS Organization.

After the service is live, provide the URL to the OpenAPI specification and the authentication credentials to the product administrator who is responsible for configuring the action.

## Configure the action {#configure-action}

An action must be configured and activated before marketers can use it in a journey. Actions are created in _Draft_ state and your changes are saved automatically. It remains as a draft until you activate it.

>[!PREREQUISITES]
>
>Obtain the URL to the OpenAPI specification and the authentication credentials from the developer before you add the configuration.
>
>To define and activate an external action, you must have the _[!UICONTROL Manage B2B Admin Configurations]_ [product permission](./user-management.md#b2b-product-permissions).

1. Go to **[!UICONTROL Administration]** > **[!UICONTROL Configurations]**. 

1. Click **[!UICONTROL External Actions]** on the intermediate panel.

   ![Access the External Actions configuration space](./assets/configuration-external-actions-list.png){width="800" zoomable="yes"}

1. Click **[!UICONTROL Create action]** at the top right.

1. Enter the URL to the OpenAPI specification for your external service and click **[!UICONTROL Create]**.

   ![Enter the service URL](./assets/configuration-external-actions-create-url.png){width="500"}

   >[!NOTE]
   >
   >Your external service must be live and reachable for this step to succeed.

1. When the URL resolves successfully, review the **[!UICONTROL Service details]**.

   The service details are read directly from the OpenAPI specification when the action is created. You cannot change these properties in the configuration after creation.

   | Property | Description | OpenAPI spec property |
   | -------- | ----------- | --------------------- |
   | [!UICONTROL Name] | Name for the action | `info.title` |
   | [!UICONTROL Description] | Description for the action | `info.description` |
   | [!UICONTROL URL] | URL to the OpenAPI specification that defines the external service | `servers.url` |

1. Enter the **[!UICONTROL Authentication]** credentials for the external service (`components.securitySchemes`).

   >[!NOTE]
   >
   >The displayed credential fields depend on the authentication mechanism defined in the external service. Supported types are API Key, OAuth2, and HTTP Basic Authentication.

   ![Add the authentication credentials](./assets/configuration-external-actions-auth-credentials.png){width="600" zoomable="yes"}

   You can change the credentials as needed when the configured action is in the _Draft_ or _Active_ status.

1. Click **[!UICONTROL Next]**.

1. Set the **[!UICONTROL Configurations]** properties to define how the action exchanges data with the external service. 

   >[!NOTE]
   >
   >Properties marked as _Static_ are not updatable at configuration time and are based on the service definition.

   * **[!UICONTROL Action type]** (_Static_) – The supported journey node type:
   
      * [!UICONTROL External action] (`enableSplitPath` = false)
      * [!UICONTROL External action split path] (`enableSplitPath` = true)

      You cannot change the action type after creating the action configuration.

   * **[!UICONTROL Accessors]**  (_Static_) – (External action split path only) The variables that are returned by the external service to be available as path conditions in an External split path node. (`invocationPayloadDef.accessorsMetadata`)

   * **[!UICONTROL Journey context]**  (_Static_) – The scope of audience data sent in the request (`supportedEntityType`):

      * [!UICONTROL Account] – Sends only accounts

      * [!UICONTROL People] – Sends only people

      * [!UICONTROL People in Account] – Sends accounts and account-related people

   * **[!UICONTROL Outgoing Fields]** – Map each field in the table to an [XDM field](../admin/xdm-field-management.md). These fields are sent in the request body to the external service. Service definition properties: `invocationPayloadDef.accountFields`, `invocationPayloadDef.fields`.

   ![Map external action outgoing fields](./assets/configuration-external-actions-fields.png){width="600" zoomable="yes"}

   * **[!UICONTROL Incoming Fields]** – Map each field in the table to an [updatable XDM field](../admin/xdm-field-management.md#updatable-fields). These fields are populated from the external service response. Service definition properties: `callbackPayloadDef.accountFields`, `callbackPayloadDef.fields`. Updatable after creation.

   * **[!UICONTROL Header parameters]** – Enter a value for each row to pass as an HTTP header in the request. Service definition property: `invocationPayloadDef.headers`.

   * **[!UICONTROL Timeout]** – Enter the number of minutes to wait for the external service to invoke the callback before the request is considered failed. Service definition property: `timeout`.

   * **[!UICONTROL Global attributes]** – Enter a value for each row to include as a static field in the request body. Service definition property: `invocationPayloadDef.globalAttributes`.

   ![External action header parameters, timeout, and global attributes](./assets/configuration-external-actions-header-timeout-global.png){width="600" zoomable="yes"}

1. Click the _Back arrow_ to return to the list and keep the action in a _Draft_ state. 

   Or, click **[!UICONTROL Activate]** to change the action configuration to the _Active_ state. The configured external action must be active to make it available for use in account journeys.

## Add an external node to a journey {#add-journey-node}

After an action is activated, marketers can add an _[!UICONTROL External action]_ or _[!UICONTROL External split path]_ node to any account journey. For information about how to add and use these nodes in the account journey canvas, see [External nodes](../journeys/external-nodes.md).
