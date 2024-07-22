---
title: Manage assets with Experience Manager Assets
description: Learn about asset management.
feature: Assets, Integrations
---
# Manage your Experience Manager assets

When Adobe Experience Manager Assets as a Cloud Service is integrated with Adobe Journey Optimizer B2B Edition, you can easily discover and access digital assets for use in your marketing content. As you author your content, the assets are accessible from the _[!UICONTROL Assets]_ item on the left navigation, and when authoring email content for an account journey. You can also upload assets to connected AEM Assets as a Cloud Service repository directly from Adobe Journey Optimizer B2B Edition.

When you use these digital assets, the latest changes in Assets as a Cloud Service automatically propagate to live email campaigns through linked references. If images are deleted in Adobe Experience Manager Assets as a Cloud Service, the images appear with a broken reference in the emails. When assets that are currently used within Journeys are modified or deleted, the journey authors are notified about the image changes and the list of journeys using the image. All changes to the assets must be done in the Adobe Experience Manager Assets central repository.

>[!NOTE]
>
>Currently, only image assets from Adobe Experience Manager Assets are supported in Adobe Journey Optimizer B2B Edition. Changes to the assets must be done from the Adobe Experience Manager Assets central repository, [Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets)

## Access assets

An administrator must add users who need access to Assets to the Assets Consumer Users or/and Assets Users Product profiles.



## Upload assets

To import files to Assets as a Cloud Service, you first need to browse or create the folder to be used for storage. You can then import an asset and add it to your email content. After assets are uploaded, you can [use the image assets as you author content](./assets-overview.md#add-assets-to-your-content).

>[!BEGINTABS]

>[!TAB From the Assets browser]

1. From the Adobe Journey Optimizer B2B Edition home page, select **[!UICONTROL Content Management]** > **[!UICONTROL Assets]** in the left navigation.

1. If there is more than one Assets repository connected, choose the repository where you want to upload the assets.

1. Double-click a folder from the central section or from the tree view to open it.

   You can also click Create folder to create a new folder.

1. From the selected or created folder, click **[!UICONTROL Add Assets]** to upload a new asset to your folder.

1. From the Upload files, click **[!UICONTROL Browse]** and choose if you want to browse files or browse folders.

1. Select the file and click **[!UICONTROL Upload]**. 

   You can manage the asset file using the Experience Manager Assets capabilities, and edit the image file in Adobe Photoshop Express.

>[!TAB From the email designer]

1. While authoring your content in the email designer, drag an image element into the canvas. 

   The properties on the right reflect the image element selection. 

1. Click **[!UICONTROL Import media]** to open the _[!UICONTROL Upload image]_ dialog.

1. If your file system is open to your image file, drag and drop the file on the box in the dialog.

   ![Upload image file to Assets repository](./assets/email-designer-image-upload.png){width="700" zoomable="yes"}

   You can also click the **[!UICONTROL Select a file from your computer]** link and use your file system to locate and select the image file. Click Open and the image file is displayed in the box.

1. Click **[!UICONTROL Import]**.

>[!ENDTABS]
