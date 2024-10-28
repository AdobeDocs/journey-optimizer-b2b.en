---
title: Email Template Authoring
description: Learn how to author content email templates that can be used for account journey emails to reuse your designs easily and efficiently.
feature: Email Authoring, Content
---
# Email template authoring

After you [create an email template](./email-templates.md#create-an-email-template), use the visual designer to author the structural and content components in your email template. 

## Add structure and content {#structure-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_template"
>title="Add Structure components"
>abstract="Structure components define the layout of the template. Drag and drop a **Structure** component into the canvas to start designing the content for your template."

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_template"
>title="About Content components"
>abstract="Content components are empty content placeholders that you can use to create the layout of a template."

{{$include /help/_includes/content-design-components.md}}

### Add fragments

In the visual content editor, the _Fragments_ icon is displayed on the left. The following example outlines steps to add fragments to the template content.

1. To open the fragments listing, select the _Fragments_ icon ( ![Fragments icon](../assets/do-not-localize/icon-fragments.svg) ).

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
>If you want the fragment to occupy the entire horizontal layout within the email, add a 1:1 column structure and then drag and drop the fragment into it.

After the email is saved, it appears in the fragment details page when you select the _[!UICONTROL Used By]_ tab in the summary. Fragments added to an email template are not editable within the template --- the source fragment defines the content.

### Add assets

{{$include /help/_includes/content-design-assets.md}}

### Navigate the layers, settings, and styles

{{$include /help/_includes/content-design-navigation.md}}

### Personalize content

{{$include /help/_includes/content-design-personalization.md}}

### Edit linked URL tracking

{{$include /help/_includes/content-design-links.md}}

## View options

Leverage the view and content validation options that are available in the visual designer.

* Zoom in/out on the content across preset zoom options.

* Switch viewing the content across Desktop, Mobile, or Text-only/Plain-text.
   * Click the _Eye_ icon for content preview across devices.
   * Select one of the out-of-the-box devices or enter custom dimensions to preview the content.

### More options

From the _[!UICONTROL More ...]_ menu at the top of the visual designer, you can take the following actions:

![Click More to access template actions](./assets/visual-designer-more-menu.png){width="500"}

* **[!UICONTROL Reset template]** - Click this option to clear the visual email designer canvas to a blank slate and restart building content.
* **[!UICONTROL Save as Fragment]** - Save all or portions of it as a fragment to be reused across multiple emails or email templates. You provide a name and description for the fragments and it to the list of available fragments. 
* **[!UICONTROL Change your design]** - Return to the _Design your template_ page. From there, you can choose to design your template from scratch or use an existing template to restart the design process.
* **[!UICONTROL Export HTML]** - Download the content in the visual canvas to your local system in HTML format packaged as a zip file.
