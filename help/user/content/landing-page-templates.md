---
title: Landing Page Templates
description: Create, manage, and reuse landing page templates - design from scratch, import HTML, duplicate, delete, and track usage for marketing teams in Journey Optimizer B2B Edition.
feature: Landing Pages, Templates, Content
role: User
hide: yes
hidefromtoc: yes
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
exl-id: 107879bb-9020-4cf6-897c-75311817899e
---
# Landing page templates

For an accelerated and improved design process, you can create standalone landing page templates to standardize your page design and content. Marketing strategists can reuse the pages and adapt them to fit use in campaigns and journeys.

## Access and manage landing page templates

To access landing page templates in Adobe Journey Optimizer B2B Edition, go to **[!UICONTROL Content Management]** > **[!UICONTROL Templates]**. Under _[!UICONTROL WEB]_ in the navigation panel, select **[!UICONTROL Landing page templates]**.

The displayed listing page includes all the landing page templates created in the instance listed in table format. The table is sorted by the _[!UICONTROL Modified]_ column by default, with the most recently updated templates at the top. Click the column title to change between ascending and descending.

To search for a template by name, enter a text string in the search bar. 

![Access the landing page templates library and filter by name](./assets/landing-page-templates-list-search.png){width="700" zoomable="yes"}

Click the _Filter_ icon ( ![Filter icon](../assets/do-not-localize/icon-filter.svg) ) at the top left to filter the list according to creation or modification dates, and templates that you have created or modified.

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. Select the columns to display and click **[!UICONTROL Apply]**.

From the displayed list of templates, you can take the actions described in the following sections.

## Create a landing page template

You can create a landing page template from the landing page template listing page by clicking **[!UICONTROL Create template]** at the top right.

1. In the dialog, enter a unique **[!UICONTROL Name]** (required) and a useful **[!UICONTROL Description]** (optional).

   ![Enter initial properties for the new landing page template](./assets/landing-page-templates-create-dialog.png){width="400"}

1. Click **[!UICONTROL Create]**.

The _[!UICONTROL Create your primary landing page]_ page opens and provides options for creating the template: _[!UICONTROL Design from scratch]_, _[!UICONTROL Import HTML]_, or select one of the _[!UICONTROL Saved templates]_.

![Choose how you want to start with your landing page template design](./assets/landing-page-templates-create-design.png){width="800" zoomable="yes"}

After you select the method that you want to use to start your template design, use the visual design space to [design your landing page template content](./landing-page-design.md).

### Design from scratch

Use the visual design space to define the structure of the landing page content. By adding and moving structural components with simple drag-and-drop actions, you can design the shape of the reusable page content within seconds.

>[!NOTE]
>
>The available design tools are equivalent to the tools used for landing page design. The difference is that this content is saved as a template that can be reused across multiple landing pages.

1. From the _[!UICONTROL Design your template]_ home page, select the **[!UICONTROL Design from scratch]** option.

1. [Add structure and content](./landing-page-design.md#add-structure-and-content) to the template.

### Import HTML

Adobe Journey Optimizer B2B Edition allows you to import existing HTML content to design your landing page templates.

{{$include /help/_includes/content-design-import.md}}

   ![import html content in a zip file](./assets/templates-import-zip-file.png){width="500"}  

>[!NOTE]
>
>Using a `<table>` tag as the first layer in an HTML file can cause style loss, including background and width settings in the top layer tag.

You can personalize the imported content as needed with the visual design space.

### Select a design template

{{$include /help/_includes/content-design-select-template.md}}

## View page template details

In the _Landing page templates_ listing page, click the name of a landing page template to open the details page. From here, you can view basic properties for the landing page template and access the visual design space to make changes to the template content.

![Review the landing page template details](./assets/template-details.png){width="700" zoomable="yes"}

* View the template details, such as name and description. These settings can be edited. Click outside of the description box to save changes automatically.

* View the template properties such as created by, created on, last updated on, and modified by.

* Click **[!UICONTROL More]** at the top right to take quick actions on the landing page template, such as _Duplicate_ and _Delete_.

* If there are active alerts (errors and warning for the landing page template), click **[!UICONTROL Alerts]** at the top right to view the information.

   These alerts do not prohibit the use of the landing page template for landing page creation. The information provides visibility for marketers on your team about what might not work and the updates that are required before it can be used for delivery.

## View template used-by references

Within the templates details page, click the **[!UICONTROL Used By]** tab to view details of where this template is used in a landing page.

![Click the Used by tab to check template usage](./assets/template-details-used-by.png){width="400"}

* Clicking the link takes you to the corresponding landing page where the template is used.

* Exit the view at any time by clicking the back arrow, which returns you to the listing page.

## Edit landing page templates

This action can be taken from:

* The details page - Click **[!UICONTROL Edit landing page template]**.
* The listing page - Click the ellipsis (**...**) next to a template and choose **[!UICONTROL Edit]**.

This action takes you to the _Design your template_ page or the visual content editor page (based on the last saved status of the landing page template). From here, you can edit your landing page template content as needed. See [Create a landing page template](#create-a-landing-page-template) for information about the editing options.

## Duplicate landing page templates

You can duplicate a landing page template using either of the following methods:

* From the template details on the right, expand **[!UICONTROL More]** and click **[!UICONTROL Duplicate]**.

   ![Click More to acess Delete and Duplicate actions](./assets/template-details-more-menu.png){width="400"}

* From the _[!UICONTROL Landing page templates]_ listing page, click the ellipsis (...) next to the template and choose **[!UICONTROL Duplicate]**.

In the dialog, enter a useful name (unique) and description. Click **[!UICONTROL Duplicate]** to complete the action.

The duplicated (new) landing page template then appears in the _Landing page templates_ listing.

## Delete landing page templates

A landing page template removal cannot be undone, so check before initiating a delete action. You can delete a landing page template using either of the following methods:

* From the template details on the right, expand **[!UICONTROL More]** and click **[!UICONTROL Delete]**.
* From the _Landing page templates_ listing page, click the ellipsis (...) next to the template and choose **[!UICONTROL Delete]**.

   ![Click ... to acess Duplicate and Delete actions](./assets/templates-list-more-menu.png){width="500"}

This action opens a confirmation dialog. You can abort the process by clicking **[!UICONTROL Cancel]**, or click **[!UICONTROL Delete]** to confirm removal.

## Take bulk actions

From the landing page templates listing page, select multiple templates at a time by selecting the checkboxes to the left. A banner appears at the bottom when you select multiple templates.

![A banner displays the number of selected templates and the Delete icon](./assets/templates-multi-select-banner.png){width="600"}

**[!UICONTROL Delete]** -- You can delete up to a maximum of 20 templates at one time. A confirmation dialog allows you to abort the action or confirm the removal of the templates.

## Author a landing page from a saved template

From the _[!UICONTROL Create your landing page]_ page, use the _Select design template_ section to start building your content from a template.

To start building your content with one of the landing page templates created, use the following steps:

1. Access the visual design space from the _Edit content_ page.

   On the _[!UICONTROL Create your landing page]_ page, the _Sample templates_ tab is selected by default.

1. To use a custom landing page template, select the **[!UICONTROL Saved templates]** tab.

   This tab displays a list of all landing page templates created on the sandbox. You can sort them _By name_, _Last modified_, and _Last created_.

1. Select the template of your choice from the list.

   After selection, this displays a preview of the template. In preview mode, you can navigate between all the templates of one category (sample or saved, depending on your selection) using the right and left arrows.

1. Click **[!UICONTROL Use this template]** at the top right.

1. From the visual content design space, edit your content as needed.
