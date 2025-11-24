---
title: Select Experience Events and Fields
description: Select Experience Platform events and fields to trigger real-time decisioning in journeys based on customer behavior.
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

* You can select up to 50 events and up to 100 fields per event.

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
>In the beta release, you cannot remove events from the list. Make sure that each event that you add is one that your organization intends to use.

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

## Events and fields

For [!DNL Journey Optimizer B2B Edition], certain people-level activities are captured as [!DNL Experience Platform] Experience Events. These events are stored in a system dataset that uses the XDM Experience Event schema and includes journey-specific field groups. You can use these events in [!UICONTROL Journey Optimizer B2B Edition] like any other Experience Event. 

Each event exposes a defined set of fields that can be used in journey _Listen for an event_ nodes (decisioning based on events). Review the available event types and their fields to determine which event and fields to use in these journey nodes:

### Email sent

This event tracks when a marketing email was sent to a person.

Event type: `directMarketing.emailSent`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Email source ID | `directMarketing.emailSent.mailingKey.sourceID` |
| Email source type | `directMarketing.emailSent.mailingKey.sourceType` |
| Email source instance ID | `directMarketing.emailSent.mailingKey.sourceInstanceID ` |
| Email source key | `directMailing.emailSent.mailingKey.sourceKey` |
| Mailing name | `directMarketing.emailSent.mailingName` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Email delivered

This event tracks when an email was delivered successfully to a person's email service.

Event type: `directMarketing.emailDelivered `

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Mailing source ID | `directMarketing.mailingKey.sourceID` | 
| Mailing source type | `directMarketing.mailingKey.sourceType` |
| Mailing source instance ID | `directMarketing.mailingKey.sourceInstanceID` |
| Mailing source key | `directMarketing.mailingKey.sourceKey` |
| Mailing name | `directMarketing.mailingName` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Email opened

This event tracks when a person opened a marketing email.

Event type: `directMarketing.emailOpened`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Mailing source ID | `directMarketing.mailingKey.sourceID` | 
| Mailing source type | `directMarketing.mailingKey.sourceType` |
| Mailing source instance ID | `directMarketing.mailingKey.sourceInstanceID` |
| Mailing source key | `directMarketing.mailingKey.sourceKey` |
| Mailing name | `directMarketing.mailingName` |
| Is mobile device | `device.isMobileDevice` |
| Device model | `device.model` |
| User agent | `environment.browserDetails.userAgent` | 
| Operating system | `environment.operatingSystem` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Email clicked

This event tracks when a person clicked a link in a marketing email.

Event type: `directMarketing.emailClicked`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Mailing source ID | `directMarketing.mailingKey.sourceID` | 
| Mailing source type | `directMarketing.mailingKey.sourceType` |
| Mailing source instance ID | `directMarketing.mailingKey.sourceInstanceID` |
| Mailing source key | `directMarketing.mailingKey.sourceKey` |
| Mailing name | `directMarketing.mailingName` |
| Link URL | `directMarketing.linkURL` | 
| Is mobile device | `device.isMobileDevice` | 
| Model | `device.model` |
| User agent  | `environment.browserDetails.userAgent` |
| Operating system | `environment.operatingSystem` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Email bounced

This event tracks when an email to a person bounced.

Event type: `directMarketing.emailBounced`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Mailing source ID | `directMarketing.mailingKey.sourceID` | 
| Mailing source type | `directMarketing.mailingKey.sourceType` |
| Mailing source instance ID | `directMarketing.mailingKey.sourceInstanceID` |
| Mailing source key | `directMarketing.mailingKey.sourceKey` |
| Mailing name | `directMarketing.mailingName` |
| Email | `directMarketing.email` |
| Email bounced code | `directMarketing.emailBouncedCode` | 
| Email bounced details | `directMarketing.emailBouncedDetails` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Email bounced soft

This event tracks when an email to a person soft-bounced.

