---
title: Assets
description: Learn about asset management in Journey Optimizer B2B Edition.
feature: Assets, Content
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
---
# Assets

In Adobe Journey Optimizer B2B Edition, assets are typically the images used in creating your journey content. You can use these images within the emails, email templates, and fragments authored in Journey Optimizer B2B Edition through an asset selector or a simple drag-and-drop interface within the visual content editor.

Adobe Journey Optimizer B2B Edition offers marketers access to two types of assets libraries: Adobe Marketo Engage Design Studio and Adobe Experience Manager Assets as a Cloud Service. You may use only the Adobe Marketo Engage Design Studio, or use both libraries configured at the same time (based on the AEM Assets license that you have).

## Asset management

If you are provisioned with a Marketo Engage account and Adobe Experience Manager as a Cloud Services, you have access to the repositories for both Marketo Engage DAM and Adobe Experience Manager Assets as a Cloud Service when your user account has the required permissions. These repositories are separate and not in sync. You can use images from either source, but only one can be enabled in the content editor at a time. An administrator can make the switch from the Marketo Engage DAM to Adobe Experience Manager Assets as a Cloud Service. The _[!UICONTROL Assets]_ item in the left navigation displays the repository that is currently set.

### Adobe Marketo Engage assets

The Adobe Marketo Engage Design Studio assets repository is provided by default with every Journey Optimizer B2B Edition subscription. This means that you have access to any of the image assets stored in Adobe Marketo Engage > [!UICONTROL Design Studio] > [!UICONTROL Images & Files]. You can use this repository as your local assets library, including upload and download assets functions. You can also use these assets within your journey content.

There are built-in guardrails that prevent edits to the Marketo Engage assets from Journey Optimizer B2B Edition, and delete and move operations. These protections ensure that the source assets (Marketo Engage Design Studio) are maintained while allowing seamless read and reuse in Journey Optimizer B2B Edition.

Supported file formats: JPG, JPEG, GIF, PNG, EPS, SVG, RGB

### Adobe Experience Manager Assets as a Cloud Service

Bring marketing and creative workflows together using Adobe Experience Manager Assets. It is natively integrated with Adobe Journey Optimizer B2B Edition, so you can easily access Assets as a Cloud Service to discover and use digital assets. It provides access to your Assets repository for assets that you can use to populate your messages.

Adobe Experience Manager Assets can connect to Adobe Experience Manager Assets as a Cloud Service for centralized asset workspaces that extend your creative system and unify digital assets for experience delivery. Adobe Experience Manager Assets as a Cloud Service offers an easy-to-use cloud solution for efficient Digital Asset Management and Dynamic Media operations. It seamlessly incorporates advanced features, including Artificial Intelligence and Machine Learning.

Learn more in the [Adobe Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/overview).

Adobe Experience Manager Assets can be accessed directly within Adobe Journey Optimizer B2B Edition from the **[!UICONTROL Assets]** item in the left navigation. You can also access assets and folders when designing an email content.

>[!NOTE]
>
>AEM Assets as Cloud Service, and Dynamic Media licenses are pre-requisite for this integration.<br/>
>Depending on your contract and configuration, Adobe Experience Manager Assets as a Cloud Service can be accessed directly from Adobe Journey Optimizer B2B Edition through the left menu Assets section. You can also access assets and folders when designing an email content.

Currently, you can only use images from Adobe Experience Manager Assets in Adobe Journey Optimizer B2B Edition.

## Use assets for content authoring

Use assets as you author your emails, email templates, and visual fragments. The visual content editor UI provides access to the images in your connected asset repositories.

### Choose an asset source

If you have a subscription for Experience Manager Assets as a Cloud Service along with the default Adobe Marketo Engage Design Studio, you can choose image assets from either source. To do that, you must select the image source at the time of creation for a new email, email template, or visual fragment. Or, you can select the image source when you edit the content. The selection applies for the editing experience only, and you can change the image source to access assets from another library when needed.

_**Creating a content resource**_ - To choose an image source when you create an email, email template, or fragment, set the **[!UICONTROL Image source]** in the dialog.

_**Editing a content resource**_ - To choose an image asset source in the visual preview, use the **[!UICONTROL Image source]** setting in the panel on the right.

### Add assets to your content

You can add an image asset as you author your content, depending on your selected image asset source.

>[!BEGINTABS]

>[!TAB Add Marketo Engage image assets]

You can add Marketo Engage assets using either of the following methods:

* Add a structural element, then drag-and-drop assets from the left navigation into the visual canvas.
* Add a structural element, then drag-and-drop the _image_ content type into the structure. In the properties settings on the right, there are two ways to specify the image:
   * Click **[!UICONTROL Browse]** to open the asset selector, where you can choose an image from the Adobe Marketo Engage Design Studio assets library.
   * Click **[!UICONTROL Import media]** to import an asset from your local system. The imported asset is stored within the Assets root folder of your Adobe Marketo Engage Design Studio library.

See [Use assets in your content](./marketo-engage-design-studio.md#use-assets-in-your-content) for more information.
   
To change the image, you can update the source URL for the image in the properties on the right.

>[!TAB Add Experience Manager Assets images]

1. While authoring your email content in the email designer, drag an image element onto the canvas. 

   The properties on the right reflect the image element selection.
   
1. Click **[!UICONTROL Select an asset]** to open the Experience Manager Asset selector.

   Here you can search, filter and access your desired content asset to add to your marketing asset. You can refer to this page for more details on how to use the selector.

   >[!NOTE]
   >
   >If more than one repository is configured, you can use the repository switcher on the Asset selector

1. Select the desired asset to be inserted in the email.

>[!ENDTABS]
