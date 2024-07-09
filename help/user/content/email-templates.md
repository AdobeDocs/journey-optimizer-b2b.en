---
title: Email templates
description: Learn how to create and edit email templates that can be used to author account journey emails easily and efficiently.
feature: Email Authoring, Content
---
# Email templates

For an accelerated and improved design process, you can create standalone email templates to reuse custom content across Adobe Journey Optimizer B2B Edition account journeys. Through templates, your content-oriented team members can work on email content outside of journeys. Marketing strategists can then reuse and adapt these standalone templates inside their account journeys. For example, one team member is in charge of content only, with no access to account journeys. However, they can create an email template that marketers can select as a starting point for email communications and customize it according to the requirements for the journey.

## Access and manage email templates

To access email templates in Adobe Journey Optimizer B2B edition, go to the left navigation and click **[!UICONTROL Content Management]** > **[!UICONTROL Templates]**. This action opens a listing page with all the email templates created in the instance listed in a table.

You can sort the table by any of the columns by clicking the column title.

To search for a template by name, enter a text string in the search bar.

Customize the columns that you want to display in the table by clicking the _Customize table_ icon on the top right. Select the columns to display and click **[!UICONTROL Apply]**.

From the listing page, you can take the actions described in the following sections.

## Create email templates

You can create a new email template from the email template listing page by clicking **[!UICONTROL Create template]** at the top right.

In the dialog, enter a useful name and description, then click **[!UICONTROL Create]**. 

The _[!UICONTROL Design your template]_ page opens and provides multiple options for creating the template: Design from scratch, Import HTML, or select a design template. 

### Design from scratch

Use the email designer to define the structure of your email content. By adding and moving structural elements with simple drag-and-drop actions, you can design the shape of the reusable email content within seconds.

1. From the _[!UICONTROL Design your template]_ home page, select the **[!UICONTROL Design from scratch]** option.

1. Start designing your content by dragging and dropping components into the canvas to define the structural layout of the email.

   The available design tools are equivalent to the tools used for email authoring. The difference is that this content is then saved as a template that can be reused across multiple send email nodes within account journeys.

### Import HTML

Adobe Journey Optimizer B2B edition allows you to import existing HTML content to design your email templates. This content can be:

* An HTML file with an incorporated style sheet.
* A .zip file that includes an HTML file, the style sheet (.css), and images

   >[!NOTE]
   >
   >There are no constraints on the .zip file structure. However, references must be relative and fit with the tree structure of the .zip folder.

1. From the _[!UICONTROL Design your template]_ home page, select the **[!UICONTROL Import HTML]** option.

1. Drag and drop the HTML or .zip file containing your HTML content and click **[!UICONTROL Import]**.

   After the HTML content is uploaded, your content is in _Compatibility mode_. In this mode, you can only personalize your text, add links, or include assets to your content.

1. To use the email designer content components, click the **[!UICONTROL HTML converter]** tab and click **[!UICONTROL Convert]**.

>[!NOTE]
>
>Using a `<table>` tag as the first layer in an HTML file can cause style loss, including background and width settings in the top layer tag.

You can personalize the imported content as needed with the visual email editor tools.

### Select a design template

From the _[!UICONTROL Design your template]_ home page, use the Select design template section to start building your content from a template. You can use a sample template or a saved email template from your Journey Optimizer B2B Edition instance.

>[!BEGINTABS]

>[!TAB Saved templates]

On the _Design your template_ home page, the _Sample templates_ tab is selected by default. To use a custom template, select the **[!UICONTROL Saved templates]** tab.

The list of all email templates created on the current sandbox displays. You can sort them By name, Last modified, and Last created.

Select the template that you want from the list.

   After selection, this displays a preview of the template. In preview mode, you can navigate between all the templates of one category (sample or saved, depending on your selection) using the right and left arrows.

When the display matches what you want to use, click Use this template at the top right of the preview window.

