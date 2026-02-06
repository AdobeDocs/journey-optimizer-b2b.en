---
title: Person Audience Nodes
description: Configure person audience nodes with segment or event-based audiences to define person journey entry points for targeted orchestration in Journey Optimizer B2B Edition.
feature: Audiences
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
exl-id: 8d4785cd-87f0-4548-9aba-fa18165b0f45
---
# Person audience journey nodes

The _person audience_ node specifies which person profiles enter the journey. When you [create a person journey](./create-publish-journey.md#create-a-journey), the journey always starts with a person audience node that defines its input. The person audience node can have one of two audience input types: CDP segments or event-based membership. Segment and event-based audience definitions cannot be combined.

Use one of the following input options for the person audience journey node:

* **Profile audience** - Use segment audiences defined in a CDP. All profiles qualifying for the audience are added as members to the journey. Newly qualifying profiles for the segment are added to the journey during the daily [profile ingestion](#profile-ingestion) tasks. If a profile no longer qualifies for the segment, it is **_not_** removed from the journey.

* **Event audience** - Use qualifying events to define the audience. These events are defined in the node configuration and must use [XDM events configured in the administration settings](../admin/configure-aep-events.md). Up to 10 events are supported for event-based audience membership. A profile qualifies immediately for the journey after the first matching event that their profile takes.

   >[!NOTE]
   >
   >Events cannot be combined with profile attributes to narrow down audience definitions. Improvements to address this limitation are planned for future releases.

## Profile ingestion

In Journey Optimizer B2B Edition, a nightly audience ingestion task keeps profiles in sync with Experience Platform. While event-based person journeys can qualify profiles that are not part of a profile or account audience that is ingested/in-use by Journey Optimizer B2B Edition, it results in ingested profiles that remain stale unless they are part of an audience that is used by a person journey, account journey, or buying group. If a profile is ingested and later added to an audience, profile stitching is performed and the profile stays in sync with Experience Platform. Improvements to this profile data synchronization are planned for future releases.

A newly created profile ingested by an event-based person journey may not have the updated profile information at the time of ingestion. For example, if a profile is created through a form fill event, and a person journey ingests them from the qualifying form fill event, the data submitted in the form may not yet be synced to the profile when the journey ingested it. The result could be incomplete data for personalization (such as in email content). Improvements to this profile event data synchronization are planned for future releases.

Event-based person journeys can qualify profiles that are still anonymous/without email addresses and only containing ECIDs. It happens most commonly when you have qualification logic for web page activity. Overly broad event based audience logic could result in the instance hitting the 40 million profile cap if too many profiles qualify. Limit the possible scope of your audience to prevent this scenario.

>[!IMPORTANT]
>
>During the current beta program, the ideal use of person journeys is to qualify only profiles that you are also targeting in account journeys and buying group definitions. This usage ensures a full profile that stays in sync with Experience Platform.

## Set the audience for the person audience node

1. Click the **[!UICONTROL Person audience]** node.

   This action displays the node properties on the right.

   ![Person audience journey node](./assets/person-journey-person-audience-node.png){width="700" zoomable="yes"}

1. Choose the input type for people entering the journey:

   * **[!UICONTROL Profile audience]**

     Choose the _[!UICONTROL Profile audience]_ option. Then, click **[!UICONTROL Add profile audience]**.

     In the _[!UICONTROL Add audience]_ dialog, select a previously created audience segment. Then, click **[!UICONTROL Add audience]**.

     ![Select a profile audience for the node](./assets/node-person-audience-add-audience-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL Event audience]**

     Choose the _[!UICONTROL Event audience]_ option. Then, click **[!UICONTROL Add event criteria]**.

     In the _[!UICONTROL Edit event criteria]_ dialog, add one or more events that you want to use for audience member qualification. For each event that you add, click **[!UICONTROL Add constraint]** to choose an event attribute for a match. Set the evaluation that you want to use for a match. You can add multiple constraints to match the event.

     ![Add events and match criteria for qualifying a person profile](./assets/node-person-audience-edit-event-criteria-dialog.png){width="700" zoomable="yes"}

     When the event criteria are defined, click **[!UICONTROL Save]**.

     For more information about configuration for journey-supported events, see [Manage Experience Events](../admin/configure-aep-events.md#manage-experience-events).
