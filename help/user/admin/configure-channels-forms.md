---
title: Forms Configurations
description: Learn how to configure form presets.
feature: Setup, Channels
role: Admin
autotag-review: '2026-05-27T16:06:59.553Z'
TQID: 'https://experienceleague.adobe.com/GFW5SZ5Z-phoEIE6jTVD7EgwcT1Vx647mjoLXJejbFg'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
    internal-label: Administration
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Forms configurations

Before marketers can [create and publish forms](../content/forms.md) to use in their landing pages, a product administrator must create one or more dedicated presets. Each preset defines the connection endpoint used to send the form submission data, and the dataset used to store the captured data.

When data lands on the streaming endpoint, it is linked with the dataset information. Using the generated source/target connections and source flow, the data is then pushed into the dataset.

>[!BEGINSHADEBOX]

## Prerequisites

To use web forms, you must have one or more _**HTTP API streaming connections**_ defined in Adobe Experience Platform. Make sure that each connection that you want to use meets the following requirements:

* Data type must be set to XDM (not Raw data)
* Authentication must be disabled (non-authenticated connection)

For detailed information about creating a streaming source connections, refer to the [_Experience Platform documentation_](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/streaming/http).

Forms channel configuration in Journey Optimizer B2B Edition requires the following [permissions](../admin/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.

>[!ENDSHADEBOX]

## Form preset configuration guidelines

When creating a preset:

* You can set up multiple presets using different combinations of datasets and streaming connections.

* You can reuse the same dataset or streaming connection across multiple presets.

* Each streaming connection automatically generates resources, such as:

   * _Source connection_ – where the data originates.
   * _Target connection_ – where the data is stored or consumed.
   * _Source flow_ – the pipeline that moves data from the source connection into Experience Platform. It handles mapping, transformation, and validation.

## Create a form preset

1. In the left navigation, go to **[!UICONTROL Administration]** > **[!UICONTROL Channels]**. 

1. Under _[!UICONTROL Form Settings]_ in the navigation panel, select **[!UICONTROL Form presets]**.

   ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"}

1. Click **[!UICONTROL Create form preset]**.

1. Enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional) for the configuration.

   >[!NOTE]
   >
   >Names must begin with a letter (A-Z) and can only contain alphanumeric characters. You can also use underscore `_`, dot `.`, and hyphen `-` characters.

1. Select the **[!UICONTROL Streaming connection]**. 

   This connection is the streaming endpoint used to send the data when a web viewer submits a form. If the needed streaming connection does not appear in the list, verify that the requirements are met.

1. Click the _Select dataset_ ( ![Select dataset icon](../assets/do-not-localize/icon-select-data.svg) ) icon to link a dataset with the form. 

   The dataset is where the form responses are stored and reflected. You can enter a text string to search for a specific dataset or select it from the list.

   ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"}   

   >[!NOTE]
   >
   >Currently only Profile-enabled and Non-Profile-enabled [Adobe Experience Platform datasets](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) are available for selection. One dataset can be selected at a time. System datasets cannot be used for saving form data.

   Select the checkbox for the dataset and click **[!UICONTROL Select]**.

1. Click **[!UICONTROL Save as draft]**. 

## Publish a form preset

1. Click the form preset name to open the configuration page.

   You can make any adjustments to the draft if needed.

1. Click **[!UICONTROL Publish]**.

   When the form preset is listed with a _Published_ status, it is available to use for form creation.
