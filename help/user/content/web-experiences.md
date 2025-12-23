---
title: Web Experiences
description: Create, design, and publish personalized web experiences for account journeys - deliver targeted content modifications to website visitors in Journey Optimizer B2B Edition.
feature: Content, Channels
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
---
# Web experiences

The web channel in Adobe Journey Optimizer B2B Edition empowers you to create personalized experiences directly on your website, helping you connect with customers in meaningful ways. This feature offers a flexible toolkit that you can use to enhance engagement with tailored content and seamlessly integrate it with other channels, such as email and SMS.

Web experiences enable you to:

* Deliver personalized content modifications to targeted website visitors
* Customize website elements such as banners, text, images, and buttons based on account attributes
* Target specific pages or apply changes across multiple pages using URL matching rules
* Track engagement and monitor the impact of your web personalization efforts

## Prerequisites

Before you can create web experiences, ensure that the following requirements are met:

* A product administrator has configured one or more web channels with appropriate URL matching rules. For more information, see [Web channel configurations](../admin/configure-channels-web.md).

* Your website has the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview) (`alloy.js`) implemented for visitor identification and content delivery. Make sure that the Adobe Experience Platform Web SDK version is 2.16 or above.

* You have the necessary [permissions to create and manage web experiences](../admin/user-management.md#b2b-product-permissions) in Journey Optimizer B2B Edition.

* You have the Adobe Experience Cloud [Visual Editing Helper browser extension installed](#install-the-visual-editing-helper-extension) for your web browser. This extension is required to open, author, and preview your web pages reliably into the Journey Optimizer B2B Edition content design space.

   >[!NOTE]
   >
   >Google Chrome and Microsoft Edge are currently the only browsers that support authoring web pages in Journey Optimizer B2B Edition.

## Install the Visual Editing Helper extension

1. Open a new tab in your browser ([!DNL Google Chrome] or [!DNL Microsoft Edge]).

1. Go to the [Google Chrome Web Store](https://chromewebstore.google.com/category/extensions).

   If you are using [!DNL Microsoft Edge], select _Allow extensions_ from other stores on the top banner. Enabling this option allows you to add extensions from the [!DNL Chrome Web Store] to [!DNL Microsoft Edge].

1. Search and navigate to the _[!DNL Adobe Experience Cloud Visual Editing Helper]_ browser extension.

1. Click **[!UICONTROL Add to Chrome]**, and then click **[!UICONTROL Add Extension]** in the confirmation dialog.

   If you are using [!DNL Microsoft Edge], this action adds the extension to [!DNL Edge].

1. Make sure that the [!DNL Visual Editing Helper] browser extension is correctly enabled in your browser toolbar.

The [!DNL Adobe Experience Cloud Visual Editing Helper] is now automatically enabled when a website is opened in the Journey Optimizer B2B Edition visual editor for web experiences. The extension does not have any conditional settings and handles all the settings automatically, including SameSite cookies settings.

>[!NOTE]
>
>Some websites might not open reliably in the Journey Optimizer B2B Edition web editor due to one of the following reasons:
>
>* The website has strict security policies.
>* The website is in an iframe.
>* The customer QA or stage site is not available externally (the site is internal).

## Create a web experience

You can set up web experiences in a journey when you [add a _[!UICONTROL Take an action]_ node](../journeys/action-nodes.md) and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.

1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Personalize web experience]**.

1. Click **[!UICONTROL Create web experience]**.

   <!-- ![Take an action - personalize web experience](assets/journey-node-personalize-web-experience.png){width="700" zoomable="yes"} -->

1. In the _[!UICONTROL Create web experience]_ dialog, enter a useful **[!UICONTROL Name]** and **[!UICONTROL Description]** (optional).

   * Name - Maximum of 100 characters, must be unique, case-insensitive

   * Description - Maximum of 300 characters

   >[!NOTE]
   >
   >Name and description fields support alpha, numeric, and special characters. Reserved characters (`\ / : * ? " < > |`) are **_not allowed_**.

   ![Create web experience dialog](./assets/web-experience-create-dialog.png){width="400"}

<!-- WHat is this for? 1. Properties? -->

1. Set the web experience properties according to how you want to define it.

1. Click the **[!UICONTROL Actions]** tab and select the **[!UICONTROL Web channel]** to use for the web experience.

   The web channel configuration determines where the content modifications are applied based on the configured page matching rules. See [Web channel configurations](../admin/configure-channels-web.md) for more information.

      <!-- ![Selected web channel configuration](assets/journey-node-personalize-web-experience.png){width="700" zoomable="yes"} -->

1. In the right panel, set the web experience properties according to how you want to define and manage it.

   * **[!UICONTROL Visual editor]** - Toggle between the [visual and non-visual editor](./web-experience-design.md#web-design-tools) for the web experience modification design.
   * **[!UICONTROL Visitor redirection]** - Enable this option to [redirect visitors to another existing URL](#redirect-to-url) rather than authoring a new variation in the content tab.

1. Define the web modifications: 

   * Visual editor - Click **[!UICONTROL Edit Content]**.
   * Non-visual editor - Click **[!UICONTROL Add a modification]**.

   The editor opens in the _[!UICONTROL Content]_ tab, where you can define the modifications for your web experience. See [Web experience design](./web-experience-design.md) for detailed information about using the design tools to create the web experience content modifications.

1. When the modification definitions are complete, click the left arrow above the editor to return to the content tab and web experience properties. 

   You can click the left arrow at the very top to return to the journey canvas.

## Edit a web experience

1. Open the journey and select the **[!UICONTROL Personalize web experience]** action node.

1. To make changes to the web channel configuration or content, click **[!UICONTROL Edit web experience]**.

1. Select the **[!UICONTROL Actions]** tab and change the web configuration as needed.

1. Select the **[!UICONTROL Content]** tab and use the visual design tools as needed.

   See [Web experience design](./web-experience-design.md) for detailed information.

1. When the modification definitions are complete, click the left arrow above the editor to return to the content tab and web experience properties. 

   You can click the left arrow at the very top to return to the journey canvas.

## Redirect to URL

When creating a web experience, you can redirect visitors to another existing URL rather than authoring a new variation in the content editor. This option is useful when you want to run a content experiment comparing two different experiences instead of just changing a few elements within a page.

For example, create a web campaign with two treatments:

In Treatment A, author a web experience using the content editor for half of your targeted population.

In Treatment B, select the _[!UICONTROL Redirect to URL]_ option for the other half of the targeted population. Enter the URL of a page with an alternate design that you authored outside of Journey Optimizer B2B Edition.

>[!NOTE]
>
>With this option selected, the website preview is not displayed and the _[!UICONTROL Visual editor]_ toggle is disabled. 

When your web campaign is live, you can track how the web experience that you defined in Journey Optimizer B2B Edition is performing against web experiences that used a redirection to the alternative page.

## Test the web experience

After the content design is complete for the web experience, you can use the _Simulate content_ feature to preview your web page modifications. If you inserted personalized content, you can use test profile data to check how the content is rendered. The simulation tools are available from the _[!UICONTROL Content]_ tab for the web experience, or the content visual design editor.

1. Click **[!UICONTROL Simulate content]** at the top right.

1. Select a test profile.

1. Add a test profile to check your web page using the test profile data.

<!-- This works differently than emails (rely on Marketo data), currently. Will expand when we figure it out -->

## Activate your web experience

Your web experience is activated and made visible to the audience when you publish the journey. Before you activate a web experience through a journey, consider the following:

* If you publish a journey with a web experience that impacts the same pages as another journey that is already live, all the changes are applied to the web pages.

* If multiple journeys update the same elements of your website, the most recently applied change takes precedence.

### Delivery requirements

To enable web experience delivery, the following settings must be defined:

* In the Adobe Experience Platform Data Collection, make sure that you have a datastream defined with the Adobe Journey Optimizer B2B Edition option enabled under the Adobe Experience Platform service.

   This configuration ensures that the Adobe Experience Platform Edge can handle the inbound events correctly. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure)

* In Adobe Experience Platform, make sure that you have one merge policy with the _[!UICONTROL Active-On-Edge Merge Policy]_ option enabled. 

   Select a policy under the Customer > Profiles > Merge Policies Experience Platform menu. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/profile/merge-policies/ui-guide#configure)

   This merge policy is used by Journey Optimizer B2B Edition inbound channels to correctly activate and publish inbound web experiences on the edge. [Learn more](https://experienceleague.adobe.com/en/docs/experience-platform/profile/merge-policies/ui-guide)

### Troubleshooting

You can use the Edge Delivery view within Adobe Experience Platform Assurance to troubleshoot the delivery of Journey Optimizer B2B Edition Web experiences. This plugin enables you to inspect request calls in detail, verify the expected edge calls, and examine profile data. This profile data includes identity maps, segment memberships, and consent settings. You can also review the qualified and unqualified activities for the request.

For more information about the Edge Delivery view in Assurance, see the [Experience Platform documentation](https://experienceleague.adobe.com/en/docs/experience-platform/assurance/view/edge-delivery).

