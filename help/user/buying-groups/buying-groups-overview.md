---
title: Buying Groups
description: Learn how buying groups in Journey Optimizer B2B Edition can increase marketing effectiveness by identifying and targeting members for your account lists.
feature: Buying Groups
role: User
exl-id: ddcd7b62-6a76-4f5e-b6d3-a20944ca8332
---

# Buying groups

For B2B sales and marketing activities, accounts are key to any strategy. Each account has a group of people associated with it, and these people may be employees of the account or contractors who work with the account. Accounts are hierarchical, and different products might be sold at different levels in the hierarchy. For example, Adobe Experience Platform might be sold at the corporate level to a top-level account. And Adobe Photoshop might be sold to an account that represents a division or department within an organization, such as a design department within a larger corporation.

![Account roles diagram](assets/account-roles-diagram.png){width="800"}

Within the account, there could be a subset of people who comprise the _buying group_. These people ultimately make the purchase decision, so they need special attention from the marketer and might need different information delivered to them than the other people associated with the account. Buying groups may comprise a different group of people for different product lines or offerings. For example, a cybersecurity product might typically require a Chief Information Officer or Chief Security Officer, and a representative from the Legal department to approve a purchase. A bug tracking product might typically have a VP of Engineering and an IT Director as members of the buying group.

