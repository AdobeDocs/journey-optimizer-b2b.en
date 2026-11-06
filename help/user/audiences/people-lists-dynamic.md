---
title: Dynamic People Lists
description: Define membership rules and duplicate dynamic people lists in Journey Optimizer B2B Edition.
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

# Dynamic people lists

A dynamic [people list](./people-lists.md) is a collection of person profiles that is defined by rules (filters). Dynamic list membership is defined using simple filters that reference person attributes and activities. Membership is maintained automatically as profiles qualify and disqualify according to the filter logic.

You cannot add or remove individual people from a dynamic list. To change the list membership, update its rules. If you need to manage membership manually or through a journey, use a [static list](./people-lists-static.md) instead.

## Set membership rules {#set-membership-rules}

>[!NOTE]
>
>A dynamic list without rules has no members. To populate the list, add at least one filter.

1. Open the dynamic list and select the **[!UICONTROL Rules]** tab.

1. Click **[!UICONTROL Edit rules]**.

   ![Access rules for building a dynamic people list](./assets/people-list-dynamic-rules-edit.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL Edit rules]_ dialog, define the rules for qualifying profiles by dragging filters from the left panel.

   Qualify profiles for the list using any combination of:

   * Activity history
   * [!DNL Experience Platform] enabled person fields
   * Custom fields
   * Intent data
   * Person attributes
   * Special filters, such as journey membership

   For each filter that you add, click **[!UICONTROL Add constraints]** to refine the matching criteria. Fine-tune your conditions by applying the **[!UICONTROL Filter logic]** at the top. You can choose to match all conditions, any condition, or define advanced logic.

   ![Add filters with constraints to populate the dynamic list](./assets/people-list-dynamic-rules-edit-filter.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Done]** to save your changes.

   The **[!UICONTROL Rules]** tab displays the filters and the filter logic for the list, and the **[!UICONTROL Members]** tab refreshes to reflect the updated membership. To find the most up-to-date audience qualifications, use **[!UICONTROL Refresh members]** in the **[!UICONTROL More]** menu.

1. Select the **[!UICONTROL Members]** tab.

   Qualifying members appear in the list after a brief delay.

   ![Generated members for a dynamic people list](./assets/people-list-dynamic-members.png){width="700" zoomable="yes"}

>[!NOTE]
>
>To change the list rules at any time, you can repeat these steps. The list membership refreshes based on the saved filters.

<!--

## Duplicate a dynamic list {#duplicate-dynamic-list}

Duplicating a dynamic list replicates its membership filtering so that you can reuse it in a different context.

1. In the _[!UICONTROL Dynamic lists]_ tab, click the _More menu_ ( **...** ) icon next to the list and choose **[!UICONTROL Duplicate]**.

1. Enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional).

   By default, the dialog appends `_copy` to the name of the originating list. Enter a different unique name as needed.

   ![Duplicate list dialog](./assets/people-list-duplicate-dialog.png){width="375"}

1. Click **[!UICONTROL Duplicate]**.
-->