This action copies the content into the visual content designer, where you can edit the content as needed.

>[!TAB Sample template]

Adobe Journey Optimizer B2B Edition offers a selection of email templates offered out-of-the-box, which can be used for creating emails and email templates.

## Add structure and content

Start designing your content by dragging and dropping structures from the **[!UICONTROL Components]** menu into the canvas to define the layout of your email.

Add as many structures as needed and edit their settings in the element properties on the right.

Select the _n:n column_ component to define the number of columns of your choice (between three and 10). Define the width of each column by moving the arrows at the bottom.

>[!NOTE]
>
>Each column size cannot be under 10% of the total width of the structure component. You remove empty columns only.

Expand the **[!UICONTROL Contents]** section and add as many elements as you need into one or more structure components.

Each component can be further customized using the _[!UICONTROL Settings]_ or _[!UICONTROL Style]_ tabs in the right panel. For example, you can change the text style, padding, or margin of each component.

## Navigate the layers, settings, and style

The following example outlines steps to adjust padding and vertical alignment inside a structure component composed of three columns.

1. Select the structure component directly in the email or using the Navigation tree available in the left menu.

1. From the toolbar, click **[!UICONTROL Select a column]** and choose the one that you want to edit.

   You can also select it from the structure tree. The editable parameters for that column are displayed in the _[!UICONTROL Styles]_ tab.

1. Under **[!UICONTROL Alignment]**, select the _Top_, _Middle_, or _Bottom_ icon.

1. Under **[!UICONTROL Padding]**, define the padding for all sides.

   Select **[!UICONTROL Different padding for each side]** if you want to fine tune the padding. Click the lock icon to break synchronization.

1. If needed, adjust the alignment and padding for the other columns.

1. Save your changes.

## Personalize content

The following example outlines steps to personalize template content using lead/account attributes and system tokens.

1. Select the text component and click the _Add personalization_ icon in the toolbar.

   This action opens the _Edit Personalization_ dialog.

1. Drag and drop one or more tokens onto the blank space.

1. Click **[!UICONTROL Save]**.

## Add fragments

In the visual content editor, the _Fragments_ icon is displayed on the left. The following example outlines steps to add fragments to the template content.

1. To open the fragments listing, click the _Fragments_ icon.

   You can:

   * Sort the listing.
   * Browse, Search, or Filter the listing.
   * Switch between Thumbnail and List views.
   * Refresh the list to reflect any of the recently created fragments.

1. Drag and drop any of the fragments into the structure component placeholder.

   The editor renders the fragment within the section/element of the email structure.

The content of the fragment is dynamically updated within the structure to render a visual of how the content appears in the email.

If you want to add the fragment so that it occupies the entire horizontal layout within the email, add a 1:1 column structure and then drag and drop the fragment into it.

After the email is saved, it appears in the fragment details page > Used By section. Fragments added to an email template are not editable within the template – the content is defined by the source fragment.

## Add assets

In the visual content editor, the _Assets_ icon is displayed on the left. The following example outlines steps to add assets to the template content.

1. To open the assets library, click the _Assets_ icon.

   From the asset selector, you can directly select assets stored in the Assets library.

1. Double-click the folder that contains the assets you need.

1. Drag and drop one or more image assets into a structure component.

## Preview and edit URLs

1. Click the _[!UICONTROL Links]_ tab on the left to display all the URLs of your content to be tracked. 

1. If needed, modify the _Tracking Type_ or _Label_ and add _Tags_.

## View options

Leverage the view and content validation options that are available in the visual email editor.

* Zoom in/out on the content across preset zoom options.

* Switch viewing the content across Desktop, Mobile, or Text-only/Plain-text.
   * Click the _Eye_ icon for content preview across devices.
   * Select one of the out-of-the-box devices or enter custom dimensions to preview the content.

## More options

From the _More options_ selector in the visual content editor, you can take the following actions:

