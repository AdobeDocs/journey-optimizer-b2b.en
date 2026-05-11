---
title: Work with Experience Manager Assets
description: Access and use AEM Assets images in content authoring - drag and drop, search, filter, and sync changes automatically in Journey Optimizer B2B Edition.
feature: Assets, Content, Integrations
role: User
exl-id: c6864981-209c-4123-8d3f-24deb07026a0
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: d09181b5-a36a-43de-ba01-36641440bc43
    internal-label: Experience Manager Assets
feature_v2:
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
autotag-review: 2026-03-30T22:38:14.175Z
TQID: https://experienceleague.adobe.com/xcGhfHeUuvmdsUws17Kpb7w3HmM7LaB3C633HiicmJ0
---
# Work with Experience Manager assets

When [!DNL Adobe Experience Manager Assets as a Cloud Service] is integrated with [!DNL Adobe Journey Optimizer B2B Edition], you can easily discover and access digital assets for use in your marketing content. As you author your content, the assets are accessible from the _[!UICONTROL Experience Manager Assets]_ item on the left navigation, and when authoring email content for an account journey.

{{aem-assets-licensing-note}}

When you use these digital assets, the latest changes in [!DNL Assets as a Cloud Service] automatically propagate to live email campaigns through linked references. If images are deleted in [!DNL Adobe Experience Manager Assets as a Cloud Service], the images appear with a broken reference in the emails. When assets that are currently used within account journeys are modified or deleted, the journey authors are notified about the image changes and the list of journeys using the image. All changes to the assets must be done in the [!DNL Adobe Experience Manager Assets] central repository.

When your environment has one or more [Assets repositories connections](../admin/configure-aem-repositories.md), content authors can use [!DNL Experience Manager Assets] as the source for assets when creating an email, email template, or visual fragment.

>[!IMPORTANT]
>
>An administrator must add users who need access to Assets to the Assets Consumer Users or/and Assets Users Product profiles. [Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support#managing-products-and-user-access-in-admin-console){target="_blank"}

## Access AEM Assets images

In the content design space, click the _[!UICONTROL Experience Manager Assets]_  ( ![Experience Manager Assets icon](../../assets/do-not-localize/icon-assets-aem.svg) ) icon in the left sidebar. This changes the tools panel to a list of available assets in the selected repository.

![Click the Assets selector icon to access the image assets](./assets/content-assets-selector-aem-assets.png){width="700" zoomable="yes"}

>[!NOTE]
>
>Currently, only image assets from [!DNL Adobe Experience Manager Assets] are supported in [!DNL Adobe Journey Optimizer B2B Edition]. Changes to the assets must be done from the [!DNL Adobe Experience Manager Assets] central repository. [Learn more](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets){target="_blank"}

### Change the displayed repository

If you have more than one connected AEM repository, click the menu arrow for **[!UICONTROL Repository]** to choose the repository you want to display in the left panel.

![Choose an AEM Assets repository to access the image assets](./assets/content-assets-selector-aem-repo.png){width="700" zoomable="yes"}

There are multiple methods for adding an image asset to the visual canvas.

### Drag and drop an image

1. Browse the image thumbnails displayed in the left panel.

1. Drag the image thumbnail and drop it in the canvas where you what to add the new image component.

   ![Drag and drop an image asset](./assets/content-drag-drop-image-aem-assets.png){width="700" zoomable="yes"}

## Find and select an image

1. Add an image component to the canvas and click **[!UICONTROL Experience Manager Assets]** to open the _[!UICONTROL Select Assets]_ dialog.

   ![Select an asset for the image component](./assets/content-image-component-empty.png){width="600" zoomable="yes"}

1. From the dialog, choose an image using the available tools to locate the asset that you need:
   
   * Change the **[!UICONTROL Repository]** at the top right.

   * Click **[!UICONTROL Manage assets]** at the top right to open the Assets repository in another browser tab and use AEM Assets management tools.

   * Click the _View type_ selector at the top right to change the display to **[!UICONTROL List View]**, **[!UICONTROL Grid View]**, **[!UICONTROL Gallery View]**, or **[!UICONTROL Waterfall View]**.

   * Click the _Sort order_ icon to change the sort order between ascending and descending.

      ![Use tools in the Select Assets dialog to find and select an image asset](./assets/content-select-assets-dialog-aem.png){width="700" zoomable="yes"}

   * Click the **[!UICONTROL Sort by]** menu arrow to change the sort criteria to **[!UICONTROL Name]**, **[!UICONTROL Size]**, or **[!UICONTROL Modified]**.

   * Click the _Filter_ icon on the top left to filter the displayed items according to your criteria.

   * Enter text in the Search field to filter the displayed items for a match of the asset name.

   ![Use the filters and search field to locate the asset](./assets/content-select-assets-dialog-aem-filter.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Select]**.
<!--

## Upload assets

To import files to Assets as a Cloud Service, you first need to browse or create the folder to be used for storage. You can then import an asset and add it to your email content. After assets are uploaded, you can [use the image assets as you author content](./assets-overview.md#add-assets-to-your-content).

1. While authoring your content in the email designer, drag an image element into the canvas. 

   The properties on the right reflect the image element selection. 

1. Click **[!UICONTROL Import media]** to open the _[!UICONTROL Upload image]_ dialog.

1. If your file system is open to your image file, drag and drop the file on the box in the dialog.

   ![Upload image file to Assets repository](./assets/email-designer-image-upload.png){width="700" zoomable="yes"}

   You can also click the **[!UICONTROL Select a file from your computer]** link and use your file system to locate and select the image file. Click Open and the image file is displayed in the box.

1. Click **[!UICONTROL Import]**.
-->
