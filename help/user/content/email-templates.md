---
title: Email Templates
description: Learn how to create and edit email templates that can be used to author account journey emails easily and efficiently.
feature: Email Authoring, Content
exl-id: 4e146802-e3ef-4528-b581-191e28afe86f
---
# Email templates

For an accelerated and improved design process, you can create standalone email templates to reuse custom content across Adobe Journey Optimizer B2B Edition account journeys. Through templates, your content-oriented team members can work on email content outside of journeys. Marketing strategists can then reuse and adapt these standalone templates inside their account journeys. For example, one team member is in charge of content only, with no access to account journeys. However, they can create an email template that marketers can select as a starting point for email communications and customize it according to the requirements for the journey.

## Access and manage email templates

To access email templates in Adobe Journey Optimizer B2B edition, go to the left navigation and click **[!UICONTROL Content Management]** > **[!UICONTROL Templates]**. This action opens a listing page with all the email templates created in the instance listed in a table.

The table is sorted by the _[!UICONTROL Modified]_ column, with the most recently updated templates at the top of the list by default. Click the column title to change between ascending and descending.

To search for a template by name, enter a text string in the search bar. Click the _Filter_ icon at the top left to filter the list according to creation or modification dates, and templates that you have created or modified.

![Access the email templates library and filter by name and dates](./assets/templates-list-search-filter.png){width="700" zoomable="yes"}

Customize the columns that you want to display in the table by clicking the _Customize table_ icon on the top right. Select the columns to display and click **[!UICONTROL Apply]**.

From the listing page, you can take the actions described in the following sections.

## Create email templates

You can create a new email template from the email template listing page by clicking **[!UICONTROL Create template]** at the top right.

1. In the dialog, enter a useful **[!UICONTROL Name]** and **[!UICONTROL Description]** (optional).

   ![Enter initial properties for the new email template](./assets/templates-create-dialog.png){width="400"}

1. Set the initial **[!UICONTROL Image source]**.

   If you have a subscription for Experience Manager Assets as a Cloud Service along with the default Adobe Marketo Engage Design Studio, you can choose image assets from either source. To do that, you must select the image source at the time of creation for an email template, or visual fragment. However, you can also select the image source when you edit the content.

   For more information about image sources, see [Assets](./assets-overview.md).

1. Click **[!UICONTROL Create]**.

The _[!UICONTROL Design your template]_ page opens and provides multiple options for creating the template: _[!UICONTROL Design from scratch]_, _[!UICONTROL Import HTML]_, or _[!UICONTROL Select design template]_.

![Choose how you want to start with your email template design](./assets/templates-create-design.png){width="800" zoomable="yes"}

### Design from scratch {#design-from-scratch}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_template"
>title="Add Structure components"
>abstract="Structure components define the layout of the template. Drag and drop a **Structure** component into the canvas to start designing the content for your template."

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_template"
>title="About Content components"
>abstract="Content components are empty content placeholders that you can use to create the layout of a template."

Use the visual content editor to define the structure of the email content. By adding and moving structural components with simple drag-and-drop actions, you can design the shape of the reusable email content within seconds.

>[!NOTE]
>
>The available design tools are equivalent to the tools used for [email authoring](./email-authoring.md). The difference is that this content is then saved as a template that can be reused across multiple send email nodes within account journeys.

1. From the _[!UICONTROL Design your template]_ home page, select the **[!UICONTROL Design from scratch]** option.

