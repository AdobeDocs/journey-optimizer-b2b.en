---
title: Person Journeys
description: Placeholder page for person journeys.
---
# Person Journeys

In Journey Optimizer B2B Edition Prime, person journeys are automated, multistep lead-based marketing plans using Marketo Engage data that orchestrate personalized experiences across channels in response to engagement, business events, or scheduled campaigns. 

To get started with your first person journey:

1. Create a person journey.
1. Add the nodes and define the journey flow in the journey map.
1. Publish the journey.

## Access and browse person journeys

On the left navigation, expand **[!UICONTROL Marketing Management]** and select **[!UICONTROL Person journeys]**.

You can enter text in the _Search_ tool at the top of the list to filter the displayed list by name.

### Journey list columns

The journeys list page includes the following columns:

Name (click the name to open the journey map for editing)
Status
Creation date
Created by
Last update
Last updated by
Published on
Published by
Start date
End date

You can sort the list by Status, Creation date, or Last update by clicking the column header.

To customize (show/hide) the columns that are displayed in the table, click the Customize table (  ) icon in the top-right corner. Select or clear the checkboxes in the dialog and click Apply.

### Journey status

The status of a journey can change based on the actions that you apply. Based on the status of a journey, certain actions are/are not available from the right side of the header.

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

The _journey map_ is the central zone in the journey workspace. It is where you can add journey nodes and configure them. Click a node to open its properties in the panel to the right of the layout and set them according to your design. A person journey always starts with a _[!UICONTROL Person audience]_ node, where you can define the input for the journey.

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


## Journey management



## Journey map

Click the name (displayed as a link) in the journeys list to review the details, make changes, and take actions.

The header of each journey map includes:

Journey name
Edit tool for the journey name (  Edit icon)
Status of the journey
From the journey map, you can Add the nodes and define the journey flow.

### Journey actions

The journeys list page includes all account or person journeys in your Journey Optimizer B2B Edition instance. From the list page, you can apply a number of actions to a journey.



#### Duplicate a journey

A duplicate action is similar to a clone function, but a duplicated journey does not include any created journey content assets. You can duplicate the details for the journey, or just a simple skeleton of the flow and path structure.

NOTE

Click the More icon (…) next to the journey name and choose Duplicate.

Depending on the status of the journey, you can also access the duplicate action from the journey details or journey map:

For a draft journey, click the More… menu at the top right and choose Duplicate.
For all other journey statuses, click Duplicate at the top right.
In the Duplicate Journey dialog, set the Name and Description for the new journey.
By default, the dialog uses the name of the duplicated journey appended with _copy. Enter another unique name for the journey as needed.

Choose the duplication Type:
Partial content duplication - Use this type to copy everything in the journey, excluding any created emails or SMS messages. Nodes that reference a Marketo Engage email or SMS message are fully intact.
Duplicate without details - Use this type copy only the node structure and paths. All node settings and path conditions are undefined (default), so that you can reuse the basic flow with different audience, actions, and path segmentation settings. All Wait nodes use the default of five days.
Click Duplicate.
The duplicated journey opens in the journey map, where you can set the details and create journey content as needed.

Delete a journey

Use a delete action to delete a journey permanently. You cannot delete a live or scheduled journey.

Click the More icon (…) next to the journey name and choose Delete.
Depending on the status of the journey, you can also access the delete action from the journey details or journey map:

For a draft journey, click the More… menu at the top right and choose Delete.
For other journey statuses, such as Finished or Aborted, click Delete at the top right.
In the confirmation dialog, click Delete.






