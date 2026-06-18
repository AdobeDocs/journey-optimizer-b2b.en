---
title: Assets
description: Manage image assets from Journey Optimizer B2B Edition for emails, templates, and vidual fragments.
feature: Assets, Content
role: User
badge: label="Beta" type="Informative"
autotag-review: '2026-06-18T20:11:57.611Z'
TQID: 'https://experienceleague.adobe.com/Xsl4zqpk4xqXuOS85Z5U08tnbv8GWm3FXdqsegPCBI4'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
    internal-label: Assets
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Assets

In [!DNL Adobe Journey Optimizer B2B Prime], assets are typically the images used when designing content to support journeys. You can use these images within your emails, email templates, and visual fragments from the asset selector or a simple drag-and-drop interface within the visual design space.

Supported file formats: JPG, JPEG, GIF, PNG, EPS, SVG, and RGB

>[!NOTE]
>
>In this Beta release, you can choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas. You can also upload additional image assets from the _[!UICONTROL Assets]_ library or content design space. These uploaded assets are available for use only in the [!DNL Adobe Journey Optimizer B2B Prime] instance.
>
>Import of assets from external systems such as the Marketo Engage DAM and access to a pre-populated asset library are not yet available. Future releases are expected to include asset import from existing systems, folder support, and expanded asset management capabilities.

<!-- You can [edit these assets using Adobe Express](./image-edit-adobe-express.md), and move them into folders to organize them for use across your emails, templates, and fragments. -->

The **Assets** library provides access to the centralized repository for storing and managing images and other creative assets. It includes AI-powered capabilities that automatically generate metadata and enable natural-language search.

In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Assets]**.

![Assets library](./assets/dam-asset-library-list-view.png){width="800" zoomable="yes"}

The library supports two layout options:

* **[!UICONTROL List]** — Click the _List view_ ( ![List view icon](../../assets/do-not-localize/icon-falco-list-view.svg) ) icon to display assets in a sortable table with metadata columns.
* **[!UICONTROL Gallery]** — Click the _Gallery view_ ( ![Gallery view icon](../../assets/do-not-localize/icon-falco-gallery-view.svg) ) icon to display assets as a visual thumbnail grid.

## Search for assets {#find-assets}

Use the _[!UICONTROL Search]_ field to find assets by describing what you need in natural language. Search results are based on AI-generated metadata, so you are not limited to searching by file name. 

**Examples:**

* `team members`
* `nature`
* `exercise`

![Selected image from search results in Assets library](./assets/dam-asset-library-select-image.png){width="700" zoomable="yes"}

## View asset details {#view-details}

Select an asset to open its detail view. The detail view displays an AI-generated description, tags and keywords, and additional metadata fields. This information is generated automatically when the asset is uploaded.

Select any asset in list or gallery view to open its detail view on the right. Select the AI metadat tab to view AI-generated description, tags, and metadata. 

![Selected image from search results in Assets library](./assets/dam-asset-library-select-image-metadata.png){width="700" zoomable="yes"}

## Upload an asset {#upload}

1. Click **[!UICONTROL Upload]** to the top right.

1. In the dialog, drag and drop a file from your local system.

   ![Upload an image asset](./assets/dam-upload-assets-dialog.png){width="450"}

   Alternatively, you can click **[!UICONTROL Select file from your computer]** to use you local file system to locate and select the file.

1. Click **[!UICONTROL Upload file]** to confirm and upload the file to the repository.

After the upload completes, the system automatically generates a description, assigns tags and keywords, and extracts visual attributes such as subject and setting. No manual tagging is required. The new image is displayed with a _[!UICONTROL PROCESSING]_ status until this process is complete.

![New image asset in processing status](./assets/dam-asset-library-upload-processing.png){width="700" zoomable="yes"}
