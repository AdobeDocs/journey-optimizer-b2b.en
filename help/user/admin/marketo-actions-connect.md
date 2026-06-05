---
title: Activate Marketo Engage to Support Journey Actions
description: Activate Marketo Engage connections to support journey actions so that marketers can coordinate campaigns between Marketo Engage and Journey Optimizer B2B Edition.
feature: Setup, Integrations
role: Admin
exl-id: e324a11b-1025-4850-865f-ef8886a6b2bb
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
    internal-label: Administration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
autotag-review: 2026-03-27T22:48:47.183Z
TQID: https://experienceleague.adobe.com/nM-Jxcj7wekzRks2xCqshOdlY7W8K0WKCXtWCNSb388
---
# Activate Marketo Engage connections to support actions

Marketo Engage actions are _people-based_ actions that allow you to coordinate your _account-based_ marketing orchestration between Journey Optimizer B2B Edition and your _lead-based_ marketing efforts in Marketo Engage. Use these actions to orchestrate static list membership and to place people into campaigns.

To use Marketo Engage journey actions, an administrator first creates a [custom service](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services){target="_blank"} in Marketo Engage, which provides the credentials needed for authentication. Then, a product administrator for Journey Optimizer B2B Edition uses the credentials to create a connection to Marketo Engage. Journey Optimizer B2B Edition users can then reference the connection to configure Marketo Engage actions in person and account journeys:

* [!UICONTROL Add to Marketo List]
* [!UICONTROL Remove from Marketo List]
* [!UICONTROL Add to Marketo Request Campaign]

## Configure a Marketo Engage connection {#external-marketo-configure}

>[!CONTEXTUALHELP]
>id="ajo-b2b_marketo-configure-connections"
>title="External Marketo Engage connections"
>abstract="Product administrators can configure connections to external Marketo Engage instances, which makes them available for journey actions."

To configure an external Marketo Engage instance for use with journey actions, complete the following tasks.

### Create the Marketo Engage custom service

1. Log in to Marketo Engage as an administrator and [create a custom service](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/create-a-custom-service-for-use-with-rest-api){target="_blank"}.
1. Copy the following values to use for the Journey Optimizer B2B Edition connection:

   * Munchkin ID
   * Client ID
   * Client Secret

The [role permissions assigned in the custom service](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#permission-list){target="_blank"} govern Marketo Engage workspace visibility for assets, such as lists and campaigns. Marketers can use the same connection multiple times within a journey and use different Marketo Engage connections within the same journey.

### Add the integration

![Add integration details](assets/integration-connection-details.png){width="800" zoomable="yes"}

1. In Journey Optimizer B2B Edition, navigate to **[!UICONTROL Administration]** > **[!UICONTROL Configurations]**.
1. Select the **[!UICONTROL Integrations]** tab.
1. Click **[!UICONTROL Create a connection]**.
1. Enter a **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional).
1. Select the update policy that is used for applying an action to a matching person record.

   When an action runs for the connected Marketo Engage instance, the selected _update policy_ determines the person records in Marketo Engage to select if multiple identifiers exist in the unified person profile. 
   
   * **[!UICONTROL Update all matching records]**
   * **[!UICONTROL Update only the oldest matching record]**
   * **[!UICONTROL Update only the newest matching record]**
   
   >[!NOTE]
   >
   >A person/lead proceeds through the journey regardless of a match, except when an error occurs. A journey action does not create a new person record in Marketo Engage when a matching record does not exist.

1. Enter the Munchkin ID, Client ID, and Client Secret for the service created in the external Marketo Engage instance.
1. Click **[!UICONTROL Connect to Marketo]**.
1. Click **[!UICONTROL Create]**.

## Use the connection in a journey action

When a marketer uses a Marketo Engage action in a journey, they can configure the node using the connection name.

>[!NOTE]
>
>Marketo Engage actions executed from a journey do not apply to the REST API limits for the connected Marketo Engage instance.

With the completed integration, Marketo Engage actions are available from **_Actions on:_** in the node properties.

![Marketo actions list](assets/marketo-actions-list.png){width="800" zoomable="yes"}
