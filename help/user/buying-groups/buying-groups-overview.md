---
title: Buying Groups
description: Learn how buying groups in Journey Optimizer B2B Edition can increase marketing effectiveness by identifying and targeting members for your account lists.
feature: Buying Groups
exl-id: ddcd7b62-6a76-4f5e-b6d3-a20944ca8332
---

# Buying groups

For B2B sales and marketing activities, accounts are key to any strategy. Each account has a group of people associated with it, and these people may be employees of the account or contractors who work with the account. Accounts are hierarchical, and different products might be sold at different levels in the hierarchy. For example, Adobe Experience Platform might be sold at the corporate level to a top-level account, while Adobe Photoshop might be sold to an account that represents a division or department within an organization, such as a design department within a larger corporation.

![Account roles diagram](assets/account-roles-diagram.png){width="800"}

Within the account, there could be a subset of people who comprise the _buying group_. These are the people that ultimately make the purchase decision, so they need special attention from the marketer and might need different information delivered to them than the other people associated with the account. Buying groups may comprise a different group of people for different product lines or offerings. For example, a cybersecurity product might typically require a Chief Information Officer or Chief Security Officer, and a representative from the Legal department to approve a purchase, but a bug tracking product might typically have a VP of Engineering and an IT Director as members of the buying group.

![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the video overview](#overview-video)

## Key components

You can increase marketing effectiveness by establishing buying groups in Journey Optimizer B2B Edition that identify missing members for your target account lists based on the solutions that your Sales teams are responsible for selling. Before you and your Marketing team start creating your buying groups, make sure that you have the key components defined. These components are critical for meeting your business goals and objectives.

| Component | Purpose |
| --------- | ------- |
| Solution interest | This component provides the answer to: <ul><li>As a marketing organization, what are you selling?</li><li>What product or collection of products are you targeting to sell?</li></ul>  **_Example:_** Cross-selling new Product X to existing customers|
| Account audience | This component provides the answer to: <ul><li>To whom are you selling?</li><li>What is the list of accounts that you are targeting?</li></ul> **_Example:_** Account segment defined by accounts with Product Y that have revenue over 1M|
| Buying group role templates |  This component provides the answer to: <ul><li>What roles are you targeting?</li><li>What set of rules are used to determine who is assigned to buying group roles?</li></ul>  **_Example:_** Assign a person with CMO title to the Decision Maker role |
| Buying group stages | (Optional) This component provides the answer to: How is the buying group tracking towards success or failure? |

## Buying group workflow

1. Create buying groups.

   Options:
   * Use [solution interest](./solution-interests.md) and [role template](./buying-groups-role-templates.md)
   * Use third-party import
   * Generate from AI/ML

1. Identify missing people.

   Analyze the buying group using filters.
   
   **_Example:_** Decision Maker role is missing and the completeness score is < 50

1. Complete the buying groups definitions.
<!--
   * Acquire missing people
   * Send to LinkedIn Destination
   * Enrich with Zoominfo -->

1. Use in an account journey through the associated solution interest.

## View buying groups and components

On the left navigation, expand **[!UICONTROL Accounts]** and click **[!UICONTROL Buying groups]**.

The _[!UICONTROL Buying groups]_ page is organized as tabs:

| Tab | Description |
| --- | ----------- |
| [!UICONTROL Overview] | This tab is the default and displays the [Buying groups dashboard](../dashboards/buying-groups-dashboard.md). |
| [!UICONTROL Browse] | This tab supports the following activities: <ul><li>View the list of existing buying groups. </li><li>Search by buying group name. </li><li>Filter by solution interest. </li><li>Drill in to buying group details. </li><li>Create a buying group. Delete a buying group.</li></ul> |
| [!UICONTROL Solution interests] | This tab supports the following activities: <ul><li>View the list of existing buying groups. </li><li>Search by buying group name. </li><li>Access and edit solution interest properties. </li><li>Create a solution interest. </li><li>Delete a solution interest. </li><li>View and delete buying group jobs. </li></ul>|
| [!UICONTROL Roles Templates] | This tab supports the following activities: <ul><li>View the list of existing roles templates. </li><li>Search by roles template name. </li><li>Access and edit roles template properties and conditions. </li><li>Create a roles template. </li><li>Delete a roles template. </li></ul>|
| [!UICONTROL Stages] | This tab supports the following activities: <ul><li>View the existing buying groups stages model. </li><li>Access and edit the draft buying group stages model. </li><li>Create the buying group stages model. </li></ul> |

## Buying group search and filter

Use the _[!UICONTROL Browse]_ tab to view the list of buying groups. You can search by name and filter the list by solution interest.

![Buying group browse page](assets/buying-groups-browse.png){width="800" zoomable="yes"}

## Buying group details

To access details for a buying group, click the buying group name from the _[!UICONTROL Browse]_ tab.

![Buying group details](assets/buying-group-details.png){width="600" zoomable="yes"}

### Buying group completeness score

The completeness score is used to determine if the buying group is complete, which means that it has the right members assigned to the roles and is ready to be used in an account journey. This score is a percentage based on the number of roles within the buying group and how many roles are assigned with at least one lead.

For example, if there are four roles within a buying group and three out of the four roles are assigned to at least one lead, the buying group is 75% complete. 

The buying group completeness score is re-calculated every time a buying group is created or updated.

### Buying group engagement score

Buying group engagement score is a number to determine the engagement of the members of a buying group, based on the activities they perform. Any inbound activity performed by the members of the buying group in the last 30 days is used to calculate the score.

There is a daily frequency cap of 20 for each activity. If a member of a buying group performs the same activity more than 20 times a day, the count of the activity is capped at 20 and not a higher number.

The displayed score is rounded. For example, a score of 75.89999 is displayed as 76.

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
