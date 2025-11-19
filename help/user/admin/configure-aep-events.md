---
title: Select Experience Events and Fields
description: Configure Experience Platform event definitions to trigger real-time account journeys in Journey Optimizer B2B Edition based on customer behavior.
feature: Setup, Integrations
role: Admin
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a beta release"
solution: Journey Optimizer B2B Edition, Experience Platform
exl-id: a7696d03-f4c4-4f64-8ef2-b15e59b59770
---
# Select Experience Events and fields

Administrators can select specific [AEP Experience Events](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent){target="_blank"} and their associated fields within the Experience Event union schema. After selection, users can configure decisioning rules to listen to those Experience Events to enable dynamic and targeted campaign actions based on near real-time event data. 

<!-- ![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the video overview](#overview-video) -->
Using AEP experience events in journeys is a two-step process: 

1. An administrator [adds AEP experience events and fields](#add-an-event) in the Journey Optimizer B2B Edition configurations.

2. In a journey, a marketer adds a _Listen for an event_ node and [selects an Experience Event](../journeys/listen-for-event-nodes.md#listen-for-an-experience-event).

   * Selects the event to use in the node.
   * Selects the fields to use as constraints.

>[!BEGINSHADEBOX]

## Guidelines and limitations

As you select events to meet your organizational goals, keep the following in mind: 

* Journeys can listen to Experience Events that are ingested using Experience Platform streaming capabilities, such as Web SDK or HTTP API. 

* You can use Experience Events for decisioning purposes within a journey, but they are not retained. Therefore, you cannot leverage a historical record of Experience Events within Journey Optimizer B2B Edition. 

* When you use an Experience Event and publish the journey, you can add more fields, but you cannot remove fields that were previously selected. 

* You can reference an Experience Event in multiple journeys or use one more than once within the same journey. 

>[!ENDSHADEBOX]

## Manage Experience Events

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Configurations]**.

1. Click **[!UICONTROL XDM Classes]** on the intermediate panel, and then click the **[!UICONTROL Events]** tab to display the list of the available events.

   ![Access the selected Experience Events](./assets/configurations-xdm-classes-events.png){width="800" zoomable="yes"}

   The table is sorted by the _[!UICONTROL Last update]_ column, with the most recently updated events at the top by default.

   From this page, you can [select](#add-an-event) and [edit](#edit-an-event) events for use in journeys.
      
   To access the details for a selected event, click the event name.

### Filter the event list

Enter text in the _[!UICONTROL Search]_ field to filter the displayed events for a match of the event name.

![Filter the list of selected events by name](./assets/configurations-xdm-classes-events-search.png){width="600" zoomable="yes"}

### Add an event

To make an Experience Event available for a _Listen for an event_ node in a journey, select the event and the supported fields.

>[!NOTE]
>
>In the beta release, you cannot remove events from the list. Make sure that each event that you add is intended for use by your organization.

1. Click **[!UICONTROL Select experience event]** at the top right.

   The event details page is displayed. From this page, you can choose the event type and the fields.

   ![Event details for a new event](./assets/configurations-xdm-classes-events-select-new.png){width="700" zoomable="yes"}

1. Choose the event type.

   * Click **[!UICONTROL Select event type]**.

   * In the dialog, choose the event type.

      Use the _[!UICONTROL Search]_ field to filter the displayed list by name. Use the **[!UICONTROL Only show selected fields]** slider to review the current selections.

      ![Select event type dialog](./assets/configurations-xdm-classes-select-event-type-dialog.png){width="450" zoomable="yes"}      
   
   * Click **[!UICONTROL Select]**.

1. Choose one or more fields for the event type.

   * Click **[!UICONTROL Select fields]**.
   
   * In the dialog, select the fields that you want to use as constraints for matching events.

      Use the _[!UICONTROL Search]_ field to filter the displayed list by name. Use the **[!UICONTROL Only show selected fields]** slider to review the current selections.

      ![Select fields dialog](./assets/configurations-xdm-classes-select-fields-dialog.png){width="450" zoomable="yes"} 
   
   * Click **[!UICONTROL Select]**.

1. In the event details page, click **[!UICONTROL Save]**.

The saved event is displayed in the list on the _[!UICONTROL Events]_ tab.

### Edit an event

Edit the event details to change the fields.

1. Click the event name, or click the _More menu_ ( **...** ) icon and choose **[!UICONTROL Edit]**.

   ![Click the More menu icon](./assets/configurations-xdm-classes-events-more-menu.png){width="500" zoomable="yes"}    

1. Click **[!UICONTROL Edit fields]** to add more fields or remove existing selections in the _[!UICONTROL Select fields]_ dialog.

1. Click **[!UICONTROL Select]** to save your selections.

### Remove an event

>[!NOTE]
>
>For the Beta release of this feature, you cannot remove an event from the list of selected events. Event removal is planned for the GA release.

<!-- ## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3448637/?learn=on) -->