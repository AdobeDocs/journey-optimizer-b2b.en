---
title: Build and Publish a Journey
description: Create account and person journeys in the visual canvas, add action and event nodes, configure scheduling, and publish for live orchestration in Journey Optimizer B2B Edition.
feature: Account Journeys
role: User
exl-id: f536b1a1-8dfe-437f-a84d-b66879529621
---
# Build and publish a journey

To get started with a journey, create the journey and then construct the nodes and journey flow in the journey map.

![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the overview video](#overview-video)

## Create a journey

Under **[!UICONTROL Journey management]** in the left navigation, select the journey type that you want to create:

* **[!UICONTROL Account journeys]**
* **[!UICONTROL Person journeys]** (Beta)

_To add a new journey:_

+++Account journey

1. Click **[!UICONTROL Create Account Journey]** at the top-right of the page.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional).

   ![Create Account Journey dialog](./assets/account-journey-create-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**. 

+++

+++Person journey (Beta)

1. Click **[!UICONTROL Create Journey]** at the top-right of the page.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and **[!UICONTROL Description]** (optional).

   ![Create Journey dialog](./assets/person-journey-create-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**.

+++

## Building blocks for journey design

The _journey map_ is the central zone in the journey workspace. It is in this zone that you can add journey nodes and configure them. Click a node to open its properties pane to the right of the canvas and set them according to your design. A journey always starts with an audience node, where you can define the input for your journey:

* [Account audience node](./account-audience-nodes.md)
* [Person audience node](./person-audience-nodes.md)

After you create an account journey and add the audience, build out the journey using nodes. The journey map provides a canvas, where you can build your multistep B2B marketing use cases using the following node types to construct an account journey:

* [Take an action](./action-nodes.md)
* [Listen for an event](./listen-for-event-nodes.md)
* [Split paths](./split-merge-paths-nodes.md)
* [Wait](./wait-nodes.md)
* [Merge paths](./split-merge-paths-nodes.md)

## Guardrails

To help you build a journey without running into errors, the following guard rails are in place:

* _Deleting a Split path node_: Deleting a node requires deleting all subsequent nodes in each path.
* _Deleting a Merge node_: A merge node can be deleted only when there is one path connected to it. To delete a merge node, leave only one path selected.
* _Switching between account and people_: Changing the selection from accounts to people deletes all subsequent nodes in each path.

## Add a node

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on the path and select the node type.

1. Set the node properties on the right.

## Delete a node

1. Navigate to the journey map.

1. In the node properties on the right, click the _Delete_ ( ![Delete icon](../assets/do-not-localize/icon-delete.svg) ) icon.

1. In the conformation dialog, click **[!UICONTROL Delete]**.

## Add and delete a path

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on the path and add the [split path node](./split-merge-paths-nodes.md#split-paths).

1. In the node properties on the right, select **[!UICONTROL Account]**.

1. To add more paths, click **[!UICONTROL Add path]**.

   With each path that is created in the journey, a new path card appears in the properties.

1. Navigate to one of the paths in the journey and add [action](./action-nodes.md) or [event](./listen-for-event-nodes.md) nodes to this path using the plus icon.

1. Select the [split path](./split-merge-paths-nodes.md) node to open the properties on the right.

   The paths that have nodes on them cannot be deleted.

1. To delete these paths, you must delete all the nodes on that path first.

## Schedule a journey

When you publish a journey, it can start immediately or on a scheduled future date. The end date can be a maximum of three years from the start date. After a journey is published (_Live_ status), you can update the end date of the journey but not the start date.

1. Navigate to the journey map.

1. Schedule your journey by clicking **[!UICONTROL Journey settings]** in the header.

1. In the dialog, set the schedule options:

   * Choose a schedule type.
   
      To activate the journey at publish time, choose **[!UICONTROL Immediately]**.

      To activate the journey on a future date, choose **[!UICONTROL On a specific date]** and click the _Calendar_ icon to select the date.

      ![Journey settings dialog](./assets/account-journey-settings-dialog.png){width="400" zoomable="no"}
   
   * Specify the **[!UICONTROL End date]** for the journey. It can be a maximum of three years from the start date (this field is required to publish).

1. Click **[!UICONTROL Save]**.

   When you are ready to publish your journey, you can review these settings when you click _[!UICONTROL Publish]_.

## Publish a journey

You can publish a journey if there are no blocker errors. When published, the journey status changes to _Live_. If the journey has errors, the _[!UICONTROL Publish]_ button is dimmed with content information: `Resolve errors before publishing`.

>[!NOTE]
>
>After publishing an account journey, there is a delay of up to 24 hours for qualifying accounts to enter the journey.

1. At the top right of the journey map, click **[!UICONTROL Publish]**.

1. In the _[!UICONTROL Review journey settings]_ dialog, set the journey start options.

   If you already set the journey settings to define a schedule, review the settings.

   If you need to set the journey activation, choose a schedule type:
   
      * To activate the journey at publish time, choose **[!UICONTROL Immediately]**.

      * To activate the journey on a future date, choose **[!UICONTROL On a specific date]** and click the _Calendar_ icon to select the date.

1. If needed, specify the **[!UICONTROL End date]** for the journey.

   ![Journey settings dialog](./assets/journey-publish-dialog.png){width="400" zoomable="no"}

   It can be a maximum of three years from the start date (this field is required to publish).

1. Click **[!UICONTROL Next]**.

1. In the confirmation dialog, click **[!UICONTROL Publish]**.

## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3443204/?learn=on)
