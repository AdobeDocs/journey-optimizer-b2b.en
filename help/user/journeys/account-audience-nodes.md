---
title: Account Audience Nodes
description: Configure account audience nodes with account audiences or account lists to define journey entry points for targeted orchestration in Journey Optimizer B2B Edition.
feature: Account Journeys, Audiences, Account Lists
role: User
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
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

# Account audience journey nodes

The account audience node specifies which accounts enter the journey. When you [create an account journey](./create-publish-journey.md#create-a-journey), the journey always starts with an account audience node that defines its input.

Use one of the following input options for this journey node:

* **[Account audience](../audiences/account-audience-overview.md)** — The account audience represents the basic audience that syncs from Experience Platform Segmentation Service.
* **[Account list](../accounts/account-lists.md)** — The account list is a collection of named accounts that you use for targeted journey orchestration. An account list targets named accounts using defined criteria, such as industry, location, or company size.

## Set the audience for the account audience node

1. Click the **[!UICONTROL Account audience]** node. This action displays the node properties on the right.

   ![Account audience journey node](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. Choose the input type for accounts entering the journey:

   * **[!UICONTROL Account audience]**

     Choose the account audience option. Then, click **[!UICONTROL Add account audience]**.

     In the _[!UICONTROL Add audience]_ dialog, select a previously created audience segment. Then, click **[!UICONTROL Add audience]**.

     ![Select an audience segment for the node](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL Account list]**

     Choose the account list option. Click **[!UICONTROL Add account list]**.

     In the _[!UICONTROL Select live account list]_ dialog, select a published account list. Then, click **[!UICONTROL Save]**.

     ![Select a live account list for the node](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     For more information about creating and publishing account lists, see [Account lists](../accounts/account-lists.md).

## Create an audience segment

1. In the left navigation, select **[!UICONTROL Accounts]** > **[!UICONTROL Audiences]**.

1. Click **[!UICONTROL Create audience]** in the upper-right corner.

   ![Create an audience segment](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. Follow the steps in the [Segmentation Service guide](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/types/account-audiences){target="_blank"}.
