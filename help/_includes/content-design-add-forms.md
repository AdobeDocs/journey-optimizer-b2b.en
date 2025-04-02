---
title: Content authoring - add forms
description: Reused section about adding forms in landing pages and templates
---
# Content authoring - add forms

A form is a reusable component that can be referenced by multiple landing pages and landing page templates across Adobe Journey Optimizer B2B Edition. It is a block of fields and a submit button that can be pre-created and quickly inserted to make page design quicker and more consistent.

The following example outlines steps to add a form as you design your page.

1. Under the **[!UICONTROL Contents]** section, drag the **[!UICONTROL Form]** item and drop it into a structural component on the page design space.

   ![Drag a Form component into the visual design space](../assets/content-design-shared/content-design-add-form.png){width="600"}

   >[!TIP]
   >
   >To add the form so that it occupies the entire horizontal layout within the email, add a 1:1 column structure and then drag and drop the form into it.

1. Click the _Form_ icon in component toolbar, or use the **[!UICONTROL Embed Form]** properties on the right to select the published form. 

   ![Select the published form](../assets/content-design-shared/content-design-add-form-properties.png){width="600"}

1. If you want to override the default **[!UICONTROL Follow up type]** for the form, change the setting according to the requirements for your page or template.

   This is also know as the _Thank you page_ for the form and this setting determines what happens when a visitor submits the form:

   * **[!UICONTROL Stay on page]** - Choose this option to keep the visitor on the same page when the form is submitted.

   * **[!UICONTROL Landing page]** - Choose this option to select any Journey Optimizer B2B Edition or Marketo Engage landing page as the follow-up.

   * **[!UICONTROL External URL]** - Choose this option to specify any URL as the follow-up page. After the visitor submits the form, the browser loads the designated URL.

      >[!TIP]
      >
      >If you want the use the form for downloading a file, you can specify a URL for the hosted file. With this configuration, the submit botton functions as a download button.
    
    ![Change the follow-up setting](../assets/content-design-shared/content-design-add-form-follow-up.png){width="280"} 

1. If you want to limit the form display by device type, change the **[!UICONTROL Display Options]** setting:

   * **[!UICONTROL Show only on desktop devices]**
   * **[!UICONTROL Show only on mobile devices]**
   * **[!UICONTROL Show on all devices]** (default)

1. If needed, select the **[!UICONTROL Styles]** tab in the right panel to set the form margins within the page.
