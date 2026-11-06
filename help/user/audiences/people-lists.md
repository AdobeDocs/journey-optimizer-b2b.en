---
title: People Lists
description: Learn people lists, and how to browse, view, edit, delete, and use them in Journey Optimizer B2B Edition.
feature: Audiences
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
---

# People lists

In [!DNL Journey Optimizer B2B Edition], a people list is a named collection of person profiles that you can reuse across your journeys. Instead of recreating the same set of filters in every journey, define the group of people one time and reference it wherever you need it. For example, use a people list to exclude internal staff or existing customers from a nurture journey, or to track people who completed a step in one journey so that another journey can act on them.

There are two types of people lists:

* **[!UICONTROL Static]** - Membership changes only when you explicitly add or remove people. You can add people by applying a filter set to populate the list based on current person data, or add and remove people through an account or person journey. See [Static people lists](./people-lists-static.md).
* **[!UICONTROL Dynamic]** - You define a set of rules (filters) for automatically curating the list. The list refreshes dynamically as people become qualified or disqualified for the rules definition. See [Dynamic people lists](./people-lists-dynamic.md).

You can [use people lists in account journeys and person journeys](#use-people-lists-in-journeys) to split paths based on list membership and to add people to or remove people from static lists.

>[!NOTE]
>
>People lists include person profiles that are already synced and available in [!DNL Journey Optimizer B2B Edition]. Profiles are not read directly from [!DNL Adobe Experience Platform] audiences when the list is evaluated.

## Access and browse people lists {#access-browse}

Access people lists from the left navigation to view, create, and manage list membership.

>[!AVAILABILITY]
>
>The following product permissions control access to people lists:
>
>* [!UICONTROL Manage B2B Person Lists]  - View, create, edit, and delete people lists.
>* [!UICONTROL View B2B Person Lists] - View people lists and their members (read-only).
>
>For information about assigning permissions, see [User access and permissions](../admin/user-management.md#b2b-product-permissions).

* On the left navigation, expand **[!UICONTROL Accounts]** and select **[!UICONTROL People lists]**.

* Select **[!UICONTROL Dynamic lists]** or **[!UICONTROL Static lists]** to switch between the two list types.

* Enter text in the _Search_ field at the top of the list to filter the displayed list by name.

   ![Access people lists to manage your person-level audiences](./assets/people-lists-browse-search.png){width="800" zoomable="yes"}

* Click the _Column settings_ ( ![Column settings icon](../assets/do-not-localize/icon-column-settings-new.svg) ) icon in the top-right corner to select or clear the displayed columns.

* To change the width of a column, drag the divider between column headers.

Each tab includes the **[!UICONTROL Name]**, **[!UICONTROL Last updated]**, **[!UICONTROL Updated by]**, **[!UICONTROL Created on]**, and **[!UICONTROL Created by]** columns. Click the people list name to view its details.

From this page, you can also:

* Create new dynamic and static lists.
* Open a list and [review current members](#view-list-members).
* Click the _More actions_ ( **...** ) icon for a list and choose to [edit](#edit-list-properties) or [delete](#delete-people-list) it.

## Create a people list {#create-people-list}

1. Click **[!UICONTROL Create list]** at the top right of the _[!UICONTROL People lists]_ page.

   ![Create people list dialog](./assets/people-list-create-dialog.png){width="450"}

1. Enter a **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional) for the list.

   The name can include up to 180 characters and must be unique among lists of the same type. The description can include up to 2,000 characters.

1. Choose the list **[!UICONTROL Type]**:

   * [**[!UICONTROL Static]**](./people-lists-static.md) - Qualification filters determine membership when you apply them to the list. Membership updates only when you manually add people or a journey adds or removes them.
   * [**[!UICONTROL Dynamic]**](./people-lists-dynamic.md) - Qualification filters determine membership dynamically. Membership refreshes automatically.

1. Click **[!UICONTROL Create]**.

   The new people list opens on its details page, and the filter editor opens so that you can define the people for the list. To add people to a static list, apply one or more filters. For a dynamic list, define the rules for list membership.

## View list members {#view-list-members}

On the details page for a people list, the **[!UICONTROL Members]** list displays the people in the list. The total number of people in the list is displayed at the top of the table.

The members table includes the following columns:

* **[!UICONTROL Name]**
* **[!UICONTROL Email address]**
* **[!UICONTROL Job title]**
* **[!UICONTROL Company]**
* **[!UICONTROL Unsubscribed]**
* **[!UICONTROL Created on]**
* **[!UICONTROL Last modified]**

By default, the system sorts members by **[!UICONTROL Last modified]**, showing the most recently modified people first. You can also sort by **[!UICONTROL Name]**, **[!UICONTROL Email address]**, or **[!UICONTROL Created on]**.

* To find a specific member, use the _Search_ field. You can search by first name, email address, or company.
* To choose the columns to display, click the _Column settings_ icon and select or clear the checkboxes. The _[!UICONTROL Name]_ column is always displayed.
* To see the latest membership, use the _[!UICONTROL More]_ menu to choose **[!UICONTROL Refresh members]**.
* To view more information about a person, click the person's name to open the [person details](../accounts/person-details.md) page, where you can view their summary and recent activities.

## Edit people list properties {#edit-list-properties}

You can change the name and description for a static or dynamic people list.

1. Open the _[!UICONTROL Edit list]_ dialog using one of the following methods:

   * On the _[!UICONTROL People lists]_ page, click the _More actions_ ( **...** ) icon for the list and choose **[!UICONTROL Edit]**.
   * On the details page for the list, click **[!UICONTROL Edit list properties]**.

1. Update the **[!UICONTROL Name]** or **[!UICONTROL Description]**.

1. Click **[!UICONTROL Save]**.

## Delete a people list {#delete-people-list}

>[!IMPORTANT]
>
>Deleting a people list is permanent and cannot be undone. You cannot delete a people list that is in use by an active journey.

1. Delete the list using one of the following methods:

   * On the _[!UICONTROL People lists]_ page, click the _More actions_ ( **...** ) icon next to the list name and choose **[!UICONTROL Delete]**.
   * On the details page for the list, click **[!UICONTROL Delete list]**.

1. In the confirmation dialog, click **[!UICONTROL Delete]**.

## Use people lists in journeys {#use-people-lists-in-journeys}

In account journeys and person journeys, you can use people lists to filter paths and to maintain list membership:

* **Split paths by list membership** - In a [split path by people](../journeys/split-merge-paths-nodes.md#people-path-filters) condition, use the _[!UICONTROL Special filters]_ > _[!UICONTROL Person Member of People Static List]_ or _[!UICONTROL Person Member of People Dynamic List]_ filter to include or exclude people based on their membership in a specified list.

* **Add and remove from a static list**

   * Use the _[!UICONTROL Add to People List]_ action to add people to a selected static list. If a person is already a member, the action is ignored.

   * Use the _[!UICONTROL Remove from People List]_ action to remove people from a selected static list. If a person is not a member, the action is ignored.

   For details about adding these actions to a journey, see [People actions](../journeys/action-nodes.md#people-actions).
