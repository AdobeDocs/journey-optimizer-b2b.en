---
title: Person Journeys
description: Placeholder page for person journeys.
autotag-review: '2026-06-12T23:03:17.139Z'
TQID: 'https://experienceleague.adobe.com/MhkAuypbebo-n9uwxFPUKbNgyHijaTnaVsqhs9-lXC0'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Person Journeys

In Journey Optimizer B2B Edition Prime, person journeys are automated, multistep lead-based marketing plans that orchestrate personalized experiences across channels. These journeys use Marketo Engage data to execute these marketing plans in response to engagement, business events, or scheduled campaigns.

>[!NOTE]
>
>Each journey resides with the structure of a defined program. You must have a created program before you create a journey.

_To define a person journey:_

1. Create the person journey.
1. Add the nodes and define the journey flow in the journey map.
1. Publish the journey.

## Access and browse person journeys

On the left navigation, expand **[!UICONTROL Marketing Management]** and select **[!UICONTROL Person journeys]**.

You can enter text in the _Search_ tool at the top of the list to filter the displayed list by name.

### Journey list columns

The journeys list page includes the following columns:

* Name (click the name to open the journey map for editing)
* Status
* Creation date
* Created by
* Last update
* Last updated by
* Published on
* Published by
* Start date
* End date

You can sort the list by Status, Creation date, or Last update by clicking the column header.

Customize the columns that you want to display in the table by clicking the _Customize table_ ( ![Customize table icon](../../user/assets/do-not-localize/icon-column-settings.svg) )  icon at the top right. Select or clear the checkboxes in the dialog and click **Apply**.

### Journey status

The status of a journey can change based on the actions that you apply. Based on the status of a journey, certain actions are available from the right side of the header.

| Status | Description | Available actions |
| ------ | ----------- | ----------------- |
| Draft | An unpublished journey that is editable. | <li>Publish <li>Duplicate <li>Delete |
| Live | Journey status changes from Draft to Live when a journey is published. In this state, it is no longer editable. | <li>Duplicate |
| Finished | When all account or person audience members in a journey complete the journey, the status changes from Live or Closed to new entries to Finished. | <li>Duplicate <li>Delete |

## Create a person journey

1. Click **[!UICONTROL Create Journey]** at the top-right of the journey list.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional).

<!-- 
   ![Create Journey dialog](./assets/person-journey-create-dialog.png){width="400"}
-->

1. Click **[!UICONTROL Create]**.

### Journey design

The _journey map_ is the central zone in the journey workspace. It is where you can add journey nodes and configure them. Click a node to open its properties in the panel to the right of the layout and set them according to your design. A person journey always starts with a [_[!UICONTROL Person audience]_ node](./), where you can define the input for the journey.

<!--
![Journey map for newly created journey](./assets/person-journey-create-dialog.png){width="400"}
-->

After you create a person journey and add the person audience, build out the journey using nodes. The journey map provides a canvas, where you can build your multistep B2B marketing use cases using the following node types to construct the journey:

* [Take an action](./action-nodes.md)
* [Listen for an event](./listen-for-event-nodes.md)
* [Wait](./wait-nodes.md)
* [Split paths](./split-merge-paths-nodes.md)
* [Next best path](./next-best-path.md)
* [Merge paths](./split-merge-paths-nodes.md)

The header of each journey map includes the journey name and status. Click the _Edit_ ( ![Edit icon](../../user/assets/do-not-localize/icon-edit.svg) ) to change the journey name or description information.

## Journey management

Click the name (displayed as a link) in the journeys list to review the details, make changes, and take actions.

### Journey actions

The journeys list page includes all person journeys in your Journey Optimizer B2B Prime instance. From the list page, you can apply a number of actions to a journey.

#### Duplicate a journey

A duplicate action is similar to a clone function, but a duplicated journey does not include any created journey content assets. You can duplicate the details for the journey, or just a simple skeleton of the flow and path structure.

1. Click the More icon (…) next to the journey name and choose **[!UICONTROL Duplicate]**.

   Depending on the status of the journey, you can also access the duplicate action from the journey details or journey map:

   * For a draft journey, click the **More** menu at the top right and choose **Duplicate**.
   * For all other journey statuses, click **Duplicate** at the top right.

1. In the _Duplicate Journey_ dialog, set the **Name** (required) and **Description** (optional) for the new journey.

   By default, the dialog uses the name of the duplicated journey appended with _copy. Enter another unique name for the journey as needed.

1. Choose the duplication Type:

   * **Partial content duplication** - Use this type to copy everything in the journey, excluding any created emails or SMS messages. Nodes that reference a Marketo Engage email or SMS message are fully intact.
   * **Duplicate without details** - Use this type copy only the node structure and paths. All node settings and path conditions are undefined (default), so that you can reuse the basic flow with different audience, actions, and path segmentation settings. All Wait nodes use the default of five days.

1. Click **Duplicate**.

   The duplicated journey opens in the journey map, where you can set the details and create journey content as needed.

## Delete a journey

Use a delete action to delete a journey permanently. You cannot delete a live or scheduled journey.

1. Click the _More_ icon ( **...** ) next to the journey name and choose **Delete**.

   Depending on the status of the journey, you can also access the delete action from the journey details or journey map:

   * For a draft journey, click the **More** menu at the top right and choose Delete.
   * For other journey statuses, such as _Finished_ or _Aborted_, click **Delete** at the top right.

1. In the confirmation dialog, click Delete.
