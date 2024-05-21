---
title: Account Journey nodes
description: Learn about the node types that you can use to construct your account journeys.
exl-id: 4edb87d9-cdf8-47a4-968b-6dc76d97b89c
---
# Account Journey nodes

After you [create an account journey](journey-overview.md#create-an-account-journey) and [add the audience](journey-overview.md#add-the-account-audience-for-your-journey), build out the journey using nodes.

## Node types

| Node type | Details |
| --------- | ------- |
| [Account Audience](journey-overview.md#add-the-account-audience-for-your-journey) | Input account audience for the journey. This node is always the first node and is automatically created by default |
| [Action on people](#add-a-people-action) | Send email |
| | Change Score |
| | Assign Person to Buying Group |
| | Remove Person from Buying Group |
| | Add to Marketo Campaign |
| | Create Lead Interesting Moment |
| [Action on accounts](#add-an-account-action) | Change Data Value |
| | Remove Account from (current) Journey |
| | Add Account to (other) Journey |
| | Create Account Interesting Moment |
| | Add to Marketo Account List (implicit) |
| [Events for people](#add-a-people-event) | Data Value Changes |
| | Score change |
| | Opens Email |
| | Clicks link in email |
| | Clicks link on web page |
| | Assigned to Buying Group |
| | Removed from Buying Group |
| [Events for accounts](#add-an-account-event) | Change in Account Data Value |
| | Has interesting moment |
| [Split by people](#add-a-split-path-by-people-node) | Lead Attributes |
| | Data Value Changed (such as filter on activity history) |
| | Opened Email |
| | Clicked link in email |
| | Clicked link on web page |
| | Had Interesting moment |
| | Member of Buying Group |
| [Split by accounts](#add-a-split-path-by-account-node) | Change in Account Data Value (such as filter on activity history) |
| [Wait](#wait) | Available on account level |
| [Merge paths](#merge-paths) | |

## Take an action

Execute an action like send an email, change score, and so on.

**Action on accounts**: The action is applied to all people that are part of accounts on this path.

**Action on people**: The action is applied to all people on this path. An action on people can be used within the split path by people or split path by accounts.

### Add an account action

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

   ![Add journey node - split paths](./assets/add-node-action.png){width="400"}

1. In the node properties on the right, choose **[!UICONTROL Accounts]** for the action.

1. Select an action from the list and set any values for the action.

   ![Journey node - take an action on an account](./assets/node-take-action-account.png){width="700" zoomable="yes"}

### Add a people action

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

1. In the node properties on the right, choose **[!UICONTROL People]** for the action.

1. Select an action from the list and set any values for the action.

![Journey node - take an action on people](./assets/node-take-action-people.png){width="700" zoomable="yes"}

## Listen for an event

Move your audience forward to the next step in the journey when an event occurs.

* You can also define the amount of time the journey waits for this event. The journey ends after a timeout.
* Additionally, you can choose to add other nodes on your timeout path.

**Listen to events on accounts**: If at least one person from an account triggers an event, the account moves forward to the next step on the journey.

**Listen to events on people**: Events on people can only be applied on an account path; it is not available for a split by people node.

### Add an account event

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Listen for an event]**.

1. In the node properties on the right, choose **[!UICONTROL Accounts]** for the event type.

   ![Journey node - listen to events on account](./assets/node-listen-events-account.png){width="700" zoomable="yes"}

1. Select an event from the list.

1. Click **[!UICONTROL Edit event]** and define details for the event.

### Add a people event

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Listen for an event]**.

1. In the node properties on the right, choose **[!UICONTROL People]** for the event type.

   ![Journey node - listen to events on people](./assets/node-listen-events-people.png){width="700" zoomable="yes"}

1. Select an event from the list.

1. Click **[!UICONTROL Edit event]** and define details for the event.

### Add a timeout to an event node

If needed, define the amount of time the journey waits for the event. The journey ends after timeout.

1. Enable the timeout toggle.

1. Select the duration for which the journey waits for an event to occur before it times out.

   You can choose to end the path here or take a different course of action by setting another path.

1. To create a new path in the journey where you can add actions and events applicable to accounts when the event does not occur, select the **[!UICONTROL Set timeout path]** check box.

   ![Journey event node - set timeout path](./assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}

## Split paths

Split your audience based on filter conditions. 

**Split paths by accounts**: Paths split by accounts can include both account and people actions and events, and these paths can be split further.

_How does a split path by accounts node work?_ 

* When you add a split path node and choose _Account_, each path that is added includes an end node with the ability to add nodes to each edge.
* It is possible to split the path by Accounts repeatedly, such as in a nested manner. A split path includes an option for not adding the default path.
* Accounts/people that do not qualify for one of the split paths do not move forward in the journey.
* These paths can be combined using a merge node.

![Journey node - split paths by account](./assets/node-split-paths-account.png){width="700" zoomable="yes"}

**Split paths by people**: Paths split by people and can include only people actions, and these paths can't be split again. Paths automatically join back.

_How does a split path by people node work?_ 

* Split path by people nodes are grouped nodes. They automatically merge so that all the people in the audience can move forward to the next step without losing the context of the accounts that they belong to.
* Split path for people cannot be nested--you cannot add split path for people on a path that is in this grouped node.
* Split path includes an option for not adding a default path. Accounts/people who do not qualify do not move forward in the Journey.

![Journey node - split paths by people](./assets/node-split-paths-people.png){width="700" zoomable="yes"}

>[!NOTE]
>
>A maximum of 25 paths are supported.

### Add a split path by account node

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Add journey node - split paths](./assets/add-node-split.png){width="300"}

1. In the node properties on the right, choose **[!UICONTROL Accounts]** for the split.

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

   ![Split path node - add condition](./assets/node-split-properties-apply-condition.png){width="500"}

1. In the conditions editor, add one or more filters to define the split path.

   * Drag and drop filter attributes from the left navigation and complete the match definition.

   * Fine tune your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all attribute conditions or any condition.

      ![Split path node - conditions filter logic](./assets/node-split-conditions.png){width="700" zoomable="yes"}

   * Click **[!UICONTROL Done]**.

1. To add more paths, click **[!UICONTROL Add path]** and repeat the previous steps to add conditions applicable to this path.

   You can also label each path based on these conditions or use the default labels.

1. (Optional) Add a default path for accounts not qualified for the other paths. If not, the journey ends for these accounts.

   ![Split path node  properties - other accounts](./assets/node-split-properties-other-accounts.png){width="700" zoomable="yes"}

### Add a split path by people node

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Add journey node - split paths](./assets/add-node-split.png){width="300"}

1. In the node properties on the right, choose **[!UICONTROL People]** for the split.

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

1. In the conditions editor, add one or more filters to define the split path.

   * Drag and drop filter attributes from the left navigation and complete the match definition.

   * Fine tune your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all attribute conditions or any condition.

   * Click **[!UICONTROL Done]**.

1. To add more paths, click **[!UICONTROL Add path]** and repeat the previous steps to add conditions applicable to this path.

   You can also label each path based on these conditions or use the default labels.

1. Lastly, you can add a default path for people not qualified for the above paths. If not, the journey ends for these people

When you have conditions defined for each path that you're splitting your audience on the people level, you can add actions that you want to take on people.

>[!NOTE]
>
>When you split the audience by people, you can only add people actions.

## Wait

Wait for a certain duration before moving to the next step.

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Wait]**.

1. In the node properties on the right, set the **[!UICONTROL Duration]** of time to wait before the journey proceeds to the next node in the path.

![Journey node - wait](./assets/node-wait.png){width="700" zoomable="yes"}

## Merge paths

Different paths in your journey can be merged and unmerged using this node.

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

1. Click the split node to open its properties on the right.

1. Click [!UICONTROL Add path] to create three paths.

1. Add a combination of actions and events to each path.

1. Click the plus ( **+** ) icon for any one of these paths and choose **[!UICONTROL Merge]** from the displayed options.

   ![Journey node - merge paths](./assets/node-plus-icon-merge-paths.png){width="400"}

1. In the merge node properties, select the paths you want to merge.

   ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"}

   You should now see that the paths are merged so that accounts from the selected paths combine to a single path and can continue to progress through the journey.

1. If needed, you can unmerge paths by navigating back to the merge node properties and clearing the checkbox for any paths that you want to remove.

