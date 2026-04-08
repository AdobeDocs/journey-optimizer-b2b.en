---
title: External Nodes
description: Learn how to use External Action and External Split Path nodes in account journeys to connect with external services and route accounts and people based on the service response.
feature: Account Journeys, Integrations
role: User
---
# External nodes

Use external nodes to connect your account journey with an external service. When an account audience reaches one of these nodes, Journey Optimizer B2B Edition asynchronously sends audience attribute data to the external service. The service processes the data and responds using a callback, returning audience information and metadata that the journey uses to continue.

>[!NOTE]
>
>External action nodes are available only in account journeys. They are not supported in person journeys.
>
>An administrator must [configure and activate the external action](../admin/configure-external-actions.md) before marketers add and implement these nodes in a journey.

There are two external action node types:

* **[External action](#external-action)** – Calls an external service and continues along a single outgoing path. Use this node when you want to trigger an external process without branching logic, such as updating a record in an external system or sending a signal to a downstream service.
* **[External split paths](#external-split-paths)** – Calls an external service and evaluates the response to route accounts along one of several defined paths. Use this node when the external service returns a value, such as a score, tier, or classification, that determines the next step in the journey.

## External action node {#external-action}

The _External action_ node calls an external service and continues along a single outgoing path, regardless of the response content. Use it for integrations where no branching is needed after the external call.

1. Navigate to the account journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL External action]**.

   ![Add an External action node](./assets/node-external-action.png){width="400"}

1. In the node properties on the right, set the **[!UICONTROL Action on]** context for the external action:

   * Choose **[!UICONTROL Accounts]** when you want to apply the external action to all people that are part of accounts on the node path.
   * Choose **[!UICONTROL People]** when you want to apply a change to all people on the node path.

1. Select the external **[!UICONTROL Service name]**.

   ![External action node - select external service](./assets/node-external-action-service-name.png){width="600" zoomable="yes"}

   The list includes all configured external actions that are active and designated for the _External action_ type and the context.

1. If the service has global attributes, enter the required values in the fields that are displayed below the service name.

1. Continue building the journey from the outgoing paths of the node.

   The _[!UICONTROL Timeout or error]_ path is automatically created. If the timeout period (as configured in the service) elapses before a response is received, the account or person progresses down this path. It is the same if an error response is received. You can add journey nodes to this path to handle these scenarios, or the journey ends for the audience member.

## External split paths node {#external-split-paths}

The External split paths node calls an external service and uses the response to determine which path accounts take next. Each path is defined by a condition based on a variable (accessor) returned by the external service. The journey evaluates the response against the defined path conditions and routes each account along the first matching path. Path conditions are evaluated in top-down order. Each account proceeds along the first path whose condition matches the value returned by the external service.

1. Navigate to the account journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL External split paths]**.

   ![Add an External split path node](./assets/node-external-split-path.png){width="400"}

1. In the node properties on the right, choose a **[!UICONTROL Split paths by]** type:

   * **[!UICONTROL Accounts]** - For split paths by accounts, you can add both account and people nodes within the defined paths. 
   * **[!UICONTROL People]** - For split paths by people, you can add only people action nodes within the defined paths. A people-based split is automatically closed with a _[!UICONTROL Merge paths]_ node so that all people can move forward to the next step without losing their account context.

1. Select the **[!UICONTROL Service name]**.

1. If the service configuration has _global attributes_, enter the required values in the fields that appear below the service name.

1. For _[!UICONTROL Path 1]_, define the branching condition:

   * For **[!UICONTROL Label]**, replace the default value with a more descriptive label. 
   * For **[!UICONTROL Select variable]**, choose an accessor. Accessors are values returned by the external service and are defined when the action is configured.
   * For **[!UICONTROL Select operator]**, choose the operator.
   * For **[!UICONTROL Enter values]**, enter the value to match against.

   ![External split path node - set path condition using a service variable](./assets/node-external-split-path-properties.png){width="600" zoomable="yes"}

   >[!NOTE]
   >
   >The available condition variables and supported journey context (_Account_, _People_, or _People in Account_) are determined by the external action configuration. Contact your administrator if the expected service or variables are not available.

1. To add more paths, click **[!UICONTROL Add path]** and define a condition for each one that you need.

1. Continue building the journey from each outgoing path of the node.

   The _[!UICONTROL Timeout or error]_ path is automatically created. If the timeout period (as configured in the service) elapses before a response is received, the account or person progresses down this path. It is the same if an error response is received. You can add journey nodes to this path to handle these scenarios, or the journey ends for the audience member.

1. For _Split by accounts_, you can add a [Merge paths node](./split-merge-paths-nodes.md#merge-paths) to combine two or more paths as needed.
