---
title: Account Audiences
description: Learn about account audiences and how they enable account-based journeys.
exl-id: f9ba690f-bab2-4c31-9000-f0be1342c8b3
---
# Account audiences

An audience is a set of people who share similar behaviors and/or characteristics. Journey Optimizer B2B Edition uses the account segmentation functionalities found in Adobe Real-Time Customer Data Platform B2B and B2P editions. With account segmentation, users can generate account audiences by leveraging data from any of the B2B entities within the system. These account audiences serve as inputs for Journey Optimizer B2B Edition account journeys, facilitating seamless activation and personalization capability.

Learn more about account audiences and how to define them in the [Adobe Experience Platform Segmentation Service documentation](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/account-audiences).

## Account audience workflow

You can think of Journey Optimizer B2B Edition as an Experience Platform (AEP) destination that does not appear in the destinations catalog. Activate account audiences to Journey Optimizer B2B Edition using the following steps:

1. Create schemas for your data in AEP.
1. Ingest your data into AEP.
1. Create an account segment to evaluate your data.
1. Activate your evaluated data to Journey Optimizer B2B Edition.

In Journey Optimizer B2B Edition, account audiences are used as an input for account-based journeys, allowing you to target the people within those accounts. For example, you can use account audiences to retrieve records of all the accounts that do not have contact information for any people with the title Chief Operating Officer (COO) or Chief Marketing Officer (CMO).

Journey Optimizer B2B Edition allows you to build Adobe Experience Platform (AEP) account audiences directly from the left navigation, and incorporate them into your account journeys.

![Access account audiences](./assets/account-audiences-browse.png){width="800" zoomable="yes"}

## Create an account audience

Define the account audience by creating an account segmentation. You have the option to create the account segmentation directly within the Journey Optimizer B2B Edition application, or you can use the [Segment Builder UI](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder). The following are the steps that you can use to create an account segmentation in Journey Optimizer B2B Edition.

1. In the left navigation, choose **[!UICONTROL Accounts]** > **[!UICONTROL Audiences]**.

1. Click **[!UICONTROL Create audience]** at the top right.

1. Build the segment definition.

   The account attributes and audiences are displayed on the left navigation bar. Under the _[!UICONTROL Attributes]_ tab, you can add both Platform-created and custom attributes. Drag each attribute to build the logic for the segment.

   >[!TIP]
   >
   >When creating an account audience, be aware that events are listed under _[!UICONTROL People]_, because these attributes are associated with people.<br/>
   >
   >Under the _[!UICONTROL Audiences]_ tab, you can add previously created people-based audiences to build off of when creating your own account audience.

   The following example defines audience created using `Country Code`, `Revenue Amount`, and `Market segment`. The query in English would be, "I want all accounts in the US who are in the Finance Segment whose revenue exceeds $1M."

   ![account audience segment builder example](./assets/audience-segment-builder-US-finance-1M.png){width="700" zoomable="yes"}

   >[!IMPORTANT]
   >
   >The `Account Name` attribute for account records must contain a value to be included in account journeys. If this attribute is empty (null), the account record is excluded.<br/>
   >To ensure that only accounts with a non-empty Account Name are included, add the **[!UICONTROL Account Name]** attribute and select _[!UICONTROL exists]_ as the match condition.<br/>
   >![Account Name attribute exists](./assets/audience-segment-builder-account-name-exists.png){width="500"}
   ><br/>If you are using a custom attribute for the account name, use your custom attribute name in place of _[!UICONTROL Account Name]_.

1. Click **[!UICONTROL Save and Close]** at the top right.

To activate your account audience for Journey Optimizer B2B Edition, you must [add it to an account journey](../journeys/journey-overview.md#add-the-account-audience-for-your-journey) and [publish the journey](../journeys/journey-overview.md).
