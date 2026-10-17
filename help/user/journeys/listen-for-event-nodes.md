---
title: Listen for an Event
description: Configure event nodes for account and people triggers - listen for buying group changes, email clicks, form fills, and Experience Platform events in Journey Optimizer B2B Edition.
feature: Account Journeys
role: User
exl-id: d852660b-f1da-4da0-86f0-85271f55b79f
autotag-review: 2026-03-30T23:08:46.228Z
TQID: 'https://experienceleague.adobe.com/f9N-ZeBXK-ON-gWtJHgFwvr9DCXRQyZRj9O7Jz9qeyo'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Listen for an event

To advance the audience to the next step in your [journey](./journeys-overview.md) when an event occurs, add the _Listen for an event_ node. Depending on the journey type, you can use this node to trigger the next node in the journey according to people or account events. 

<!--
![Video](../../assets/do-not-localize/icon-video.svg){width="30", vertical-align="middle"} [Watch the overview video](#overview-video)
-->

## Account journeys {#account-journeys}

>[!NOTE]
>
>For an account journey, you cannot add the _[!UICONTROL Listen for an event]_ node type on a split path by people.

1. Open the account journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Listen for an event]**.

   ![Add journey node to an account journey - Listen for an event](./assets/node-listen-event-account-journey.png){width="400"}

1. In the node properties on the right, use the _Event type_ selector to choose between **[!UICONTROL Accounts]** and **[!UICONTROL People]**.

