---
title: Intent Data
description: Learn how to assemble and submit keywords for generating intent data for Journey Optimizer B2B Edition.
feature: Setup, Intent, Account Insights
roles: Admin
exl-id: c7f9f6fe-2275-42a4-af80-b5c3d1a82837
---
# Intent data

In Journey Optimizer B2B Edition, the Intent Detection model predicts a solution/product of interest with high enough confidence based on a lead's activity. It also leverages other account co-members' activities, along with tagged content. The intent of a person can be interpreted as the probability of having interest in a product. 

* Levels of intent - Available on known lead, account, and buying group level.
* Types of intent signal -  Keywords, product, and solution

The intent data is used in the [_Intelligent Dashboard_](../dashboards/intelligent-dashboard.md), [_Account details_ page](../accounts/account-details.md), [_Buying group details_ page](../buying-groups/buying-group-details.md), and [_Person details_ page](../accounts/person-details.md). 

![Intent data visualization](../data/assets/intent-data-visualization.png){width="700" zoomable="yes"}

## Prepare your intent mapping data

To activate this feature, create a spreadsheet, such as a Microsoft Excel file, using tabs to define the intent taxonomy. The entire spreadsheet is uploaded as one category that can have multiple products, and each product can have multiple keywords. Use the following definitions for your intent mapping spreadsheet for each category that you want to define:

* Name of the spreadsheet = _Category name_
* Each tab = your product name
* Each tab includes one column = product keywords (maximum 150)

You can download an Excel file to use as a template for preparing your mapping data. To download the template:

1. In the left navigation, choose **[!UICONTROL Administration]** > **[!UICONTROL Configuration]**.

1. Click **[!UICONTROL Intent Mapping]** in the intermediate panel.

1. Click **[!UICONTROL Create category]**.

1. In the dialog, click the **[!UICONTROL Download file template]** link.

   ![Intent data download template file](./assets/intent-data-upload-files.png){width="500"}   

1. Click **[!UICONTROL Cancel]**.

   You can return to upload the prepared file when it is complete.

1. Use the template to define your intent mapping data:

   * Rename the file to reflect your category name, such as _Personalization at scale_.
   * Rename each tabs according to your product names, such as _Journey Optimizer B2B_, _Marketo Engage_, and _Experience Manager_.
   * Add the product keywords for each tab, such as _B2B Marketing_, _Brand Recognition_, and _Lead Engagement_.

   ![Category spreadsheet](./assets/intent-category-spreadsheet.png){width="600" zoomable="yes"}

## Upload a category file

When your spreadsheet is ready, return to the _[!UICONTROL Intent Mapping]_ configuration page and upload the file.

1. Click **[!UICONTROL Create category]**.

1. Drag and drop the file into the _[!UICONTROL Upload files]_ dialog, or click **[!UICONTROL Select a file]** to locate and select the file on your system. 

1. Click **[!UICONTROL Next]**.

   Pre-processing runs to cluster similar keywords, which improves intent detection and avoids keyword dilution. A pulse notification is displayed as soon as this pre-processing is complete (up to 15 minutes, depending on the data).

   ![Pulse notification](./assets/intent-data-upload-files-pre-process.png){width="500"}
   
   The result is displayed in the _Intent Mapping_ page.

   ![Uploaded intent category for approval](./assets/intent-data-category-approve.png){width="600" zoomable="yes"}

## Approve or reject the category

Review the category listing and click **[!UICONTROL Approve]** to activate the keywords for use in the Intelligent Dashboard, Account details page, Buying group details page, and Person details page. Click **[!UICONTROL View all]** to display the full list for each product, or click **[!UICONTROL Download]** to review the full list as an Excel file.

If you are not satisfied with the list, you can click **[!UICONTROL Delete]** to remove the category. You can then make adjustments to your spreadsheet file before starting the upload process again to define that category.

>[!IMPORTANT]
>
>You must approve or reject (delete) the new category before you can add another category or edit a category. 

If you add another category and its taxonomy would impact an existing category, a warning appears. Consider this impact when you decide to approve or reject the category. The product-to-keyword mapping should be the same across all categories if the product is used in more than one category. 

![Alert of existing category impact](./assets/intent-data-category-overlap.png){width="600" zoomable="yes"}
