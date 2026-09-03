---
title: Use Account Lists in Journeys
description: Use account lists in journey orchestration and add/remove accounts dynamically in Journey Optimizer B2B Edition.
feature: Account Lists, Account Journeys
role: User
exl-id: 7cda080d-6263-4ccd-b144-432e4e78c298
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: e935834c-48b7-43d8-b754-a815196a1b05
    internal-label: Account lists
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
autotag-review: 2026-03-27T22:29:03.719Z
TQID: https://experienceleague.adobe.com/FokJGxTj7abTN01WCcrVLDEuNLW0oI-i-8z0j-rFBO4
---
# Use account lists in journeys

There are multiple ways that you can incorporate Live (published) account lists into your account journeys.

## Account audience node

All account journeys start with an [_Account audience_ node](../journeys/account-audience-nodes.md). When you set this node to use an account list, the member accounts move through the journey when it goes live (published).

1. Select the **[!UICONTROL Account list]** option for the starting _Account audience_ node.

   ![Select account list option for account audience node](../journeys/assets/node-audience-account-list.png){width="500"}

1. Click **[!UICONTROL Add accounts list]**.

1. Select the checkbox for the account list and click **[!UICONTROL Save]**.

   ![Select account list option for account audience node](../journeys/assets/node-audience-account-list-select-dialog.png){width="600" zoomable="yes"}

## Take an action node - Add to account

**_Static account lists only_**

Within an account journey, add accounts to a static account list using [a _Take an Action_ node](../journeys/action-nodes.md).

For example, you have a journey path where you send an email and some accounts take various actions as a response. You consider this activity to be a qualification point in the journey. With the qualification, you want to add them to an account list that is used as the audience for another journey with a different flow for qualified accounts.

>[!NOTE]
>
>If an account is already in the list when the node executes, the action is ignored.

1. Select the _[!UICONTROL Action on]_ **[!UICONTROL Accounts]** option.

1. For _[!UICONTROL Action on accounts]_, choose **[!UICONTROL Add to account list]**.

   ![Select Add to account list](../journeys/assets/node-action-account-add-to-account-list.png){width="500"}

1. For **[!UICONTROL Select live static account list]**, choose the account list where you want to add accounts.

   ![Select Add to account list](../journeys/assets/node-action-account-add-to-account-list-select.png){width="500"}

## Take an action node - Remove from account

**_Static account lists only_**

Within an account journey, remove accounts from a static account list using [a _Take an Action_ node](../journeys/action-nodes.md).

For example, you have a journey path where you send an email and some accounts take various actions as a response. You consider this activity to be a qualification point in the journey. With this qualification, you want to remove them from an account list. This list is used as the audience for another journey that sends additional emails so that you don't duplicate your qualification communications.

>[!NOTE]
>
>If an account is not in the list where it is scheduled for removal, the action is ignored.

1. Select the _[!UICONTROL Action on]_ **[!UICONTROL Accounts]** option.

1. For _[!UICONTROL Action on accounts]_, choose **[!UICONTROL Remove from account list]**.

   ![Select Remove from account list](../journeys/assets/node-action-account-remove-from-account-list.png){width="500"}

1. For **[!UICONTROL Select live static account list]**, choose the account list where you want to remove accounts.

   ![Select Remove from account list](../journeys/assets/node-action-account-remove-from-account-list-select.png){width="500"}
