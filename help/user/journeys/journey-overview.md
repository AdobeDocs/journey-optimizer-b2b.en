---
title: Account Journeys
description: Learn about account journeys and how you can create and manage them.
feature: Account Journeys
exl-id: 5c22f11f-1967-4b55-8aee-16371173c040
---

# Account journeys

Build and execute journeys that are tailored for each buying group and buying group member using automated engagement across email, SMS, events,  and more. WIth account journeys you can streamline demand generation and buying group qualification and drive more qualified demand for your acquisition, upsell/cross-sell, and retention programs.

Define sales-driven engagement that includes email, SMS, and more inside account journeys to coordinate inbound marketing with outbound sales activities for each buying group member.

## Access and browse account journeys

1. In your Adobe Experience Platform home page, click Adobe Journey Optimizer B2B Edition.

1. On the left navigation, click **[!UICONTROL Account journeys]**.

   ![Access account journeys](./assets/account-journey-browse.png){width="800" zoomable="yes"}

   The displayed journeys page includes the following columns:

   * [!UICONTROL Name] (click the name to open the account journey for editing)
   * [!UICONTROL Status]
   * [!UICONTROL Description] 
   * [!UICONTROL Created by]
   * [!UICONTROL Last updated at]
   * [!UICONTROL Last updated by]
   * [!UICONTROL Published on]
   * [!UICONTROL Published by]

  This table includes the ability to search by Name and Created by. Sort is currently unavailable.

You can customize the displayed table by clicking the _Columns_ icon in the top-right corner and selecting or clearing the checkboxes. 

![Choose the columns to display in the acount journeys list](./assets/account-journeys-list-columns.png){width="800" zoomable="yes"}

## Anatomy of an account journey

Click the name (displayed as a link) in the _[!UICONTROL Account journeys]_ list to review the details, make changes, and take actions.

![Account journey workspace](./assets/account-journey-workspace.png){width="800" zoomable="yes"}

The editor header of each account journey includes: 

* Journey name
* Ability to edit the name (_Edit_ icon)
* Status of the journey

The following actions are available in the header:

* **Publish** - You can publish a journey if there are no blocker errors. When published, the journey status changes to _Live_. If the journey has errors, the button is dimmed with content information: `Resolve errors before publishing`.
* **Duplicate** - This action is similar to a clone function, but the duplicated journey does not include any assets.
* **Close to new entries** - If you close a journey, accounts currently in the journey continue their path in the journey and no further journey entrance can happen. A closed journey cannot be restarted. You can duplicate a closed journey.
* **Abort** - If you stop a journey, accounts in the journey immediately stop their progress and no further journey entrance can happen. A stopped journey cannot be restarted. If you block new entrances without stopping people's progress, consider closing the journey instead.
* **Delete** - This action permanently deletes the journey.

The status of a Journey changes based on the actions that you apply. Based on the status of a journey, certain actions are/are not available in the header.

| Status | Description | Available actions |
| ------ | ----------- | ----------------- |
| _**Draft**_ | An unpublished journey that is editable. |<ul><li>Publish</li><li>Duplicate </li><li>Delete </li></ul> |
| _**Live**_ | Journey status changes from Draft to Live when a journey is published. In this state, it is no longer editable. | <ul><li>Duplicate </li><li>Close to new entries </li><li>Abort </li></ul> |
| _**Closed to new entries**_ | The journey status changes from _Live_ to _Closed to new entries_ when you click [!UICONTROL Close to new entries] in the top navigation. | <ul><li>Duplicate </li><li>Abort </li></ul> |
| _**Aborted**_ | Journey status changes from _Live_ or _Closed to new entries_ when you abort a journey. An aborted journey cannot be restarted. | <ul><li>Duplicate </li><li>Delete </li></ul> |
| _**Finished**_ | When all accounts in a journey complete the journey, the status changes from Live or Closed to new entries to Finished.| <ul><li>Duplicate </li><li>Delete </li></ul> |

## Get started with a journey

To get started with an account journey, create the journey and then construct the nodes and journey flow in the journey editor.

### Create an account journey

1. On the left navigation, click **[!UICONTROL Account journeys]**.

1. Click **[!UICONTROL Create Account Journey]** at the top-right of the page.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional).

   ![Create Account Journey dialog](./assets/account-journey-create-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**.   

### Building blocks of a journey

The _journey map_ is the central zone in the journey designer. It is in this zone that you can add journey nodes and configure them. Click a node to open its properties pane to the right of the canvas and set them according to your design. An account journey always starts with an [Account Audience node](./account-audience-nodes.md) where you can add input to your journey.

After you create an account journey and add the audience, build out the journey using nodes. The journey map provides a canvas, where you can build your multistep B2B marketing use cases using the following node types to construct an account journey:

* [Take an action](./action-nodes.md)
* [Listen for an event](./listen-for-event-nodes.md)
* [Split paths](./split-merge-paths-nodes.md)
* [Wait](./wait-nodes.md)
* [Merge paths](./split-merge-paths-nodes.md)

### Guardrails

To help you build a journey without running into errors, the following guard rails are in place:

* _Deleting a Split path node_: You cannot delete a node without deleting all subsequent nodes in each path.
* _Deleting a Merge node_: A merge node can be deleted only when there is one path connected to it. To delete a merge node, leave only one path selected.
* _Switching between account and people_: You cannot change the selection from accounts to people without deleting all subsequent nodes in each path.

### Add a node

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on the path and select the node type.

1. Set the node properties on the right.

### Delete a node

1. Navigate to the journey editor.

1. In the node properties on the right, click the _Delete_ ( ![Delete icon](../assets/do-not-localize/icon-delete.svg) ) icon.

1. In the conformation dialog, click **[!UICONTROL Delete]**.

### Add and delete a path

1. Navigate to the journey editor.

1. Click the plus ( **+** ) icon on the path and add the [split path node](./split-merge-paths-nodes.md#split-paths).

1. In the node properties on the right, select **[!UICONTROL Account]**.

1. To add more paths, click **[!UICONTROL Add path]**.

   With each path that is created in the journey, a new path card appears in the properties.

1. Navigate to one of the paths in the journey and add [action](./action-nodes.md) or [event](./listen-for-event-nodes.md) nodes to this path using the plus icon.

1. Select the [split path](./split-merge-paths-nodes.md) node to open the properties on the right.

   The paths that have nodes on them cannot be deleted.

1. To delete these paths, you must delete all the nodes on that path first.

### Schedule a journey

When you publish a journey, it can start immediately or on a scheduled future date. The end date can be a maximum of three years from the start date. After a journey is published (_Live_ status), you can update the end date of the journey but not the start date.

1. Navigate to the journey editor.

1. Schedule your journey by clicking [!UICONTROL Journey settings] in the header.

1. In the dialog, set the schedule options:

   * Chose a schedule type.
   
      To activate the journey at publish time, choose **[!UICONTROL Immediately]**.

      To activate the journey on a future date, choose **[!UICONTROL On a specific date]** and click the _Calendar_ icon to select the date.

      ![Journey settings dialog](./assets/account-journey-settings-dialog.png){width="400" zoomable="no"}
   
   * Specify the **[!UICONTROL End date]** for the journey. It can be a maximum of three years from the start date (this field is required).

1. Click **[!UICONTROL Save]**.

   When you are ready to publish your journey, you can review these settings when you click _[!UICONTROL Publish]_.

### Publish an account journey


