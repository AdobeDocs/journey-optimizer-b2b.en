---
title: Split and Merge Paths
description: Split and merge journey paths to segment accounts or people by conditions, buying groups, and event history in Journey Optimizer B2B Edition.
feature: Account Journeys
solution: Journey Optimizer B2B Edition
role: User
exl-id: 563d6a85-504d-4c70-b075-8a9a9e88bd6b
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
autotag-review: 2026-03-30T23:10:13.939Z
TQID: https://experienceleague.adobe.com/qTheDe4jO49z8u8ia2wGZvLg-Gbh0MrN--a0lksLPBs
---
# Split and merge paths {#split-paths}

Use split and merge path nodes to segment people or accounts according to the conditions that you define. Create paths for the audience or accounts list according to conditions, define each path with action and event nodes for the segment, and then combine the paths and continue the journey.

![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the overview video](#overview-video)

A _Split paths_ node defines one or more segmented paths based on **_either_** account or people filters. A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step without losing their account context.

>[!NOTE]
>
>A maximum of 25 paths are supported.

## Split paths by accounts {#split-paths-by-accounts}

**_(Account journeys only)_**

Split by accounts paths can include both account and people actions and events. These paths can be split further.

_**How a split path by accounts node works**_ 

* Each path that you add includes an end node with the ability to add nodes to each edge.
* Split by account nodes can be nested (you can split the path by accounts repeatedly). 
* Evaluation of each path is from top to bottom. If an account matches the first and second paths, it proceeds along the first path only.
* Two or more paths can be combined using a merge node.
* The node supports the definition of an _[!UICONTROL Other accounts]_ path, where you can add actions or events for accounts that do not match one of the defined segments/paths.

![Journey node - split paths by account](./assets/node-split-paths-account.png){width="700" zoomable="yes"}

### Account path conditions {#account-path-filters}

| Path conditions | Description |
| --------------- | ----------- |
| [!UICONTROL Account Attributes] | Attributes from the account profile, including: <li>Annual revenue <li>City <li>Country <li>Employee size <li>Industry <li>Name <li>SIC code <li>State |
| [!UICONTROL Custom Objects] > Has `<custom object>` | [!BADGE Beta]{type=Informative tooltip="Beta feature"} The account does or does not have relational schema records. It can also be evaluated against any of the selected custom object criteria, as configured in the [XDM relational schema](../admin/xdm-field-management.md#relational-schemas). (See [Custom data filtering](#custom-data-filtering).) |
| [!UICONTROL Special filters] > [!UICONTROL Account has matched buying group] | The account is matched with one or more buying groups. It can be evaluated against one or more of the following constraints for a matched buying group: <li>Solution Interest <li>Buying Group stage <li>Buying Group status <li>Engagement Score <li>Completeness Score <li> Number of people in buying group role |

### Add a split path by account node

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Add journey node - split paths](./assets/add-node-split.png){width="300" zoomable="no"}

1. In the node properties on the right, choose **[!UICONTROL Accounts]** for the split.

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

   ![Split path node - add condition](./assets/node-split-properties-apply-condition.png){width="500" zoomable="yes"}

1. To define the split path, add one or more filters in the conditions editor.

   * Drag and drop filter attributes from the left navigation and complete the match definition.

   * Refine your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all filters or any filter.

      ![Split path node - conditions accounts filter logic](./assets/node-split-conditions-accounts.png){width="700" zoomable="yes"}

   * Click **[!UICONTROL Done]**.

1. To add more paths, click **[!UICONTROL Add path]** and repeat the previous steps to add conditions applicable to this path.

   You can also label each path based on these conditions or use the default labels.

1. If needed, reorder the paths according to the priority that you want for the split.

   Path filtering is evaluated in top-down order. Each account proceeds along the first path that matches.

   Click the up and down arrows at the top right of each path card to move it higher or lower in the list of paths.

   ![Split path node - reorder paths](./assets/node-split-reorder-paths-accounts.png){width="500" zoomable="yes"}

1. Enable the **[!UICONTROL Other accounts]** option to define the default path for accounts that are not a match for the defined segments/paths.

   When this option is not enabled, the journey ends for accounts that do not match a defined segment/path within the split.

### Buying group filtering for accounts {#buying-group-filtering-accounts}

You can define a path for accounts associated with buying groups and filter the path using buying group criteria. Use the **[!UICONTROL Account has matched buying group]** filter to define the path segment using a matched buying group. This filter also includes the option to identify accounts based on the number of assigned roles within a matched buying group.

For example, you could evaluate buying group readiness based on the depth (number of people) it has in different roles, such as three decision makers and two influencers. In this case, set the condition to target accounts with a minimum of three (3) Decision Makers and two (2) Influencers in a matched buying group:

1. Click **[!UICONTROL Add filter]** and choose the **[!UICONTROL Number of people in buying group role]** filter.

   ![Add filter for Account has matched buying group and choose Number of people in buying group role](./assets/node-split-account-condition-matched-buying-group-number-people-role.png){width="700" zoomable="yes"}

1. Define the first role parameter.

   * Set the number of people evaluation to `at least` with a value of `3`.
   * Set the role evaluation to `is` and choose `Decision Maker` from the list of roles.

1. Repeat step 1 to add another buying group role parameter.

1. Define the second role parameter.

   * Set the number of people evaluation to `at least` with a value of `2`.
   * Set the role evaluation to `is` and choose `Influencer` from the list of roles.

   ![Conditions example for role depth in matched buying group for an account](./assets/node-split-account-condition-matched-buying-group-role-depth-example.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Done]** when you have all conditions defined for the path.

For the identified accounts, you could then add an action node in the path to update the status of the buying group or stage, or to send a sales alert email.

## Split paths by people

_(Account and person journeys)_

Split by people paths can include only people actions. These paths cannot be split again and automatically join back.

_**How a split path by people node works**_ 

* Split by people nodes function within a _grouped node_ split-merge combination. The split paths automatically merge so that all people can move forward to the next step without losing their account context.
* Split by people nodes cannot be nested (you cannot add a split path for people on a path that is in this grouped node).
* Evaluation of each path is from top to bottom. If a person matches the first and second paths, they proceed along the first path only.
* The node supports the use of _account-person relationships_, which allows you to filter people based on their role (such as contractor or full-time employee) as defined in the relationship.
* The node supports the definition of an _[!UICONTROL Other people]_ path, where you can add actions or events for people that do not match one of the defined segments/paths.

![Account journey node - split paths by people](./assets/node-split-paths-people.png){width="700" zoomable="yes"}

### People path filters {#people-path-filters}

| Filters | Description |
| ------------ | ----------- |
| [!UICONTROL Custom Objects] > Has `<custom object>` | [!BADGE Beta]{type=Informative tooltip="Beta feature"} The person does or does not have relational schema records. It can also be evaluated against any of the selected custom object criteria, as configured in the [XDM relational schema](../admin/xdm-field-management.md#relational-schemas). (See [Custom data filtering](#custom-data-filtering)) |
| [!UICONTROL Event history] | Splits people based on experience events that occurred prior to journey entry. Expand the folder to see all event types configured in [Admin > XDM event configuration](../admin/configure-aep-events.md) and select one to add as a filter. Constraints include fields from the selected event, a lookback time window measured back from when the person enters the journey, and an optional minimum number of times. |
| [!UICONTROL Person attributes] | Attributes from the [person profile](../admin/field-mapping.md#xdm-business-person-attributes), including: <li>City <li>Country <li>Email address <li>Email invalid <li>Email suspended <li>First name <li>Inferred state region <li>Job title <li>Last name <li>Mobile phone number <li>Person engagement score <li>Phone number <li>Postal code <li>State |
| [!UICONTROL Special filters] > [!UICONTROL Member of Buying Group] | The person is or is not a buying group member evaluated against one or more of the following criteria: <li>Solution Interest</li><li>Buying Group status</li><li>Completeness Score</li><li>Engagement Score</li><li>Is Removed</li><li>Role</li> |
| [!UICONTROL Special filters] > [!UICONTROL Member of List] | (Deprecated) The person is or is not a member of one or more [!DNL Marketo Engage] lists. |
| [!UICONTROL Special filters] > [!UICONTROL Member of Program] | (Deprecated) The person is or is not a member of one or more [!DNL Marketo Engage] programs. |

### Account-person path conditions

| Path conditions | Description |
| --------------- | ----------- |
| [!UICONTROL Role in account] | The person is or is not assigned a role in the account. Optional constraints: <li>Role name |

### Add a split path by people node {#add-a-split-path-by-people-node}

>[!NOTE]
>
>When you split paths by people, a _Close split paths_ node is automatically inserted to end the split. A split-by-people path allows only _Take an action_ on people nodes.

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Add journey node - split paths](./assets/add-node-split.png){width="300" zoomable="no"}

1. In the node properties on the right, choose **[!UICONTROL People]** for the split.

1. (Account journeys only) Set the **[!UICONTROL Attributes used for conditions]**.

   * Choose **[!UICONTROL People attributes only]** to use conditions related to the person profile. 
   * Choose **[!UICONTROL Account-person attributes only]** to use conditions related to the person's role membership within an account.

1. To define a condition applicable to _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

1. In the conditions editor, add one or more filters to define the split path.

   * Drag and drop any of the people filters from the left navigation and complete the match definition.

      >[!NOTE]
      >
      >If you have custom person fields defined in the account audience schema in Experience Platform, these fields are also available to use as person attributes in conditions. 

   * Refine your conditions by applying the **[!UICONTROL Filter logic]** at the top. You choose to match all attribute conditions or any condition.

      ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"}

   * Click **[!UICONTROL Done]**.

1. To add more paths, click **[!UICONTROL Add path]** and repeat the previous steps to add conditions applicable to this path.

   You can also label each path based on these conditions or use the default labels.

1. If needed, reorder the paths according to the priority that you want for the split.

   Path filtering is evaluated in top-down order. Each person proceeds along the first path that matches.

   Click the up and down arrows at the top right of each path card to move it higher or lower in the list of paths.

   ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"}

1. Enable the **[!UICONTROL Other people]** option to add a default path for people that are not a match for the defined paths. 

   When this option is not enabled, people that do not match a defined segment/path move past the split and proceed to the next step in the journey.

   When you have conditions defined for each path for splitting your audience on the people level, you can add actions that you want to take on people.

### Experience event history filtering {#experience-event-history-filtering}

For a split path by people, you can define a path based on experience events that occurred before the person entered the journey. In the conditions editor, expand the **[!UICONTROL Event history]** folder to see a list of all event types configured by your administrator. Select an event type to add it as a filter condition.

The lookback time window for event history is measured backward from the moment the person enters the journey. For example, a 30-day window evaluates whether the qualifying event occurred within the 30 days prior to journey entry.

You can further refine the filter using constraints specific to the selected event's fields. The optional **[!UICONTROL Minimum number of times]** and **[!UICONTROL Date of activity]** constraints are both evaluated within the defined lookback window. Because event history data is synced from Adobe Experience Platform, there may be a brief delay before a recently occurring event becomes visible to this filter.

>[!NOTE]
>
>The events available in the [!UICONTROL Event history] folder are determined by the [Experience Events and fields configurations](../admin/configure-aep-events.md).

**Example:** To route people who clicked a link in a marketing email before entering the journey, select the email click event from the [!UICONTROL Event history] folder, set the lookback window to cover the relevant time period, and apply any field-level constraints (such as a specific link URL) as needed.

![Split path by people condition for event history](./assets/node-split-people-condition-event-history.png){width="700" zoomable="yes"}

>[!BEGINSHADEBOX "Inactivity filtering"]

For each of the _[!UICONTROL Event history]_ filters, you can enable the **[!UICONTROL Switch to inactivity filter]** option. This option changes the filter to an evaluation for an absence of that activity type. For example, add the _[!UICONTROL Direct Marketing Email Opened]_ filter to create a path for people who _**did not**_ open an email. Enable the inactivity option and specify the email.

![Split path by people inactivity condition](./assets/node-split-people-condition-inactivity.png){width="700" zoomable="yes"}

>[!ENDSHADEBOX]

### Membership filtering

Within the _[!UICONTROL Special Filters]_ section, there are multiple filters that you can use to evaluate a person's membership in a buying group or [!DNL Marketo Engage] list. 

For example, if you want to create a path for people who are members of a buying group and are assigned a particular role, add the _[!UICONTROL Special filters]_ > _[!UICONTROL Member of Buying group]_ filter. For the filter, set the membership as _true_, select a _[!UICONTROL Solution interest]_ that is associated with one or more buying groups, and set the _[!UICONTROL Role]_ that you want to match.

![Split path by people condition for buying group membership](./assets/node-split-people-condition-buying-group-membership.png){width="700" zoomable="yes"}

You can also include additional buying group membership constraints:

* _[!UICONTROL Buying group stage]_
* _[!UICONTROL Buying group status]_
* _[!UICONTROL Completeness score]_
* _[!UICONTROL Engagement score]_
* _[!UICONTROL Is Removed]_

>[!TIP]
>
>To exclude members who were removed from a buying group, use the _[!UICONTROL Is Removed]_ constraint set to `false`. You can also explicitly include removed members by setting this constraint to `true`.

>[!BEGINSHADEBOX "Marketo Engage list and program membership"]
   
In [!DNL Marketo Engage], _Smart Campaigns_ check membership of programs to ensure that leads don't receive duplicate emails and aren't members of multiple streams of emails at the same time. In Journey Optimizer B2B, you can check for [!DNL Marketo Engage] list membership as a condition for your split path by people to help eliminate duplication in journey activities.
      
To use list membership in a split condition, expand **[!UICONTROL Special Filters]** and drag the **[!UICONTROL Member of List]** or **[!UICONTROL Member of Program]** condition into the filter space. Complete the filter definition to evaluate membership in one or more [!DNL Marketo Engage] lists.
   
![Split path by people condition for [!DNL Marketo Engage] list membership](./assets/node-split-paths-conditions-people-member-of-list.png){width="700" zoomable="yes"}
<br/>

>[!NOTE]
>
>**Feature deprecation**</br></br>
>
>In the current Journey Optimizer B2B Edition release, filtering based on list or program membership in a Marketo Engage instance is not supported.
   
>[!ENDSHADEBOX]

## Custom data filtering {#custom-data-filtering}

[!BADGE Beta]{type=Informative tooltip="Beta feature"} 

You can use relational schemas (model-based classes) to split paths by account or people. The custom objects are defined within _relational schemas_, and a product administrator can [configure relational schema fields](../admin/xdm-field-management.md#relational-schemas) in [!DNL Journey Optimizer B2B Edition]. The selected schema fields are available in the condition editor for use in _split path by account_ and _split path by people_ nodes.

For a **[!UICONTROL Split path by account]** or **[!UICONTROL Split path by people]** condition, expand _[!UICONTROL Custom Objects]_. Add the condition and set the value to `true` or `false`. Click **[!UICONTROL Add constraint]** to use the field values for filtering.

![Account conditions example for relational schema custom object](./assets/node-split-paths-account-relational-schema.png){width="600" zoomable="yes"}

## Merge paths {#merge-paths}

Add a _Merge paths_ node to combine different _split paths by account_ in your journey. 

1. In a journey map with a split node that has three or more paths, add a combination of actions and events to each path.

1. Click the plus ( **+** ) icon for any one of these paths and choose **[!UICONTROL Merge]** from the displayed options.

   ![Journey node - merge paths](./assets/node-plus-icon-merge-paths.png){width="400" zoomable="no"}

1. In the merge paths node properties, select the paths you want to merge.

   ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"}

   At this point, the paths are merged so that accounts from the selected paths combine to a single path that can continue to progress through the journey.

1. If needed, you can unmerge paths by navigating back to the merge paths node properties and clearing the checkbox for any paths that you want to remove.

## Overview video {#overview-video}

>[!VIDEO](https://video.tv.adobe.com/v/3443231/?learn=on)