![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the video overview](#overview-video)

## Key components

You can increase marketing effectiveness by establishing buying groups in Journey Optimizer B2B Edition that identify members for your target account lists based on the solutions that your Sales teams are responsible for selling. Before you and your Marketing team starts creating your buying groups, make sure that you have the key components defined. These components are critical for meeting your business goals and objectives.

| Component | Purpose |
| --------- | ------- |
| Solution interest | This component provides the answer to: <ul><li>As a marketing organization, what are you selling?</li><li>What product or collection of products are you targeting to sell?</li></ul>  **_Example:_** Cross-selling new Product X to existing customers|
| Account audience | This component provides the answer to: <ul><li>To whom are you selling?</li><li>What is the list of accounts that you are targeting?</li></ul> **_Example:_** Account segment defined by accounts with Product Y that have revenue over 1M|
| Buying group role templates |  This component provides the answer to: <ul><li>What roles are you targeting?</li><li>What set of rules are used to determine who is assigned to buying group roles?</li></ul>  **_Example:_** Assign a person with CMO title to the Decision Maker role |
| Buying group stages | (Optional) This component provides the answer to: How is the buying group tracking towards success or failure? |

## Member assignment

There are three ways that members are assigned to or removed from a buying group. The following list describes these addition and removal methods in the order of precedence. The top-most method takes the highest precedence and a lower one cannot override it.

1. **_Manual action_** - A manual add member or remove member action performed by a sales user for the buying group
2. **_Journey action_** - Journey [action nodes for buying group membership](../journeys/action-nodes.md#add-a-people-based-action) (_Assign to Buying group_ or _Remove from Buying group_)
3. **_System jobs_** - Buying group [creation](../buying-groups/buying-groups-create.md#buying-group-creation-jobs) and maintenance jobs. 

To ensure that the member assignment in a buying group is not overridden incorrectly, this list is in the order of precedence followed in the system to ensure accurate member assignment. For example, when a sales user manually adds a member to the buying group, they do not want a maintenance job to alter that addition. Using the precedence order, the following scenarios are enforced:

* If a user manually assigns a member to a buying group, and this is followed by a buying group maintenance job that removes the same member from the buying group, the maintenance job **does not remove** that member and cannot override the manual assignment.
* If a user manually assigns a member to a buying group, and this is followed by a triggered journey node that removes the same member from the buying group, the node action **does not remove** that member and cannot override the manual assignment.
* If a triggered journey action node adds a member to a buying group, and this is followed by a buying group maintenance job that removes the same member from the buying group, the maintenance job **does not remove** that member and cannot override the journey action assignment.

## Buying group workflow

1. Create buying groups.

   * Define [solution interest](./solution-interests.md) and [role template](./buying-groups-role-templates.md)
   * [Create the buying group](./buying-groups-create.md#create-buying-groups) and assign [buying group stages](./buying-group-stages.md).

1. Identify missing people by completeness.

   Analyze the buying group using filters.
   
   **_Example:_** Decision Maker role is missing and the completeness score is < 50

1. Complete the buying groups definitions.
<!--
   * Acquire missing people
   * Send to LinkedIn Destination
   * Enrich with Zoominfo -->

1. Add buying group actions to your account journeys.

## View buying groups and components

On the left navigation, expand **[!UICONTROL Accounts]** and click **[!UICONTROL Buying groups]**.

The _[!UICONTROL Buying groups]_ page is organized as tabs:

| Tab | Description |
| --- | ----------- |
| [!UICONTROL Overview] | This tab is the default and displays the [Buying groups dashboard](../dashboards/buying-groups-dashboard.md). |
| [!UICONTROL Browse] | This tab supports the following activities: <ul><li>View the list of existing buying groups. </li><li>Search by the buying group name. </li><li>Filter by solution interest. </li><li>Drill in to buying group details. </li><li>Create a buying group. </li></ul> |
| [!UICONTROL Solution interests] | This tab supports the following activities: <ul><li>View the list of existing buying groups. </li><li>Search by the buying group name. </li><li>Access and edit solution interest properties. </li><li>Create a solution interest. </li><li>Delete a solution interest. </li><li>View and delete buying group jobs. </li></ul>|
| [!UICONTROL Roles Templates] | This tab supports the following activities: <ul><li>View the list of existing roles templates. </li><li>Search by roles template name. </li><li>Access and edit roles template properties and conditions. </li><li>Create a roles template. </li><li>Delete a roles template. </li></ul>|
| [!UICONTROL Stages] | This tab supports the following activities: <ul><li>View the existing buying groups stages model. </li><li>Access and edit the draft buying group stages model. </li><li>Create the buying group stages model. </li></ul> |

## Buying group search and filter

Use the _[!UICONTROL Browse]_ tab to view the list of buying groups. You can search by name and filter the list by solution interest.

![Buying group browse page](assets/buying-groups-browse.png){width="800" zoomable="yes"}

## Buying group details

To access details for a buying group, click the buying group name from the _[!UICONTROL Browse]_ tab. [Learn more](./buying-group-details.md)

![Buying group details](assets/buying-group-details.png){width="600" zoomable="yes"}

### Buying group completeness score

The completeness score is used to determine if the buying group is complete, which means that it has the right members assigned to the roles and is ready to be used in an account journey. This score is a percentage based on the number of roles within the buying group and how many roles are assigned with at least one lead.

For example, if there are four roles within a buying group and three out of the four roles are assigned to at least one lead, the buying group is 75% complete. 

The buying group completeness score is re-calculated every time a buying group is created or updated.

### Buying group engagement score

Buying group engagement score is a number to determine the engagement of the members of a buying group, based on the activities they perform. 

* The engagement score calculation starts as soon as the buying group is generated.
* Any inbound activity performed by the members of the buying group in the last 30 days is used to calculate the score. 
* With the 30-day window and as activities expire, the score could go down.
* There is a daily frequency cap of 20 for each activity. If a member of a buying group performs the same activity more than 20 times a day, the count of the activity is capped at 20 and not a higher number.
* The displayed score is rounded. For example, a score of 75.89999 is displayed as 76.

+++Activities used for scoring

>[!BEGINSHADEBOX]

| Activity name | Description | Engagement type | Max daily frequency count | Activity weight |
| --- | --- | --- | --- | --- |
| [!UICONTROL Visit Webpage]| A member visits a web page | Web | 20 | 40 |
| [!UICONTROL Fill Out Form]| A member fills and submits a form on a web page | Web | 20 | 40 |
| [!UICONTROL Click Link] | A member clicks a link on a web page | Web | 20 | 40 |
| [!UICONTROL Open Email] | A member opens an email | Email | 20 | 30 |
| [!UICONTROL Click Email] | A member clicks a link in an email | Email | 20 | 30 |
| [!UICONTROL Open Sales Email] | A member opens a sales email | Email | 20 | 30 |
| [!UICONTROL Click Sales Email] | A member clicks a link in a sales email | Email | 20 | 30 |
| [!UICONTROL Interesting Moment] | A member has an interesting moment | Curated | 20 | 60 |
| [!UICONTROL Tap Push Notification] | A member receives a push notification | Mobile | 20 | 30 |
| [!UICONTROL Mobile App Activity] | A member performs an activity on a mobile app | Mobile | 20 | 30 |
| [!UICONTROL Mobile App Session] | A member is active on a mobile app session | Mobile | 20 | 30 |
| [!UICONTROL Fill Out Facebook Lead Ads Form] | A member fills and submits a Lead Ads form on a Facebook page | Social | 20 | 30 |
| [!UICONTROL Click RTP Call to Action] | A member clicks a personalized call to action | Web | 20 | 60 |
| [!UICONTROL View In-App Message] | A member views an in-app message | Mobile | 20 | 30 |
| [!UICONTROL Tap In-App Message] | A member taps an in-app message | Mobile | 20 | 30 |
| [!UICONTROL Subscribe SMS] | A member subscribes to SMS communications | SMS | 20 | 90 |
| [!UICONTROL Reply to Sales Email] | A member replies to a sales email | Email | 20 | 30 |
| [!UICONTROL Engaged with a Dialogue] | A member engages with a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Interacted with Document in Dialogue] | A member interacts with a document in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Scheduled Meeting in Dialogue] | A member schedules an appointment in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Reached Dialogue Goal] | A member reaches a goal in a Dynamic Chat dialogue |  |20 | 90 |
| [!UICONTROL Responded to a poll in webinar] | A member responds to a poll in a webinar event | Chat | 20 | 90 |
| [!UICONTROL Call to action clicked in webinar] | A member clicks a call-to-action link in a webinar event | Call | 20 | 30 |
| [!UICONTROL Asset downloads in webinar] | A member downloads a file/asset in a webinar event | Event | 20 | 60 |
| [!UICONTROL Asks questions in webinar] | A member asks questions in a webinar event | Event | 20 | 60 |
| [!UICONTROL Has attended event] | A member attended an event | Event | 20 | 60 |
| [!UICONTROL Engaged with an Agent in Dialogue] | A member engages with an agent in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Clicked Link in Chat in Dialogue] | A member clicks a link in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Engaged with a Conversational Flow] | A member engages with a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Scheduled Meeting in Conversational Flow] | A member schedules an appointment in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Reached Conversational Flow Goal] | A member reaches a goal in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Interacted with Document in Conversational Flow] | A member interacts with a document in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Engaged with an Agent in Conversational Flow] | A member engages with an Agent in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Clicked Link in Chat in Conversational Flow] | A member clicks a link in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Click Link in SMS V2] | A member clicks a link in an SMS message | SMS | 20 | 90 |


