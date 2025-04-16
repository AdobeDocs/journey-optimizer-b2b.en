---
title: Account Journeys
description: Learn about account journeys and how you can create and manage them.
feature: Account Journeys
exl-id: 5c22f11f-1967-4b55-8aee-16371173c040
---

# Account journeys

With account journeys, you can streamline demand generation and buying group qualification and drive more qualified demand for your acquisition, upsell/cross-sell, and retention programs. Tailor your journeys for each buying group and buying group member using automated engagement across email, SMS, events, and more. 

Define sales-driven engagement that includes email, SMS, and more inside account journeys to coordinate inbound marketing with outbound sales activities for each buying group member.

![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the overview video](#overview-video)

## Get started with a journey

To get started with account journeys:

1. [Create a journey](./create-publish-journey.md#create-an-account-journey).
1. [Add the nodes](./create-publish-journey.md#add-a-node) and [define the journey flow](./create-publish-journey.md#add-and-delete-a-path) in the journey map.
1. [Publish the journey](./create-publish-journey.md#publish-an-account-journey).

## Access and browse account journeys

On the left navigation, click **[!UICONTROL Account journeys]**.

![Access account journeys](./assets/account-journey-browse.png){width="800" zoomable="yes"}

The displayed journeys page includes the following columns:

* [!UICONTROL Name] (click the name to open the journey for editing)
* [!UICONTROL Status]
* [!UICONTROL Description] 
* [!UICONTROL Created by]
* [!UICONTROL Last updated at]
* [!UICONTROL Last updated by]
* [!UICONTROL Published on]
* [!UICONTROL Published by]

Use the _Search_ tool at the top to locate the journey by name. You can sort the list by _[!UICONTROL Status]_ by clicking the column header.

You can customize the columns that are displayed in the table by clicking the _Customize table_ ( ![Customize table](../assets/do-not-localize/icon-column-settings.svg) ) icon in the top-right corner. Select or clear the checkboxes in the dialog and click **[!UICONTROL Apply]**. 

![Choose the columns to display in the acount journeys list](./assets/account-journeys-list-columns.png){width="800" zoomable="yes"}

## Anatomy of an account journey

Click the name (displayed as a link) in the _[!UICONTROL Account journeys]_ list to review the details, make changes, and take actions.

![Account journey workspace](./assets/account-journey-workspace.png){width="800" zoomable="yes"}

The header of each account journey map includes: 

* Journey name
* Access to edit the journey name ( ![Edit icon](../assets/do-not-localize/icon-edit.svg) _Edit_ icon)
* Status of the journey

The status of a journey can change based on the actions that you apply. Based on the status of a journey, certain actions are/are not available from the right side of the header.

| Status | Description | Available actions |
| ------ | ----------- | ----------------- |
| _**Draft**_ | An unpublished journey that is editable. |<ul><li>[Publish](./create-publish-journey.md#publish-an-account-journey)</li><li>Duplicate </li><li>Delete </li></ul> |
| _**Live**_ | Journey status changes from Draft to Live when a journey is published. In this state, it is no longer editable. | <ul><li>Duplicate </li><li>Close to new entries </li><li>Abort </li></ul> |
| _**Closed to new entries**_ | The journey status changes from _Live_ to _Closed to new entries_ when you click [!UICONTROL Close to new entries] in the top navigation. | <ul><li>Duplicate </li><li>Abort </li></ul> |
| _**Aborted**_ | Journey status changes from _Live_ or _Closed to new entries_ when you abort a journey. An aborted journey cannot be restarted. | <ul><li>Duplicate </li><li>Delete </li></ul> |
| _**Finished**_ | When all accounts in a journey complete the journey, the status changes from Live or Closed to new entries to Finished.| <ul><li>Duplicate </li><li>Delete </li></ul> |

## Manage journeys

The _Account Journeys_ list includes all journeys in your Journey Optimizer B2B Edition instance.

### Abort journey

If you abort (stop) a live or scheduled journey, accounts in the journey immediately stop their progress, and no further journey entrance can happen. An aborted journey cannot be restarted. 

>[!IMPORTANT]
>
>When the account journey is used in another journey from a _Take an action_ node with the _Add Account to (other) Journey_ action, aborting the journey blocks that action from that journey.

1. Click the journey name to open it.

1. Click the **[!UICONTROL More...]** menu at the top right and choose **[!UICONTROL Abort]**.

   ![Click More at the top right](./assets/account-journey-live-more-menu.png){width="450"}

1. In the confirmation dialog, click **[!UICONTROL Abort]**.

### Close to new entries

If you close a live journey, accounts that are currently in the journey continue their path in that journey and no further journey entrance can happen. A closed journey cannot be restarted. You can duplicate a closed journey.

>[!IMPORTANT]
>
>When the account journey is used in another journey from a _Take an action_ node with the _Add Account to (other) Journey_ action, closing it to new entries blocks that action from that journey.

1. Click the journey name to open it.

1. Click the **[!UICONTROL More...]** menu at the top right and choose **[!UICONTROL Close to new entries]**.

1. In the confirmation dialog, click **[!UICONTROL Close to new entries]**.

### Duplicate journey

A duplicate action is similar to a clone function, but a duplicated journey does not include any created journey content assets. You can duplicate the details for the account journey, or just a simple _skeleton_ of the flow and path structure.s

1. Click the _More_ icon (**...**) next to the journey name and choose **[!UICONTROL Duplicate]**.

   ![Click the ... icon and choose Duplicate](./assets/account-journeys-list-more-menu.png){width="450"}

   Depending on the status of the account journey, you can also access the duplicate action from the journey details or journey map:

   * For a draft journey, click the **[!UICONTROL More...]** menu at the top right and choose **[!UICONTROL Duplicate]**.

   * For all other journey statuses, click **[!UICONTROL Duplicate]** at the top right.

     ![Click Duplicate at the top right](./assets/account-journey-duplicate-button.png){width="450"}

1. In the _Duplicate Journey_ dialog, set the **[!UICONTROL Name]** and **[!UICONTROL Description]** for the new journey.

   By default, the dialog uses the name of the duplicated journey appended with __copy_. Enter another unique name for the journey as needed.

   ![Duplicate Journey dialog](./assets/account-journey-duplicate-dialog.png){width="400"}

1. Choose the duplication **[!UICONTROL Type]**:

   * **[!UICONTROL Partial content duplication]** - Use this type to copy everything in the journey, excluding any created emails or SMS messages. Nodes that reference a Marketo Engage email or SMS message are fully intact.

   * **[!UICONTROL Duplicate without details]** - Use this type copy only the node structure and paths. All node settings and path conditions are undefined (default), so that you can reuse the basic flow with different audience, actions, and path segmentation settings. All _Wait_ nodes use the default of five days.

1. Click **[!UICONTROL Duplicate]**.

   The duplicated account journey opens in the journey map, where you can set the details and create journey content as needed.

### Delete journey

Use a delete action to delete a journey permanently. You cannot delete a live or scheduled journey.

1. Click the _More_ icon (**...**) next to the journey name and choose **[!UICONTROL Delete]**.

    Depending on the status of the account journey, you can also access the delete action from the journey details or journey map:

   * For a draft journey, click the **[!UICONTROL More...]** menu at the top right and choose **[!UICONTROL Delete]**.

   * For other journey statuses, such as _Finished_ or _Aborted_, click **[!UICONTROL Delete]** at the top right.

1. In the confirmation dialog, click **[!UICONTROL Delete]**.

## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3443202/?learn=on)
