---
title: Use People Lists in Journeys
description: Use people lists to add or remove people dynamically and to split journey paths by list membership in Journey Optimizer B2B Edition.
feature: Audiences, Person Journeys, Account Journeys
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---

# Use people lists in journeys

There are multiple ways that you can incorporate [people lists](./people-lists.md) into your account journeys and person journeys:

* **Maintain a static list from a journey** - In a _Take an action_ node, use the _[!UICONTROL Add to People List]_ or _[!UICONTROL Remove from People List]_ action to update the membership of a static people list as people move through the journey.
* **Route people based on list membership** - In a _Split paths_ node, use the _[!UICONTROL Person Member of People Static List]_ or _[!UICONTROL Person Member of People Dynamic List]_ filter to create a path for people who are (or are not) members of a list.

For example, you can build an exclusion list of team members and partners and use it to exclude those people from a nurture path. Or you can add people to a static list when they reach a qualification point in one journey and then use that list to branch people in a different journey.

## Take an action node - Add to people list {#add-to-people-list}

**_Static people lists only_**

Within an account or person journey, add people to a static people list using [a _Take an action_ node](../journeys/action-nodes.md#people-actions).

For example, consider a journey path where you send an email, and some people register for a webinar. You consider this response to be a qualification point in the journey. Upon qualification, you want to add these people to a static people list that another journey uses to split qualified people onto a different path.

>[!NOTE]
>
>If a person is already in the list when the node executes, the action is ignored.

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

1. (Account journeys only) Select the _[!UICONTROL Action on]_ **[!UICONTROL People]** option.

1. For _[!UICONTROL Action on people]_, choose **[!UICONTROL Add to People List]**.

1. For **[!UICONTROL Select Static People List]**, choose the people list where you want to add people.

   ![Select Add to People List](../journeys/assets/node-action-add-to-people-list.png){width="300"}

## Take an action node - Remove from people list {#remove-from-people-list}

**_Static people lists only_**

Within an account or person journey, remove people from a static people list using [a _Take an action_ node](../journeys/action-nodes.md#people-actions).

For example, after a person converts, you want to remove them from a static list. This list is used to route people onto a nurture path so that they no longer receive nurture communications.

>[!NOTE]
>
>If a person is not in the list from which they are scheduled for removal, the action is ignored.

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Take an action]**.

1. (Account journeys only) Select the _[!UICONTROL Action on]_ **[!UICONTROL People]** option.

1. For _[!UICONTROL Action on people]_, choose **[!UICONTROL Remove from People List]**.

1. For **[!UICONTROL Select Static People List]**, choose the people list from which you want to remove people.

   ![Select Remove from People List](../journeys/assets/node-action-remove-from-people-list.png){width="300"}

## Split paths node - Member of people list {#split-paths-by-list-membership}

**_Account and person journeys_**

Use the people list membership filters in a [_Split paths_ node](../journeys/split-merge-paths-nodes.md) to route people based on whether they are members of a people list. Two filters are available:

| Filter | Description |
| ------ | ----------- |
| [!UICONTROL Person Member of People Dynamic List] | The person is or is not a member of one or more dynamic people lists. Membership reflects the list's current rules. |
| [!UICONTROL Person Member of People Static List] | The person is or is not a member of one or more static people lists. |

These filters are available in both journey types:

* **Person journeys** - In a _Split paths_ node.
* **Account journeys** - In a _Split paths_ node that splits by _[!UICONTROL People]_.

To exclude team members and partners from a nurture path, add the _[!UICONTROL Person Member of People Static List]_ filter, set the operator to `is not`, and select the list.

1. Navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Split paths]**.

   ![Add journey node - split paths](../journeys/assets/add-node-split.png){width="300" zoomable="no"}

1. (Account journeys only) Set the node for people conditions.

   * In the node properties on the right, choose **[!UICONTROL People]** for the split.

   * Set **[!UICONTROL Attributes used for conditions]** to **[!UICONTROL People attributes only]**.

   ![Account journey - split path node - people attributes](../journeys/assets/node-split-path-account-journey-people-attributes.png){width="300" zoomable="no"}

1. To define a condition for _[!UICONTROL Path 1]_, click **[!UICONTROL Apply condition]**.

1. In the conditions editor, expand the _[!UICONTROL Special filters]_ folder and drag the **[!UICONTROL Person Member of People Dynamic List]** or **[!UICONTROL Person Member of People Static List]** filter onto the conditions workspace.

     ![Split path conditions editor with Person Member of People List filters](../accounts/assets/account-lists-person-journeys-split-path-filter.png){width="700" zoomable="yes"}

1. To include list members, set the membership to `is`.

   To exclude them, set it to `is not`.

1. Select the people list to evaluate.

   Enter text in the field to filter the available lists. Only user-created people lists are available for selection.

1. Refine your conditions by applying the **[!UICONTROL Filter logic]** at the top.

   You can combine list membership filters with other people filters and choose to match all conditions or any condition.

1. Click **[!UICONTROL Done]**.

Continue configuring the split paths node as described in [_Add a split path by people node_](../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node). For more information about membership filters, see [_Membership filtering_](../journeys/split-merge-paths-nodes.md#membership-filtering).