1. Define the event trigger for the selected event type:

   * For the _Accounts_ event type, choose the [account event](#account-events) that you want to use for the trigger.

      ![Journey node - listen for events on account](./assets/node-listen-events-account.png){width="500" zoomable="yes"}

      Click **[!UICONTROL Edit event]** and define the matching criteria for the [account event](#account-events).

   * For the _People_ event type, click **[!UICONTROL Add event criteria]**.

      ![Journey node - listen for events on people](./assets/node-listen-events-people.png){width="500" zoomable="yes"}

      In the _Edit event_ dialog, drag and drop one or more [people events](#people-events) into the builder space and set the definition for each. Click **[!UICONTROL Add constraint]** for each constraint that you want to use to refine the event match.

      You can add multiple people events to match. The first qualifying event advances the account in the journey.

      ![Account journey node - Listen to events - People event type - edit event](./assets/node-listen-events-account-people-edit-event.png){width="700" zoomable="yes"}

      (Optional) Select the **[!UICONTROL Filters]** tab to [add filters for the event](#filters-people-event).

1. Click **[!UICONTROL Done]**.

   The event and filter definitions are displayed in the node properties.

   ![Account journey node - Listen to events - Events defined](./assets/node-listen-events-account-complete.png){width="500"}

### People events for account journeys {#people-events}

In an account journey, you can listen for an event based on people when you want to advance the account in the journey according to events triggered by person (lead) activity. You can also filter events according to event history and person attributes.

>[!TIP]
>
>Experience Events can occur _before_ people enter the journey (such as a prior email click or web interaction). To route people based on these events, use the [!UICONTROL Event history] filter in a [Split paths by people](./split-merge-paths-nodes.md#experience-event-history-filtering) node.

For detailed information about using Experience Events, see [Experience Event triggers](#experience-event-triggers).

#### Journey Optimizer B2B events {#events-account-people}

| Event | Constraints |
| ----- | ----------- |
| [!UICONTROL Lead Added to Buying Group] | Solution interest (required)<br/><br/>Additional constraints (optional): <li>Role</li><li>Date of activity</li>|
| [!UICONTROL Lead Removed from Buying Group] | Solution interest (required)<br/>Date of activity (optional) |
| [!UICONTROL Person profile changes] | Attribute (required)<br/>Date of activity (optional)<br/>New value (optional)<br/>Previous value (optional)<br/>Reason (optional)<br/>Source (optional) |

### Account events {#account-events}

In an account journey, you can listen for an event based on the account when you want to advance the account in the journey according to events triggered by account activity.

| Event | Constraints |
| ----- | ----------- |
| [!UICONTROL Account had interesting moment] | Type (Email, Milestone, or Web)<br/>Additional constraints (optional): <li>Description</li><li>Source</li><li>Date of activity</li> <br/>Timeout (optional) |
| [!UICONTROL Change in Account Data Value] | Attribute<br/>Additional constraints (optional): <li>New value</li><li>Previous value</li><li>Date of activity</li> <br/>Timeout (optional) |
| [!UICONTROL Change in Buying Group Stage] | Solution interest<br/>Additional constraints (optional): <li>New stage</li><li>Previous stage</li><li>Date of activity</li><br/> Timeout (optional) |
| [!UICONTROL Change in Buying Group Status] | Solution interest<br/>Additional constraints (optional): <li>New status</li><li>Previous status</li><li>Date of activity</li><br/> Timeout (optional) |
| [!UICONTROL Change in Completeness Score] | Solution interest<br/>Additional constraints (optional): <li>New score</li><li>Previous score</li><li>Date of activity</li><br/> Timeout (optional) |
| [!UICONTROL Change in Engagement Score] | Solution interest<br/>Additional constraints (optional): <li>New score</li><li>Previous score</li><li>Date of activity</li><br/> Timeout (optional) |

1. To match the event, set the required constraint.

1. For each optional constraint that you want to include for event match, click **[!UICONTROL Add constraint]** and select the field.

   ![Account journey - Listen for an account event](./assets/node-listen-events-account-edit-event.png){width="700" zoomable="yes"}
   
   Set the operator and value for the evaluation.

1. Click **[!UICONTROL Done]**.

<!--

Removed from AJO B2B people events 

| [!UICONTROL Clicks link in email] | Email<br/><br/>Additional constraints (optional): <li>Link</li><li>Link ID</li><li>Is mobile device</li><li>Device</li><li>Platform</li><li>Browser</li><li>Is predictive content</li><li>Is bot activity</li><li>Bot activity pattern</li><li>Browser</li><li>Date of activity</li><li>Min. number of times</li><br/>Timeout (optional) |
| [!UICONTROL Clicks link in SMS] | Email<br/><br/>Additional constraints (optional): <li>Link</li><li>Device</li><li>Platform</li><li>Date of activity</li><li>Min. number of times</li><br/>Timeout (optional) |
| [!UICONTROL Data value changes] | Person attribute<br/><br/>Additional constraints (optional): <li>New value</li><li>Previous value</li><li>Reason</li><li>Source</li><li>Date of activity</li><li>Min. number of times</li><br/>Timeout (optional) |
| [!UICONTROL Opens email] | Email<br/><br/>Additional constraints (optional): <li>Link</li><li>Link ID</li><li>Is mobile device</li><li>Device</li><li>Platform</li><li>Browser</li><li>Is predictive content</li><li>Is bot activity</li><li>Bot activity pattern</li><li>Browser</li><li>Date of activity</li><li>Min. number of times</li><br/>Timeout (optional) |
| [!UICONTROL Score is changed] | Score name<br/><br/>Additional constraints (optional):<li>Change</li><li>New score</li><li>Urgency</li><li>Priority</li><li>Relative score</li><li>Relative urgency</li><li>Date of activity</li><li>Min. number of times</li><br/>Timeout (optional) |
| [!UICONTROL SMS Bounces]| SMS message<br/><br/>Additional constraints (optional): <li>Date of activity</li><li>Min number of times</li><br/>Timeout (optional) |


### Listen for a Marketo Engage event {#listen-for-marketo-engage-event}

| Marketo Engage | [!UICONTROL Visits Web Page] | Web page <br/> Select one or more Marketo Engage pages to match. <br/><br/>Additional constraints (optional): <li>Querystring</li><li>Client IP address</li><li>Referrer</li><li>User Agent</li><li>Search engine</li><li>Search query</li><li>Token</li><li>Browser</li><li>Platform</li><li>Device</li><li>Date of activity</li> |
| | [!UICONTROL Fills out form] | Form <br/> Select one or more Marketo Engage forms to match. <br/><br/>Additional constraints (optional): <li>Date of activity</li><li>Querystring</li><li>Client IP address</li><li>Referrer</li><li>User agent</li><li>Platform</li><li>Device</li><br/>Timeout (optional) |
| Adobe Experience Platform | [!UICONTROL Event definition] | Event type <br/><br/>Additional constraints (optional): <li>Fields</li> <br/>Additional constraints (not supported): <li>Date of activity</li><li>Min. number of times</li><br/> Timeout (optional) |

If you have web pages in your connected Marketo Engage instance, you can trigger an event based on a visit/no visit to these web pages, as well as Marketo Engage forms that were/were not filled. 

1. Use the **[!UICONTROL Select people event]** selector and scroll the menu to the **[!UICONTROL Marketo Engage]** section.

1. Select a Marketo Engage activity type:

   * **[!UICONTROL Visits Web Page]**.
   * **[!UICONTROL Fills Out Form]**

   ![Listen for an experience event](./assets/node-listen-events-people-me-event.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Edit event]** and define one or more web pages to match and any additional constraints for the event.

   * (Required) In the _[!UICONTROL Edit event]_ dialog, define the **[!UICONTROL Web page]** or **[!UICONTROL Fills out form]** constraint. Use **[!UICONTROL is]** (default) to match on one or more selected pages or forms. Use **[!UICONTROL is not]** to match on all page visits/forms with the exclusion of one or more selected pages/forms. Or, use the **[!UICONTROL is any]** operator to match on any Marketo Engage web page visit or filled form.

   * (Optional) Click **[!UICONTROL Add constraint]** and choose the field that you want to use for the constraint. Set the operator and the value for the field.

     ![Listen for an experience event](./assets/node-listen-events-people-me-event-edit-dialog.png){width="700" zoomable="yes"}

     To include additional field constraints as needed, repeat this action.

   * If needed, select the **[!UICONTROL Filters]** tab to [add filters for the event](#add-a-filter-to-the-people-event).

   * When the constraints and filters are defined, click **[!UICONTROL Done]**.

1. If needed, set the **[!UICONTROL Timeout]** option to limit the time period to listen for the event (see [Add a timeout to an event node](#add-a-timeout-to-an-event-node)). 

1. In the journey canvas, add the next node to execute when the event occurs.

-->

## Person journeys {#person-journeys}

1. Open the person journey canvas.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Listen for an event]**.

   ![Add journey node to a person journey - Listen for an event](./assets/node-listen-event-person-journey.png){width="350"}

1. In the node properties on the right, click **[!UICONTROL Add event criteria]**. 

   ![Journey node - Listen to events properties - add event criteria](./assets/node-listen-events-person-journey.png){width="450"}

1. Add an event and set the constraints that you want to match for the trigger.

   You can use [Experience Events](#experience-event-triggers) and [Person profile changes](#person-profile-changes) to define the event trigger.

   Drag and drop the event trigger into the builder space and set the definition. Click **[!UICONTROL Add constraint]** for each constraint that you want to use to refine the event match.

   You can add multiple events to match. The first qualifying event advances the person profile in the journey.
   
1. (Optional) Select the **[!UICONTROL Filters]** tab to [add filters for the event](#filters-people-event).

1. Click **[!UICONTROL Done]**.

   The event and filter definitions are displayed in the node properties.

   ![Journey node - Listen to events - Event and filters](./assets/node-listen-events-person-complete.png){width="450"}

### Person profile changes {#person-profile-changes}

For person journeys, you can use a change in B2B person profile attributes to trigger the _Listen for an event_ node.

1. Drag and drop **[!UICONTROL Person profile change]**s from the _[!UICONTROL Triggers]_ list into the event matching builder space.

1. Click **[!UICONTROL Add constraint]** and select the attribute change that you want to use for the event trigger. 

   Set the field value according to the change that you want to match.

   ![Person journey - Listen for a person profile change event](./assets/node-listen-event-person-edit-event.png){width="700" zoomable="yes"}

1. (Optional) Add another _Person profile change_ attribute that you want to use as an event trigger, or an [Experience Event](#experience-event-triggers).

   When you add multiple events to match, the first qualifying event advances the person profile forward in the journey.

1. (Optional) Select the **[!UICONTROL Filters]** tab to [add filters for the event](#filters-people-event).

1. Click **[!UICONTROL Done]**.

## Experience Event triggers {#experience-event-triggers}

Experience Events are available for person journeys or when you use the _People_ event type in account journeys. Use the _[!UICONTROL Edit event]_ dialog to add one or more Experience Events for triggering the _Listen for an event_ node.

>[!PREREQUISITES]
>
>Administrators configure [Adobe Experience Platform (AEP) Experience Events](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent){target="_blank"}, which enable marketers to create account and person journeys that react to the events in near real-time.
>
>To make Experience Events available for journeys, a product administrator must first [add the event types and fields of interest](../admin/configure-aep-events.md#add-an-event) in [!DNL Journey Optimizer B2B Edition].

1. Expand **[!UICONTROL Sapphire AEP events]** in the _[!UICONTROL Triggers]_ list on the left.

1. Drag and drop the Experience Event into the event matching builder space.

   You can use the _Search_ field to filter for a keyword in the event name, such as `email`.

1. Click **[!UICONTROL Add constraint]** and choose the field that you want to use to refine the event match.

   The available constraints are defined as managed fields for the event configuration.
  
   ![Edit event dialog for an Experience Event in a person journey](./assets/node-listen-events-person-journey-edit-event-aep-event.png){width="700" zoomable="yes"}

1. To match the event field, set the operator and values.

1. (Optional) Add another event.

   You can use multiple Experience Events for triggering the node.

   For a person journey you can also add [person profile changes](#person-profile-changes). For an account journey (people event type), you can also add [Journey Optimizer B2B events](#events-account-people).

   When you add multiple events to match, the first qualifying event advances the person profile forward in the journey.

1. (Optional) Select the **[!UICONTROL Filters]** tab to [add filters for the event](#filters-people-event).

1. Click **[!UICONTROL Done]**.

## Filters for events {#filters-people-event}

When you define a [people event in an account journey](#people-events) or an [event in a person journey](#person-journeys), you can include filtering to limit matching event triggers based on various criteria:

| Filters | Description |
| ------------ | ----------- |
| [!UICONTROL Event history] | Experience events configured by an administrator. See _[Select Experience Events and fields](../admin/configure-aep-events.md)_. |
| [!UICONTROL Person Attributes] | Attributes from the B2B person profile, including: <li>City <li>Country <li>Date of birth <li>Email address <li>Email invalid <li>Email suspended <li>First name <li>Inferred state region<li>Job title <li>Last name <li>Mobile phone number <li>Person engagement score <li>Phone number <li>Postal code <li>State <li>Unsubscribed <li>Unsubscribed reason |
| [!UICONTROL Person attributes] | (Person journeys only) Attribute value |
| [!UICONTROL Special filters] > [!UICONTROL Member of Buying Group] | The person is or is not a buying group member evaluated against one or more of the following criteria: <li>Solution Interest</li><li>Buying Group status</li><li>Completeness Score</li><li>Engagement Score</li><li>Is Removed (default: `false`)</li><li>Role</li> (See [Membership filtering](#membership-filtering)) |
| [!UICONTROL Special filters] > [!UICONTROL Member of Profile Audience] | The person is or is not a member of one or more [!DNL Adobe Experience Platform] profile audiences. (See [Membership filtering](#membership-filtering)) |

<!--
| [!UICONTROL Special filters] > [!UICONTROL Member of List] | The person is or is not a member of one or more Marketo Engage lists. |
| [!UICONTROL Special filters] > [!UICONTROL Member of Program] | The person is or is not a member of one or more Marketo Engage programs. |
-->

1. After you define the event trigger, select the **[!UICONTROL Filters]** tab in the _[!UICONTROL Edit event]_ dialog.

   ![Listen for Event node by people - Select Filters tab for editing the event](./assets/node-listen-event-people-edit-event-filters.png){width="700" zoomable="yes"}

1. To filter matches for the event, add one or more filter criteria.

   * Drag and drop any of the filters from the left navigation and complete the match definition.

      >[!NOTE]
      >
      >If you have custom person fields defined in the account audience schema in Experience Platform, these fields are also available under **[!UICONTROL Attributes]** to use as person attributes in filters. 

   * Refine your filtering by applying the **[!UICONTROL Filter logic]** at the top. You can choose to match all filters or any filter.

      ![Person filters used in an event definition](./assets/node-listen-events-filter-logic.png){width="600" zoomable="yes"}

1. When the event and filter definitions are complete, click **[!UICONTROL Done]**.

### Membership filtering {#membership-filtering}

Within the _[!UICONTROL Special filters]_ section, use the following filters to match an event based on a person's membership:

* _[!UICONTROL Member of Buying Group]_ - Evaluates whether the person is a member of a buying group.
* _[!UICONTROL Member of Profile Audience]_ - Evaluates whether the person is a member of an [!DNL Adobe Experience Platform] profile audience.

To add a membership filter, drag it from the _[!UICONTROL Special filters]_ folder onto the filters workspace and set the membership to _true_ to include members or _false_ to exclude them. You can combine both filters in the same event definition and use the **[!UICONTROL Filter logic]** to match any or all of them.

These filters are also available in [split path by people conditions](./split-merge-paths-nodes.md#membership-filtering).

![Listen for event node - membership filters](./assets/node-listen-event-people-membership-filters.png){width="700" zoomable="yes"}

**Member of Buying Group**

To match an event for buying group members with a specific role, set membership to _true_ and select a _[!UICONTROL Solution interest]_ associated with one or more buying groups.

When you add the filter, the system includes the _[!UICONTROL Is Removed]_ constraint by default and sets it to `false`, so the filter matches only current buying group members.

Click **[!UICONTROL Add constraint]** to include additional buying group membership constraints:

* _[!UICONTROL Buying group stage]_
* _[!UICONTROL Buying group status]_
* _[!UICONTROL Completeness score]_
* _[!UICONTROL Engagement score]_
* _[!UICONTROL Role]_

>[!IMPORTANT]
>
>The _[!UICONTROL Is Removed]_ constraint determines whether removed buying group members are evaluated:
>
>* `false` (default) - Returns only current buying group members. Removed members are not included.
>* `true` - Returns only removed buying group members. Current members are not included.
>* Constraint removed - Returns both current and removed buying group members.
>
>If you remove the constraint, the filter can match people who are no longer in the buying group.

**Member of Profile Audience**

Use the _[!UICONTROL Profile Audience]_ constraint to select one or more audiences. For example, if you select the `integroPerson` audience, the event matches only people who were members of that audience when the last batch ingestion occurred.

>[!NOTE]
>
>The filter does not calculate audience membership in real time. It qualifies people based on their membership in the selected audience as of the last batch audience ingestion. Only audiences that have been ingested into [!DNL Journey Optimizer B2B Edition] can be evaluated.

## Add a timeout to an event node {#timeouts}

If needed, define the amount of time the journey waits for the event. The journey ends after a timeout unless you define a timeout path, where you can add other nodes.

Enable the **[!UICONTROL Timeout]** option in the node properties to specify a timeout for the _Listen for an event_ node.

1. With the option enabled, choose the _Type_ and specify the parameters for the timeout:

   * **[!UICONTROL Duration]** - Use this type to specify a time period for the event trigger. If the event does not trigger within that period, the person or account does not proceed in the journey.

      Select the duration for which the journey waits for an event to occur before it times out. Specify the number of minutes, hours, days, weeks, or months.

      ![Listen for event node - Timeout duration](./assets/node-listen-events-timeout-duration.png){width="500" zoomable="yes"}

      If you want the time period to end on a specific day of the week, enable the **[!UICONTROL Must end on]** option. **[!UICONTROL Any day]** is selected by default, with all of the days selected. Clear the checkbox and then select one or more days for an ending date. Then select the **Time** and **[!UICONTROL Time zone]**.

      ![Listen for event node - Timeout duration - Must end on](./assets/node-listen-events-timeout-duration-must-end-on.png){width="300"}
   
   * **[!UICONTROL Date]** - Use this type to set an expiration date for the node. If the event does not trigger by the specified date/time, the person or account does not proceed in the journey.

      Click the _Calendar_ icon to set the date and time for the timeout.

      ![Listen for event node - Timeout date](./assets/node-listen-events-timeout-date.png){width="500" zoomable="yes"}

1. Define the timeout path.

    The system selects the **[!UICONTROL Set timeout path]** option by default. You can use this path to define what happens if the _Listen for an event_ node times out. You can add alternative actions and events that apply to person profiles when the event does not occur.

   ![Journey event node - set timeout path](./assets/node-event-timeout-set-path.png){width="600" zoomable="yes"}

   If you do not want to define the path, you can clear the _[!UICONTROL Set timeout path]_ check box.

<!--
 ## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3443219/?learn=on) 
-->
