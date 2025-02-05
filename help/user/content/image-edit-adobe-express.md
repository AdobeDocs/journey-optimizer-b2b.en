---
title: Edit Images with Adobe Express
description: Learn about using Adobe Express to edit images in the Journey Optimizer B2B Edition workspace.
feature: Assets, Content
exl-id: 16909f8f-77db-40f8-acd6-e18ac50c0af9
---
# Edit images with Adobe Express {#edit-images-adobe-express}

>[!CONTEXTUALHELP]
>id="ajo-b2b_assets_edit_adobe_express"
>title="Edit Images in Adobe Express"
>abstract="Easy and intuitive image-editing tools, powered by Adobe Express, are available directly within Adobe Journey Optimizer B2B Edition to increase content velocity."

Adobe Journey Optimizer B2B Edition integrates natively with Adobe Express, and enables you to access a set of Adobe Express image editing tools. You can use these tools to modify the images stored in the Journey Optimizer B2B Edition workspace for the connected Marketo Engage asset repository. The integration provides the following key benefits:

* Increased content reuse by editing and saving new image assets in Journey Optimizer B2B Edition.

* Reduced time and effort to update image assets or create new versions of existing image assets.

>[!NOTE]
>
>Entitlements for Adobe Express editing features are included with all Journey Optimizer B2B Edition subscriptions.

The Adobe Express functions support PNG and JPEG image file formats.

_To modify an image:_

1. Go to the left navigation and click **[!UICONTROL Content Management]** > **[!UICONTROL Assets]**.

  This action opens a listing page with all the assets listed. The _[!UICONTROL Journey Optimizer B2B Edition]_ workspace is selected by default.

1. Locate the image that you want to modify or use as an original to create a new asset.

   * To view the assets by workspace and folder, open the structure by clicking the _Show Folders_ icon at the top left.

   * To sort the table by any of the columns, click the column title. The arrow in the title row indicates the current sort column and order.

   * To search for an image asset within the selected workspace or folder, enter a text string in the search bar.

   ![Browse assets in the Journey Optimizer B2B Edition workspace](./assets/assets-native-workspace-filtered.png){width="800" zoomable="yes"}

1. Click the name of the image asset to open it and view its details.

   >[!TIP]
   >
   >It is a best practice to select [the _[!UICONTROL Used By]_ tab](./marketo-engage-design-studio.md#view-asset-used-by-references) in the image details and review the content where the image is currently used before you proceed to make edits to the image file.

1. In the image _[!UICONTROL Details]_ on the right, click **[!UICONTROL Edit with Adobe Express]**.

    ![Open the image in the Adobe Express editor](./assets/assets-edit-adobe-express.png){width="600" zoomable="yes"}

    If the image is in use, an alert dialog appears to inform you that any changes you make will affect that content. Click **[!UICONTROL Continue]** to proceed to the Adobe Express editor.

    ![An alert provides information about image usage](./assets/assets-edit-adobe-express-usage-alert.png){width="300"}

## Adobe Express Enterprise license

If you have an Enterprise license for Adobe Express, you can access and use the Express editor. These editing capabilities include operations for image adjustments, such as color, brightness, sharpness, contrasts, and cropping. They also include _AI magic_ operations, such as remove backgrounds, insert and remove objects, and erase parts of the image. 

>[!NOTE]
>
>Your Adobe Express Enterprise license must be purchased under the same IMS organization to access these full editor capabilities fro Journey Optimizer B2B Edition. As an individual member of the IMS organization, you need an assigned license in the Adobe Express instance. Otherwise, your Adobe Express access is restricted to the [quick actions on Adobe Express](#quick-actions-in-adobe-express) from Journey Optimizer B2B Edition.

![Open the image in the Adobe Express Enterprise editor](./assets/assets-edit-adobe-express-enterprise-editor.png){width="600" zoomable="yes"}

The [Adobe Express User Guide](https://helpx.adobe.com/express/user-guide.html){target="_blank"} provides detailed information about the available editing capabilities. 

## Quick actions in Adobe Express

If you do not have an Adobe Express Enterprise license, you have access to the Adobe Express quick actions editor. 

1. In the Adobe Express quick actions editor, select any of the image modification functions to alter the image.

    * [**[!UICONTROL Resize image]**](#resize-image)
    * [**[!UICONTROL Remove background]**](#remove-background)
    * [**[!UICONTROL Crop image]**](#crop-image)
    * [**[!UICONTROL Convert to PNG]**](#convert-file-format) (when a JPEG image is loaded)
    * [**[!UICONTROL Convert to JPEG]**](#convert-file-format) (when a PNG image is loaded)

   ![Select an edit type to modify the image](./assets/assets-edit-adobe-express-left-menu.png){width="600" zoomable="yes"}  

1. When you return to the main Adobe Express quick actions editor, click **[!UICONTROL Save]** to save the modified image file in the Journey Optimizer B2B Edition asset workspace using the same file name.

## Resize image

1. Use the resize settings to reduce or expand the image:

   * Select an **[!UICONTROL Aspect ratio]** option. Use a standard size for digital content or choose **[!UICONTROL Custom]** if you want to enter values for **[!UICONTROL Width]** and **[!UICONTROL Height]** to meet your needs.

   * The displayed _[!UICONTROL Original size]_ and _[!UICONTROL Compressed size]_ show the size changes that result if you apply the changes. The **[!UICONTROL Zoom and Crop]** tool allows you to inspect parts of the displayed image more closely.

   * If you want to return the image to its original state, click **[!UICONTROL Reset]**.

   ![Edit with Adobe Express- resize image](./assets/assets-edit-adobe-express-resize-image.png){width="600" zoomable="yes"}

1. When you are satisfied with the result, click **[!UICONTROL Apply]**.

## Remove background

![Edit with Adobe Express- remove background](./assets/assets-edit-adobe-express-remove-background.png){width="600" zoomable="yes"}

Adobe Express performs an automatic background removal to isolate the primary object in the image. If you are satisfied with the result, click **[!UICONTROL Apply]**.

## Crop image

1. Drag the handles on the corners of the image to remove the outer areas that you do not want to include in the image asset.

   ![Edit with Adobe Express- crop image](./assets/assets-edit-adobe-express-crop-image.png){width="600" zoomable="yes"}

1. When you are satisfied with the result, click **[!UICONTROL Apply]**.

## Convert file format

* **[!UICONTROL Convert to JPEG]** - For a PNG image, you can convert the image to a JPEG image file and save it as a new asset in the workspace. 
* **[!UICONTROL Convert to PNG]** - For a JPEG image, you can convert the image to a PNG image file and save it as a new asset in the workspace. 

![Edit with Adobe Express- convert to PNG](./assets/assets-edit-adobe-express-convert-to-png.png){width="600" zoomable="yes"}   

1. Click **[!UICONTROL Apply]**.
