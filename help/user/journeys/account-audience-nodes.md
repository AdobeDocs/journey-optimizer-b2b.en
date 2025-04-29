---
title: Account Audience Nodes
description: Learn about the account audience node type that you can use for defining the input for your account journeys in Journey Optimizer B2B Edition.
feature: Account Journeys
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
---
# Account audience journey nodes

The Account audience node defines the input accounts for the journey. When you [create an account journey](./journey-overview.md#create-an-account-journey), it always starts with an _Account audience_ node that defines the input for the journey.

There are two types of input that you can use for this node:

* **[Account audience](../audiences/account-audience-overview.md)** - This is the basic audience that is synched from the Experience Platform Segmentation Service.
* **[Account list](../accounts/account-lists.md)** - This is a collection of named accounts that you can use for targeted journey orchestration. An account list targets named accounts by the defined criteria, such as industry, location, or size of the company.

_To set the audience for the node:_
   
1. Click the **[!UICONTROL Account audience]** node to display the node properties on the right.

   ![Account audience node](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. Choose the input type for accounts to enter the journey:

   * **[!UICONTROL Account audience]**

     Choose this type and then click **[!UICONTROL Add account audience]**.

     In the _[!UICONTROL Add audience]_ dialog, select an audience segment that was previously created and click **[!UICONTROL Add audience]**.

     ![Select an audience segment for the node](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}
     
   * **[!UICONTROL Account list]**

     Choose this type and then click **[!UICONTROL Add account list]**.

     In the _[!UICONTROL Select live account list]_ dialog, select an account list that was previously published and click **[!UICONTROL Save]**.

     ![Select a live account list for the node](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     Go to [Account Lists](../accounts/account-lists.md) for detailed information about creating and publishing account lists.   

_To create an audience segment:_

1. In the left navigation, choose **[!UICONTROL Accounts]** > **[!UICONTROL Audiences]**.

1. Click **[!UICONTROL Create audience]** at the top right.

   ![Create an audience segment](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. Follow the steps described in the [Segmentation Service guide](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/account-audiences){target="_blank"}.
