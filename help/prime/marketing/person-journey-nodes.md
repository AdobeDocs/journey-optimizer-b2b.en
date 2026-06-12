---
title: Add Journey Nodes
description: Placeholder page for person journey nodes.
autotag-review: '2026-06-12T23:02:52.147Z'
TQID: 'https://experienceleague.adobe.com/sTnrOvrGIrgboPqOMrrkUvNU1y6zZJX42zEJxuUInKQ'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Add journey nodes

After you create a person journey, add the audience and build out the journey using nodes. The journey map provides a canvas, where you can build your multistep B2B marketing use cases.

The _[!UICONTROL Person audience]_ node is automatically the first node in the journey. After you select the audience, build your journey by combining the different action, event, and desicioning nodes as a multi-step, cross-channel scenario. Each node of a journey represents a step along a logical path.

## Person audience node

The person audience node specifies which person records enter the journey. When you create a person journey, the journey always starts with a person audience node that defines its input.

1. Click the node to select it.
1. In the node properties panel on the right, use one of the following input options for the person audience journey node:

   * **[!UICONTROL Dynamic list]** - Use a dynamic, rules-based people list. The list rules are evaluated at journey runtime to qualify members of the journey. People that later disqualify for the dynamic list are not removed from the journey.

   * **[!UICONTROL Static list]** - Use a static list of people as member of your journey. The current list membership is evaluated at journey runtime to qualify members for the journey. People that are later removed from the static list are not removed from the journey.

## People action nodes

In a person journey, use an action on people when you want to apply a change to all people on the node path. For an account journey, this node type can be used within the split path by people or split path by accounts.

### Actions and constraints

| Action | Contraints |
| ------ | ---------- |
| **[!UICONTROL Send email]** | <li>Create email <li>Send-time optimization (optional) |
| **[!UICONTROL Change Data Value]** | <li>Select person attribute <li>Set new value |

### Add an action node

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

1. In the node properties on the right, select an action from the list and set any values for the action.

<!-- ![Person journey node - take an action](./assets/node-take-action-people.png){width="700" zoomable="yes"} -->

+++[!UICONTROL Send email]

Use this action to send an email. After you  create the email for the node, you can design, personalize, and preview email messages in the email design space (see [Email authoring](../content/email-authoring.md)).

<!-- ![Take an action - Send email](./assets/node-action-send-email-from-marketo.png){width="300"} -->

You can use [Send-time optimization](../marketing/email-send-time-optimization.md) to personalize email delivery timing by predicting when each profile is most likely to engage.

<!--
>[!NOTE]
>
>You can use email deduplication in account journeys to ensure that the same email is not sent multiple times to the same email address within a journey. For more information, see [Email deduplication](../content/email-deduplication.md).
-->

+++

+++[!UICONTROL Change data value]

Use this action to change the value of a people profile attribute in the database. Select the attribute and then set the new value.

<!-- ![Take an action - Update person profile](./assets/node-action-update-person-profile.png){width="300"} -->

+++

## Event nodes

Add the _Listen for an event_ node to move your audience forward to the next step in the journey when an event occurs.

### People event filters

| Filters | Description |
| ------- | ----------- |
| Activity history > Email | Email activities based on conditions that are evaluated using one or more selected email messages: <li>Clicked link in email <li>Opened email |
| Activity history > Data Value Changed | For a selected person attribute, a value change occurred. These change types include: <li>New value <li>Previous value <li>Reason <li>Source <li>Date of activity <li> Min. number of times |

### Add an event node

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Listen for an event]**.

1. In the node properties on the right, choose **[!UICONTROL People]** for the event type.

   <!-- ![Journey node - listen to events on people](./assets/node-listen-events-people.png){width="700" zoomable="yes"} -->

1. Select an event from the list.

1. Click **[!UICONTROL Edit event]** and define details for the event.

>[!NOTE]
>
>The timeout functionality for Listen for an event node does not currently function and will be enabled in a later phase.

## Split paths nodes

Use split nodes to segment people according to the conditions that you define. Create paths for the audience list according to conditions, define each path with action and event nodes for the segment, and then combine the paths and continue the journey.

A Split paths node defines one or more segmented paths based on people filters.

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->


_**How a split path by people node works**_ 

* Evaluation of each path is from top to bottom. If a person matches for the first and second paths, they proceed along the first path only.
* The node supports the definition of an _Other people_ path, where you can add actions or events for people that do not match one of the defined segments/paths.

### Matching filters

For each path that you define for the node, use the following filter types to match people according to one or more conditions:

* Activity history - You can define a path according to the person's activity related to:

   * Email messages
   * Change in data value

* Person attributes - Define a condition according to a person's attributes, such as country, job title, or list membership.

### Add a split paths node

<!--
>[!NOTE]
>
>When you split paths by people, a _Close split paths_ node is automatically inserted to end the split. A split-by-people path allows only _Take an action_ on people nodes.
-->

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   <!-- ![Add journey node - split paths](./assets/add-node-split.png){width="300" zoomable="no"} -->

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

1. In the conditions editor, add one or more filters to define the split path.

   * Drag and drop any of the people filters from the left navigation and complete the match definition.

   * Fine tune your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all conditions or any one condition.

      <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

   * Click **[!UICONTROL Done]**.

1. To add more paths, click **[!UICONTROL Add path]** and repeat the previous steps to add conditions applicable to the path.

   You can also label each path based on these conditions or use the default labels.

1. If needed, reorder the paths according to the priority that you want for the split.

   Path filtering is evaluated in top-down order. Each person proceeds along the first path that matches.

   Click the up and down arrows at the top right of each path card to move it higher or lower in the list of paths.

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. Enable the **[!UICONTROL Other people]** option to add a default path for people that are not a match for the defined paths. 

   When this option is not enabled, people that do not match a defined segment/path move past the split and proceed to the next step in the journey.

When you have conditions defined for each path, you can add action or event nodes that you want to apply to people on a path.

## Merge paths nodes

1. Navigate to the journey map and locate the split paths node with two or more paths.

   Each path should have a combination of actions and events on each path.

1. Click the plus ( **+** ) icon at the end of any one of these paths and choose **[!UICONTROL Merge paths]** from the displayed options.

   <!-- ![Journey node - merge paths](./assets/node-plus-icon-merge-paths.png){width="400" zoomable="no"} -->

1. In the node properties at the right, select the paths you want to merge.

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   At this point, the paths are merged so that people from the selected paths combine to a single path that can continue to progress through the journey.

1. If needed, you can unmerge paths by navigating back to the merge paths node properties and clearing the checkbox for any paths that you want to remove.
