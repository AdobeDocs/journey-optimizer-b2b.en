---
title: Static People Lists
description: Add and remove members for static people lists in Journey Optimizer B2B Edition.
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

# Static people lists

A static [people list](./people-lists.md) is a collection of person profiles whose membership changes only when you add or remove people. Simple filters that reference person attributes and activities define static list membership. Membership changes only when you add or remove members. You can:

* [Add people](#static-list-add-members) by applying a filter set that is evaluated one time, when you apply it.
* Add and remove people through an account or person journey, using the [!UICONTROL Add to People List] and [!UICONTROL Remove from People List] actions. (See [Use people lists in journeys](./people-lists.md#use-people-lists-in-journeys))
<!-- * [Activate the list to a destination](#static-list-activate) to sync its membership downstream. -->

>[!NOTE]
>
>Static list filter definitions apply one time, when you add members to the list. The defined filter is not available afterward. If you want to maintain a consistent audience definition using filters, use a [dynamic list](./people-lists-dynamic.md) instead.

## Add members {#static-list-add-members}

>[!NOTE]
>
>If you want a static list to start empty, do not apply filters. An empty static list is useful when you plan to add members through journeys.

1. Open the static list and click **[!UICONTROL Add people]** at the top right.

   ![Add people to a static people list](./assets/people-list-static-add-people.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL Add people]_ dialog, define the rules for qualifying profiles by dragging filters from the left panel.

   Filter profiles using any combination of:

   * Activity history
   * Experience Platform enabled person fields
   * Custom fields
   * Intent data
   * Person attributes
   * Special filters, such as journey membership

   The filters are nested in category folders. Expand each folder and scroll through the available filters, or use the _Search_ field at the top to locate the filter that you need. For each filter that you add:

   * Drag the filter from the left panel to the filter definition space.
   * Complete the match evaluation definition.
   * Click **[!UICONTROL Add constraints]** to refine the matching criteria.

   Fine-tune your conditions by applying the **[!UICONTROL Filter logic]** at the top. You can choose to match all conditions, any condition, or define advanced logic.

   ![Add filters with constraints to add people to the static list](./assets/people-list-static-add-people-filters.png){width="800" zoomable="yes"}

1. Click **[!UICONTROL Done]** to save your changes.

   The system processes the request and displays a confirmation message when people are added. Processing time depends on the number of people to evaluate and the filter criteria that you selected. As the list continues to populate, use **[!UICONTROL Refresh members]** in the _[!UICONTROL More]_ menu to refresh the list.

   Qualifying members appear in the list after a brief delay. The filter set is evaluated one time, so people who later match the filters are not added automatically. You can repeat this process at any time to add more people to the list.

   ![Members for a static people list](./assets/people-list-static-members.png){width="700" zoomable="yes"}

## Remove members {#static-list-remove-members}

You can remove people from a static list automatically through a journey using the [!UICONTROL Remove from People List] action. (See [Use people lists in journeys](./people-lists.md#use-people-lists-in-journeys))

<!--
TODO: Restore this section when the activate to a destination function is released.

## Activate to a destination {#static-list-activate}

Activating a static people list sends its membership to a connected destination, with ongoing sync instead of a one-time export. This is useful for paid media targeting, suppression, and downstream orchestration.

* The static list acts as a container for the people.
* The activation sends and syncs that membership to a destination.
* People added to the list later are propagated automatically.
* People removed later are deactivated automatically.

>[!PREREQUISITES]
>
>You must have one or more configured destinations for your [!DNL Journey Optimizer B2B Edition] sandbox before you can activate a static list to a destination. See [Destinations](./destinations.md).

1. Select the **[!UICONTROL Static lists]** tab.

1. Locate the static list that you want to activate, click the _More menu_ ( **...** ) icon next to the list, and choose **[!UICONTROL Activate to destination]**.

   ![Access the More menu for a static people list](./assets/people-lists-static-more-menu.png){width="450"}

   You can also open the static list and use the **[!UICONTROL More]** menu at the top right.

1. Select the check box for the configured destination connection.

   ![Configured destinations available for activation](./assets/people-list-activate-destination-select.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

1. In the _[!UICONTROL Activate list to destination]_ dialog, click **[!UICONTROL Activate]** to confirm.

When activation completes, a confirmation message appears and the destination shows as **[!UICONTROL Active]** on the **[!UICONTROL Destinations]** tab of the list. You can activate a static list to more than one destination at a time. Membership syncs to all of them.

To review the destinations that a static list is activated to, open the list and select the **[!UICONTROL Destinations]** tab.

### Deactivate a destination {#deactivate-destination}

Remove a destination connection from a static list when you no longer want its membership synced downstream.

1. Open the static list and select the **[!UICONTROL Destinations]** tab.

1. Use the row action to remove the destination that you want to disconnect.

1. Confirm in the _[!UICONTROL Deactivate destination]_ dialog.

Deactivating removes the destination from the list. The people in the list are also removed from the connected destination audience.

-->
