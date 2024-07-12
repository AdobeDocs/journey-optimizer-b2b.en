---
title: Buying groups
description: Learn about buying groups and their components.
feature: Buying Groups
exl-id: ddcd7b62-6a76-4f5e-b6d3-a20944ca8332
---

# Buying groups

For B2B sales and marketing activities, accounts are key to any strategy. Each account has a group of people associated with it, and these people may be employees of the account or contractors who work with the account. Accounts are hierarchical, and different products might be sold at different levels in the hierarchy. For example, Adobe Experience Platform might be sold at the corporate level to a top-level account, while Adobe Photoshop might be sold to an account that represents a division or department within an organization, such as a design department within a larger corporation.

![Account roles diagram](assets/account-roles-diagram.png){width="800"}

Within the account, there could be a subset of people who comprise the _buying group_. These people are the ones that ultimately make the purchase decision, so they need special attention from the marketer and might need different information delivered to them than the other people associated with the account. Buying groups may comprise a different group of people for different product lines or offerings. For example, a cybersecurity product might typically require a Chief Information Officer or Chief Security Officer, and a representative from the Legal department to approve a purchase, but a bug tracking product might typically have a VP of Engineering and an IT Director as members of the buying group. 

## Key components

You can increase marketing effectiveness by establishing buying groups in Journey Optimizer B2B Edition that identify missing members for your target accounts lists based on the solutions that your Sales teams are responsible for selling. Before you and your Marketing team start creating your buying groups, make sure that you have the key components defined. These components are critical for meeting your business goals and objectives.

| Component | Purpose |
| --------- | ------- |
| Solution interest | This component provides the answer to: <ul><li>As a marketing organization, what are you selling?</li><li>What product or collection of products are you targeting to sell?</li></ul>  **_Example:_** Cross-selling new Product X to existing customers|
| Account audience | This component provides the answer to: <ul><li>To whom are you selling?</li><li>What is the list of accounts that you are targeting?</li></ul> **_Example:_** Account segment defined by accounts with Product Y that have revenue over 1M|
| Buying group role templates |  This component provides the answer to: <ul><li>What roles are you targeting?</li><li>What set of rules are used to determine who is assigned to buying group roles?</li></ul>  **_Example:_** Assign a person with CMO title to the Decision Maker role |

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

   * Acquire missing people
   * Send to LinkedIn Destination
   * Enrich with Zoominfo

1. Use in an account journey through the associated solution interest.

## Access buying groups and components

On the left navigation, expand **[!UICONTROL Accounts]** and click **[!UICONTROL Buying groups]**.

The _[!UICONTROL Buying groups]_ page is organized as tabs:

| Tab | Description |
| --- | ----------- |
| [!UICONTROL Overview] | This tab is the default and displays the [Buying groups dashboard](../dashboards/buying-groups-dashboard.md). |
| [!UICONTROL Browse] | This tab supports the following activities: <ul><li>View the list of existing buying groups. </li><li>Search by buying group name. </li><li>Filter by solution interest. </li><li>Drill in to buying group details. </li><li>Create a buying group. Delete a buying group.</li></ul> |
| [!UICONTROL Solution interests] | This tab supports the following activities: <ul><li>View the list of existing buying groups. </li><li>Search by buying group name. </li><li>Access and edit solution interest properties. </li><li>Create a solution interest. </li><li>Delete a solution interest. </li><li>View and delete buying group jobs. </li></ul>|
| [!UICONTROL Roles Templates] | This tab supports the following activities: <ul><li>View the list of existing roles templates. </li><li>Search by roles template name. </li><li>Access and edit roles template properties and conditions. </li><li>Create a roles template. </li><li>Delete a roles template. </li></ul>|

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

The engagement score is used to evaluate the effectiveness of your marketing programs based on buying group behavioral activities tracked across journeys. This score is derived from activity over the past 30 days. Any role change to a template requires re-calculation of the engagement score for all buying groups created using that template. Only inbound activities are evaluated in calculating an engagement score.

The displayed score is rounded off (for example, a score of 75.89999 is displayed as 76), there is no upper limit for the score for GA, and there is a daily frequency cap of 20.

The following examples illustrate the calculation of the engagement score:

**Buying group 1** - engagement score = 22.15

| User | Role | Role Weight | Action | Today | Yesterday | Action Weight | Score |
| ---- | ---- | ----------- | ------ | ----- | --------- | ------------- | ----- |
| Adam | Decision Maker | 80% | Visited Website | 1000 | 2| 1 | 22 |
| | | | Clicked Email | 1 | 0 | 1 | 1 |
| | | | Downloaded Pub | 1 | 3 | 1 | 4 |
| Bob | Influencer | 15% | Visited Website | 1 | 2 | 1 | 3 |
| Calvin | Practitioner | 5% | Visited Website | 1 | 1 | 1 | 2 |

**Buying group 2** - engagement score = 8.55

| User | Role | Role Weight | Action | Today | Yesterday | Action Weight | Score |
| ---- | ---- | ----------- | ------ | ----- | --------- | ------------- | ----- |
| Alvin | Decision Maker | 80% | Visited Website | 3 | 2 | 1 | 5 |
| | | | Clicked Email | 1 | 0 | 1 | 1 |
| | | | Downloaded Pub | 1 | 3 | 1 | 4 |
| Bret | Influencer | 15% | Visited Website | 1 | 2 | 1 | 3 |
| Cam | Practitioner | 5% | Visited Website | 1 | 1 | 1 | 2 |
