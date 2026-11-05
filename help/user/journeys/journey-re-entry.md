---
title: Journey re-entry
description: Control when and how often accounts or people can re-enter the same account or person journey.
feature: Account Journeys
role: User
level: Intermediate
exl-id: e5153125-6d5b-4835-bd19-c9b7ce67e46a
autotag-review: '2026-08-14T19:11:15.391Z'
TQID: 'https://experienceleague.adobe.com/BabVdaLaAwER8tEQLOAjChwyy4WI2Cle19-Uu-varIc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
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
# Journey re-entry

When you enable re-entry for a journey, you can control when and how often an account or person can re-enter the same journey. Use the re-entry settings to set criteria, limits, and wait times so that accounts or people requalify for the journey in a controlled way.

An account or person can requalify for a journey when the following items are true:

* The account or person is within the number of allowed re-entries for the journey.
* The account or person has met the wait time threshold (the minimum time to wait before requalifying).
* The account or person is not currently in the journey.

## Enable re-entry for a journey

You can enable re-entry and change re-entry settings when the journey is in a _Draft_ status.

>[!BEGINTABS]

>[!TAB Account journey]

1. Open the draft account journey.

1. Click the **[!UICONTROL More...]** menu at the top right and choose **[!UICONTROL Re-entry]**.

   ![Click More at the top right of an account journey](./assets/account-journey-draft-more-menu.png){width="450"}

1. In the _[!UICONTROL Journey re-entry]_ dialog, toggle the **[!UICONTROL Enable re-entry]** option.

   When the feature is enabled, the options for timing, delay, and limits are displayed.

   ![Journey re-entry dialog for an account journey with enabled feature](./assets/journey-re-entry-dialog-enabled.png){width="450"}

1. For **[!UICONTROL Re-entry timing]**, choose how the wait is calculated:

   * **[!UICONTROL Wait from end of journey]** - The wait period starts when the account exits or completes the journey. For example, "30 days after the account completes the journey, it can re-enter."

   * **[!UICONTROL Wait from start of journey]** - The wait period is based on when the account first entered the journey. For example, "30 days from when the account started the journey, it can re-enter."

1. Set the **[!UICONTROL Re-entry delay]**, which is the wait duration in hours or days.

   This setting determines how long an account must wait after exiting or starting the journey before it can re-enter.

1. To define the maximum times an account is allowed to enter the journey, set the **[!UICONTROL Entry limit]**.

   When an account reaches the limit, it no longer qualifies for entry until the limit is reset or the journey is republished with a new limit.

   This limit applies per account for that journey.

1. Click **[!UICONTROL Save]**.

>[!TAB Person journey]

1. Open the draft person journey.

1. Click the **[!UICONTROL More...]** menu at the top right and choose **[!UICONTROL Re-entry settings]**.

   ![Click More at the top right of a person journey](./assets/person-journey-draft-more-menu.png){width="450"}

1. In the _[!UICONTROL Journey re-entry]_ dialog, toggle the **[!UICONTROL Enable re-entry]** option.

   When the feature is enabled, the options for timing, delay, and limits are displayed.

   ![Journey re-entry dialog for a person journey with enabled feature](./assets/person-journey-re-entry-dialog.png){width="450"}

1. For **[!UICONTROL Re-entry timing]**, choose how the wait is calculated:

   * **[!UICONTROL Wait from end of journey]** - The wait period starts when the person exits or completes the journey. For example, "30 days after the person completes the journey, they can re-enter."

   * **[!UICONTROL Wait from start of journey]** - The wait period is based on when the person first entered the journey. For example, "30 days from when the person started the journey, they can re-enter."

1. Set the **[!UICONTROL Re-entry delay]**, which is the wait duration in hours or days.

   This setting determines how long a person must wait after exiting or starting the journey before they can re-enter.

1. To define the maximum times a person is allowed to enter the journey, set the **[!UICONTROL Entry limit]**.

   When a person reaches the limit, they no longer qualify for entry until the limit is reset or the journey is republished with a new limit.

   This limit applies per person for that journey.

1. Click **[!UICONTROL Save]**.

>[!ENDTABS]

## Progression and activity

For a published account or person journey, the journey canvas displays [progression](./journeys-overview.md#review-account-progression) for the journey nodes. Each node displays the number of accounts or people to reach that node and, for live journeys, the number currently at that node. Each time an account or person re-enters a journey, it counts as a distinct entry.

<!-- 
You can see how many times accounts have entered the journey. ?? 

When you drill in to [account details](../accounts/account-details.md), the account activity shows each time the account entered the journey. It includes explicit activity and a recurrence count so that you can see re-entries clearly.
-->