1. [Add structure and content](#add-structure-and-content) to the template.

### Import HTML

Adobe Journey Optimizer B2B Edition allows you to import existing HTML content to design your email templates.

{{$include /help/_includes/content-design-import.md}}

1. To use the email designer content components, click the **[!UICONTROL HTML converter]** tab and click **[!UICONTROL Convert]**.

>[!NOTE]
>
>Using a `<table>` tag as the first layer in an HTML file can cause style loss, including background and width settings in the top layer tag.

You can personalize the imported content as needed with the visual email editor tools.

### Select a design template

{{$include /help/_includes/content-design-select-template.md}}

## Add structure and content

{{$include /help/_includes/content-design-components.md}}

### Navigate the layers, settings, and style

The following example outlines steps to adjust padding and vertical alignment inside a structure component composed of three columns.

1. Select the structure component directly in the email or using the Navigation tree available in the left menu.

1. From the toolbar, click **[!UICONTROL Select a column]** and choose the one that you want to edit.

   ![n:n column component displayed in the canvas](./assets/visual-designer-n-n-column.png){width="800" zoomable="yes"}

   You can also select it from the structure tree. The editable parameters for that column are displayed in the _[!UICONTROL Styles]_ tab.

1. Under **[!UICONTROL Alignment]**, select the _Top_, _Middle_, or _Bottom_ icon.

1. Under **[!UICONTROL Padding]**, define the padding for all sides.

   Select **[!UICONTROL Different padding for each side]** if you want to fine tune the padding. Click the lock icon to break synchronization.

1. If needed, adjust the alignment and padding for the other columns.

1. Save your changes.

### Personalize content

The following example outlines steps to personalize template content using lead/account attributes and system tokens.

1. Select the text component and click the _Add personalization_ icon in the toolbar.

   ![Click the Personalize icon](./assets/visual-designer-personalize-icon.png){width="500"}

   This action opens the _Edit Personalization_ dialog.

1. Click **+** or **...** to add a token to the blank space.

   ![Construct personalized text using tokens](./assets/visual-designer-personalize-dialog.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

### Add fragments

In the visual content editor, the _Fragments_ icon is displayed on the left. The following example outlines steps to add fragments to the template content.

1. To open the fragments listing, click the _Fragments_ icon.

   You can:

   * Sort the listing.
   * Browse, Search, or Filter the listing.
   * Switch between Thumbnail and List views.
   * Refresh the list to reflect any of the recently created fragments.

   ![Select a fragment from the list](./assets/visual-designer-fragments.png){width="700" zoomable="yes"}

1. Drag and drop any of the fragments into the structural component placeholder.

   The editor renders the fragment within the section/element of the email structure.

The content of the fragment is dynamically updated within the structure to show how the content appears in the email.

>[!TIP]
>
>If you want to add the fragment so that it occupies the entire horizontal layout within the email, add a 1:1 column structure and then drag and drop the fragment into it.

After the email is saved, it appears in the fragment details page when you select the _[!UICONTROL Used By]_ tab in the summary. Fragments added to an email template are not editable within the template---the content is defined by the source fragment.

### Add assets

In the visual content editor, select the _Assets_ icon that is displayed on the left. 

>[!NOTE]
>
>If you have a subscription for Experience Manager Assets as a Cloud Service along with the default Adobe Marketo Engage Design Studio, you can choose image assets from the source that is selected in the template details page.

The following example outlines steps to add assets to the template content:

1. To open the assets library, click the _Assets_ icon.

   From the asset selector, you can directly select assets stored in the source library.

1. Add a new asset by dragging and dropping the image asset into a structure component.

1. Replace an image asset by selecting it on the canvas and click **[!UICONTROL Select an asset]** in the image source tools.

   ![Select an asset from the source library](./assets/visual-designer-select-an-asset.png){width="700" zoomable="yes"}

### Preview and edit URLs

1. Click the _[!UICONTROL Links]_ icon on the left to display all the URLs of your content to be tracked.

1. If needed, click the _Edit_ (pencil) icon and modify the _Tracking Type_ or _Label_ and add _Tags_ for a link.

![Click More to access template actions](./assets/visual-designer-links.png){width="500"}

### View options

Leverage the view and content validation options that are available in the visual email editor.

* Zoom in/out on the content across preset zoom options.

* Switch viewing the content across Desktop, Mobile, or Text-only/Plain-text.
   * Click the _Eye_ icon for content preview across devices.
   * Select one of the out-of-the-box devices or enter custom dimensions to preview the content.

### More options

From the _More options_ selector in the visual content editor, you can take the following actions:

![Click More to access template actions](./assets/visual-designer-more-menu.png){width="500"}

* **Reset template** - Click this option to clear the visual email designer canvas to a blank slate and restart building content.
* **Save as Fragment** - Save all or portions of it as a fragment to be reused across multiple emails or email templates. You provide a name and description for the fragments and it to the list of available fragments. 
* **Change your design** - Return to the _Design your template_ page. From here, you can take any course of action as outlined in the 'Create email templates' section.
* **Export HTML**  - Download the content in the visual canvas to your local system in HTML format packaged as a zip file.

## View email template details

In the Templates listing page, click the name of an email template to open the email template details page. From here, you can view basic properties for the email template and access the visual content editor to make changes to the template content.

![Access the email templates library and filter by name and dates](./assets/template-details.png){width="700" zoomable="yes"}

* View the email template details, such as name and description. These settings can be edited. Click outside of the description box to save changes automatically.

* View the email template properties such as created by, created on, last updated on, and modified by.

* Click **[!UICONTROL More]** at the top right to take quick actions on the email template, such as _Duplicate_ and _Delete_.

* If there are active alerts (errors and warning for the email template), click **[!UICONTROL Alerts]** at the top right to view the information.

   While these alerts do not prohibit use of the email template for email creation, this information provides visibility for marketers on your team about what might not work and the required updates before it can be used for delivery.

## View email template used-by references

Within the email templates details page, click the **[!UICONTROL Used By]** tab to view details of where this email template is used in emails across account journeys.

![Click the Used by tab to check template usage](./assets/template-details-used-by.png){width="400"}

Emails in Journey Optimizer B2B Edition are embedded and authored within journeys, so the parent journey of the email that uses the template is displayed in references.

* Clicking the link takes you to the corresponding journey email where the email template is used.

* Exit the view at any time by clicking the Back arrow, which returns you to the listing page.

## Edit email templates

This action can be taken from:

* The details page - Click **[!UICONTROL Edit email template]**.
* The listing page - Click the ellipsis (**...**) next to an email template and choose **[!UICONTROL Edit]**.

This action takes you to the _Design your template_ page or the visual content editor page based on the last saved status of the email template. From here, you can edit your email template content as needed. See [Create email templates](#create-email-templates) for information about the editing options.

## Duplicate email templates

You can duplicate an email template using either of the following methods:

* From the email template details on the right, expand **[!UICONTROL More]** and click **[!UICONTROL Duplicate]**.

   ![Click More to acess Delete and Duplicate actions](./assets/template-details-more-menu.png){width="400"}

* From the _Email Templates_ listing page, click the ellipsis (...) next to the template and choose **[!UICONTROL Duplicate]**.

In the dialog, enter a useful name (unique) and description. Click **[!UICONTROL Duplicate]** to complete the action.

The duplicated (new) email template then appears in the _Email Templates_ listing.

## Delete email templates

An email template removal cannot be undone, so check before initiating a delete action. You can delete an email template using either of the following methods:

* From the template details on the right, expand **[!UICONTROL More]** and click **[!UICONTROL Delete]**.
* From the _Email Templates_ listing page, click the ellipsis (...) next to the template and choose **[!UICONTROL Delete]**.

   ![Click ... to acess Duplicate and Delete actions](./assets/templates-list-more-menu.png){width="500"}

This action opens a confirmation dialog. You can abort the process by clicking **[!UICONTROL Cancel]**, or click **[!UICONTROL Delete]** to confirm removal.

## Take bulk actions

From the email templates listing page, select multiple templates at a time by selecting the checkboxes to the left. A banner appears at the bottom when you select multiple templates.

![A banner displays the number of selected templates and the Delete icon](./assets/templates-multi-select-banner.png){width="600"}

**[!UICONTROL Delete]** -- You can delete up to a maximum of 20 templates at one time. A confirmation dialog allows you to abort the action or confirm the removal of the templates.

## Authoring an email from a saved template

From the _Create your email_ screen, use the _Select design template_ section to start building your content from a template.

To start building your content with one of the email templates created, use the following steps:

1. Access the Email Designer from the _Edit content_ page.

   On the _Create your email_ page, the _Sample templates_ tab is selected by default.

1. To use a custom email template, select the **[!UICONTROL Saved templates]** tab.

   This tab displays a list of all email templates created on the sandbox. You can sort them _By name_, _Last modified_, and _Last created_.

1. Select the template of your choice from the list.

   After selection, this displays a preview of the template. In preview mode, you can navigate between all the templates of one category (sample or saved, depending on your selection) using the right and left arrows.

1. Click **[!UICONTROL Use this template]** at the top right.

1. From the visual content designer, edit your content as needed.