>[!ENDSHADEBOX]

>[!NOTE]
>
>Engagement score activities are recorded in the Marketo Engage [activity log for a person](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/managing-people-in-smart-lists/locate-the-activity-log-for-a-person){target="_blank"}.

+++

#### Weighting

Users can assign _weighting_ to each role in the roles template to allocate different weights for a role to calculate the engagement score.

![Set weighting to each role in the roles template](./assets/roles-templates-weighting.png){width="700" zoomable="yes"}

Each weighting level translates to a value, which is used for calculating the engagement score:

* [!UICONTROL Trivial] = 20
* [!UICONTROL Minor] = 40
* [!UICONTROL Normal] = 60
* [!UICONTROL Important] = 80
* [!UICONTROL Vital] = 100

A roles template with three roles weighted as _[!UICONTROL Vital]_, _[!UICONTROL Important]_, and _[!UICONTROL Normal]_ convert to the following weighted percentages:

|Role           |Weighting |System value | Value calculation |Percentage |
|-------------- |--------- |------------- |------------------ |---------- |
|               |          |              |                   |           |
|Decision Maker |Vital     |100           |100/240            |41.67%     |
|Influencer     |Important |80            |80/240             |33.33%     |
|Practitioner   |Normal    |60            |60/240             |25%        |
|               |Total     |240           |                   |           |

#### Calculation example

The following example illustrates the engagement score calculation using the outlined role weight percentage, count of inbound activities for each member of the buying group, and a daily cap of 20 count for each event (if it has occurred multiple times).

|Role           |Member    |Activity type|Yesterday's count|Today's count|Calculation|Total score|
|-------------- |--------- |-------------|-----------------|-------------|------|-----------|
|               |          |             |                 |             |      |           |
|Decision Maker |Adam      |Visited website|37               |15         |20 + 15|35        |
|               |          |Clicked email|1                |1            |1 + 1 |2          |
|               |          |             |                 |             |      |           |
|               |Mark      |Visited website|5                |3          |5 + 3 |8          |
|               |          |Clicked email|1                |1            |1 + 1 |2          |
|               |          |Downloaded pub|3                |2           |3 + 2 |5          |
|**Decision Makers total score**|         |             |                 |             |      |**52**         |
|               |          |             |                 |             |      |           |
|Influencer     |John      |Visited website|19               |9            |19 + 9|28         |
|**Influencers total score**|         |             |                 |             |      |**28**         |
|               |          |             |                 |             |      |           |
|Practitioner   |Bob       |Clicked email|1                |1            |1 + 1 |2          |
|               |          |             |                 |             |      |           |
|               |Paul      |Clicked email|1                |1            |1 + 1 |2          |
|               |          |             |                 |             |      |           |
|               |Calvin    |Clicked email|1                |1            |1 + 1 |2          |
|               |          |Visited website|1              |7            |1 + 7 |8          |
|               |          |Downloaded pub|1               |2            |1 + 2 |3          |
|**Practitioners total score**|         |             |                 |             |      |**17**         |

The final engagement score is calculated by applying the weighting for each of the role scores:

|Role           |Role total score |Role weight % |Score X weight % |
|-------------- |---------------- |------------- |---------------- |
|Decision Makers |52               |41.67%        |21.67            |
|Influencers     |28               |33.33%        |9.33             |
|Practitioners   |17               |25%           |4.25             |
|**Final engagement score**|                |             |**35.25**           |

## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3433078/?learn=on)