Event type: `directMarketing.emailBouncedSoft`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Mailing source ID | `directMarketing.mailingKey.sourceID` | 
| Mailing source type | `directMarketing.mailingKey.sourceType` |
| Mailing source instance ID | `directMarketing.mailingKey.sourceInstanceID` |
| Mailing source key | `directMarketing.mailingKey.sourceKey` |
| Mailing name | `directMarketing.mailingName` |
| Email | `directMarketing.email` | 
| Email bounced code | `directMarketing.emailBouncedCode` | 
| Email bounced details | `directMarketing.emailBouncedDetails` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Email unsubscribed

This event tracks when a person unsubscribed from a marketing email.

Event type: `directMarketing.emailUnsubscribed `

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey)` |
| Mailing source ID | `directMarketing.mailingKey.sourceID` | 
| Mailing source type | `directMarketing.mailingKey.sourceType` |
| Mailing source instance ID | `directMarketing.mailingKey.sourceInstanceID` |
| Mailing source key | `directMarketing.mailingKey.sourceKey` |
| Mailing name | `directMarketing.mailingName` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Visit web page

This event type is the standard method for marking the hit as a page view.

Event type: `web.webpagedetails.pageViews`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Web page source ID | `web.webPageDetails.webPageKey.sourceID` |
| Web page source type | `web.webPageDetails.webPageKey.sourceType` | 
| Web page source instance ID | `web.webPageDetails.webPageKey.sourceInstanceID` | 
| Web page source key | `web.webPageDetails.webPageKey.sourceKey` | 
| Web page name | `web.webPageDetails.name` |
| Web page URL | `web.webPageDetails.URL` |
| Web page query parameters | `web.webPageDetails.queryParameters` | 
| Web page ID | `web.webPageDetails.webPageID` | 
| User agent | `environment.browserDetails.userAgent` |
| Referrer URL | `web.webReferrer.URL` |

+++

### Form filled out

This event tracks when a person filled out a form on a web page.

Event type: `web.formFilledOut`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Web form source ID | `web.fillOutForm.webFormKey.sourceID` |
| Web form source type | `web.fillOutForm.webFormKey.sourceType` |
| Web form source instance ID | `web.fillOutForm.webFormKey.sourceInstanceID` |
| Web form source key | `web.fillOutForm.webFormKey.sourceKey` |
| Web form ID | `web.fillOutForm.webFormID` |
| Web form name | `web.fillOutForm.webFormName` |
| Web page query parameters | `web.webPageDetails.queryParameters` | 
| Web page ID | `web.webPageDetails.webPageID` | 
| User agent | `environment.browserDetails.userAgent` |
| Referrer URL | `web.webReferrer.URL` |

+++

### Web link clicked

The event signals that the Web SDK automatically recorded a link click.

Event type: `web.webinteraction.linkClicks`

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` | 
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Web interaction source ID | `web.webInteraction.webInteractionKey.sourceID` |
| Web interaction source type | `web.webInteraction.webInteractionKey.sourceType` | 
| Web interaction source instance ID | `web.webInteraction.webInteractionKey.sourceInstanceID`|
| Web interaction source key | `web.webInteraction.webInteractionKey.sourceKey` | 
| Web interaction link ID | `web.webInteraction.linkID` | 
| Web interaction link URL | `web.webInteraction.linkURL` |
| Web page query parameters | `web.webPageDetails.queryParameters` | 
| Web page ID | `web.webPageDetails.webPageID` | 
| User agent | `environment.browserDetails.userAgent` |
| Referrer URL | `web.webReferrer.URL` |

+++

### Interesting moment

This event tracks when an interesting moment was recorded for a person.

Event type: `leadOperation.interestingMoment `

+++Fields

| Field | Field type |
| ----- | ---------- |
| Identifier | `_id` |
| Event type | `eventType` |
| Timestamp  | `timestamp` | 
| Person ID  | `personID` |
| Person source ID | `personKey.sourceID` |
| Person source type | `personKey.sourceType` |
| Person source instance ID | `personKey.sourceInstanceID` |
| Person source Key | `personKey.sourceKey` |
| Moment date  | `leadOperation.interestingMoment.date` | 
| Moment description | `leadOperation.interestingMoment.description` |
| Moment source | `leadOperation.interestingMoment.source` |
| Moment type | `leadOperation.interestingMoment.type` |
| Journey ID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| Node ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

<!-- ## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3448637/?learn=on) -->