* **Reset template** - Click this option to clear the visual email designer canvas to a blank slate and restart building content.
* **Save as Fragment** - Save all or portions of it as a fragment to be reused across multiple emails or email templates. You provide a name and description for the fragments and it to the list of available fragments. 
* **Change your design** - Return to the _Design your template_ page. From here, you can take any course of action as outlined in the 'Create email templates' section.
* **Export HTML**  - Download the content in the visual canvas to your local system in HTML format packaged as a zip file.

## View email template details

Click the name of an email template to open the email template details page.

Take quick actions on the email template, such as _Duplicate_ and _Delete_, at the top right.

You can also view Alerts (errors and warning for the email template) by clicking the Alerts button. While these alerts do not prohibit use of the email template in an email creation, this information provides visibility for marketers on your team about what might not work and the required updates before it can be used for delivery.

View the email template details, such as name and description. These settings can be edited. Click outside of the description box to save changes automatically.

View the email template properties such as created by, created on, last updated on, and modified by.

## View email template used-by references

Within the email templates details page, click the **[!UICONTROL Used By]** tab to view details of where this email template is used in emails across account journeys.

Emails in Journey Optimizer B2B Edition are embedded and authored within journeys, so the parent journey of the email that uses the template is displayed in references.

Clicking the link takes you to the corresponding email where the email template is used.

Exit the view at any time by clicking the Back arrow, which returns you to the listing page.

## Edit email templates

This action can be taken from:

* The details page - Click **[!UICONTROL Edit email template]**.
* The listing page - Click the ellipsis (...) next to an email template and choose **[!UICONTROL Edit]**.

This action takes you to the _Design your template_ page or the visual content editor page based on the last saved status of the email template. From here, you can edit your email template content as needed. See [Create email templates](#create-email-templates) for information about the editing options.

## Duplicate email templates

You can duplicate an email template using either of the following methods:

* From the email template details on the right, expand **[!UICONTROL More]** and click **[!UICONTROL Duplicate]**.
* From the _Email Templates_ listing page, click the ellipsis (...) next to the template and choose **[!UICONTROL Duplicate]**.

In the dialog, enter a useful name (unique) and description. Click **[!UICONTROL Duplicate]** to complete the action.

The duplicated (new) email template then appears in the _Email Templates_ listing.

## Delete email templates

An email template removal cannot be undone, so check before initiating a delete action.

You can delete an email template using either of the following methods:

* From the template details on the right, expand **[!UICONTROL More]** and click **[!UICONTROL Delete]**.
* From the _Email Templates_ listing page, click the ellipsis (...) next to the template and choose **[!UICONTROL Delete]**.

This action opens a confirmation dialog. You can abort the process by clicking **[!UICONTROL Cancel]**, or click **[!UICONTROL Delete]** to confirm removal.

## Take bulk actions

From the email templates listing page (Content Management > Email templates), select multiple templates at a time by selecting the checkbox to the left. A banner appears at the bottom when you select multiple templates.

You can take the following bulk actions:

### Delete email templates

You can delete up to a maximum of 20 templates at one time.
A confirmation dialog allows you to abort the action or confirm the removal of the templates.

## Author an email from a saved template

From the _Create your email_ screen, use the _Select design template_ section to start building your content from a template.

To start building your content with one of the email templates created, use the following steps:

1. Access the Email Designer from the _Edit content_ page.

   On the _Create your email_ page, the _Sample templates_ tab is selected by default.

1. To use a custom email template, select the **[!UICONTROL Saved templates]** tab.

   This tab displays a list of all email templates created on the sandbox. You can sort them By name, Last modified, and Last created.

1. Select the template of your choice from the list.

   After selection, this displays a preview of the template. In preview mode, you can navigate between all the templates of one category (sample or saved, depending on your selection) using the right and left arrows.

1. Click [!UICONTROL Use this template] at the top right.

1. From the visual content designer, edit your content as needed.
