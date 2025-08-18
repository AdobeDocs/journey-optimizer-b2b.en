---
title: Email Message Authoring
description: Learn how to create email content in Adobe Journey Optimizer B2B. Use templates, HTML imports, and AI-powered tools to personalize and optimize your email communications.
feature: Email Authoring, Content Design Tools
role: User
exl-id: 0f4ae644-ade7-49a0-935c-7f4779c25ffb
---
# Email message authoring

After you [add a new<!-- or duplicated --> email asset to a journey action node](./add-email.md), you can define the content for the email message. 

Click **[!UICONTROL Edit email content]** in the _[!UICONTROL Details]_ tab on the right panel.

![Click Edit email content ](./assets/add-email-content.png){width="700" zoomable="yes"}

This action launches the email design tools, where you can choose how you want to design your email from the following options:

* [Design your email from scratch](#design-your-email-from-scratch) using the Email Designer interface.

* [Import existing HTML content](#import-existing-html-content) from a file or a .zip folder.

* [Select an existing template](#select-a-template) from a list of built-in or custom email templates.

After you create and personalize the email content, you can export the content for validation or for later use. Click **[!UICONTROL Export HTML]** to save the content as a .zip file that includes your HTML and assets.

>[!TIP]
>
>Use AI Assistant in Adobe Journey Optimizer B2B Edition, powered by generative AI to elevate your content to the next level. AI Assistant can help you optimize the impact of your deliveries by generating entire emails, targeted text content, and getting AI Assistant recommendations for images that resonate with your audience. [Learn more](./ai-assistant-emails.md)

## Design your email from scratch {#design-from-scratch}

Use the visual content design space to define the structure and content of the email. By adding and moving structural components with simple drag-and-drop actions, you can design the shape of the reusable email content within seconds.

1. From the _[!UICONTROL Design your template]_ home page, select the **[!UICONTROL Design from scratch]** option.
1. [Add structure and content](#add-structure-and-content) to the email message.
1. [Add image assets](#add-assets) to the email message.
1. [Personalize the email content](#personalize-content).
1. [Review and update links](#preview-and-edit-linked-urls).
1. [Test the email](#check-and-test-the-email).

<!-- If needed, you can further personalize your email by clicking **[!UICONTROL Switch to code editor]** from the advanced menu. The code editor allows you to edit the email source code, such as adding tracking or custom HTML tags.

>[!CAUTION]
>
>You cannot revert back to the visual designer for this email after switching to the code editor. -->

When you are satisfied with the content, click **[!UICONTROL Save]**.

## Import existing HTML content

{{$include /help/_includes/content-design-import.md}}

   ![import html content in a zip file](./assets/email-import-zip-file.png){width="500"}

>[!NOTE]
>
>Using a `<table>` tag as the first layer in an HTML file can cause style loss, including background and width settings in the top layer tag.

You can personalize the imported content as needed with the visual email editor tools.

## Select a template

{{$include /help/_includes/content-design-select-template.md}}

>[!NOTE]
>
> Saved templates may have governance (content locking) settings applied to one or more components. The visual designer provides guidelines about locked components when you [author an email from a governed template](./email-authoring-governance.md).

## Add structure and content {#structure-content}

{{$include /help/_includes/content-design-components.md}}

### Add custom CSS

You can add your own custom CSS directly within the email design space. Use custom CSS to apply advanced and specific styling, for greater flexibility and control over the appearance of your content. It is a best practice to add this highest-level styling before you include components such as images, buttons, and text.

With at least one content component in the canvas, select the **[!UICONTROL Body]** component in the left navigation tree to access the custom CSS editor.

>[!NOTE]
>
>If your email message is designed using a [template with locked content](./template-content-governance.md), you cannot add custom CSS to your content. The button label changes to **[!UICONTROL View custom CSS]** and any custom CSS already present in the content is read-only.

![Access the body styles](./assets/email-body-styles.png){width="800" zoomable="yes"}

{{$include /help/_includes/content-design-custom-css.md}}

### Add fragments

{{$include /help/_includes/content-design-use-fragments.md}}

After the email is saved, it appears in the fragment details page when you select the _[!UICONTROL Used By]_ tab in the summary.

### Add assets

{{$include /help/_includes/content-design-assets.md}}

### Navigate the layers, settings, and styles

{{$include /help/_includes/content-design-navigation.md}}

### Personalize content

{{$include /help/_includes/content-design-personalization-email.md}}

>[!NOTE]
>
>If _[!UICONTROL My Tokens]_ are defined for the account journey, you can also use these journey-specific tokens for your email content. See [Custom tokens for email personalization](./personalization-my-tokens.md) for more information.

### Edit linked URL tracking

{{$include /help/_includes/content-design-links.md}}

### View options

Leverage the view and content validation options that are available in the visual email editor.

* Zoom in/out on the content across preset zoom options.

* Switch viewing the content across Desktop, Mobile, or Text-only/Plain-text.
   * Click the _View_ icon for content preview across devices.
   * Select one of the out-of-the-box devices or enter custom dimensions to preview the content.

## More options

From the _[!UICONTROL More ...]_ menu at the top of the email design space, you can take the following actions:

![Click More to access template actions](./assets/email-designer-more-menu.png){width="500"}

* **[!UICONTROL Reset email]** - Click this option to clear the visual email designer canvas to a blank slate and restart building your content.
* **[!UICONTROL Save as fragment]** - Save all or portions of the email as a fragment to be reused across multiple emails or email templates. You provide a name and description for the fragment and save it to the list of available fragments. 
* **[!UICONTROL Change your design]** - Return to the _Design your email_ page. From there, you can choose another template to restart the design process. You can also choose to design the content from scratch with a blank canvas (_Classic mode_) or using a [brand theme](./brand-themes.md) (_Theme mode_).
* **[!UICONTROL Save as content template]** - Save the email body as an email template to be reused across multiple emails or email templates. You provide a name and description for the template and save it to the list of saved email templates.
* **[!UICONTROL Export HTML]** - Download the content in the visual canvas to your local system in HTML format packaged as a zip file.

## Check and test the email {#email-testing}

When your message content is defined, you can use test profiles to preview it, send proofs, and review its rendering in desktop and mobile aspect ratios. If you inserted personalized content, you can preview how this content is displayed in the message using test profile data.

To [preview the email content](./email-simulate-content.md), click **[!UICONTROL Simulate content]** and select a test profile to check your message using the person profile data.

![Simulate the email content to check your design](./assets/email-designer-simulate-content.png){width="700" zoomable="yes"}

You can access additional tools to validate and review the email content:

* [Send a proof](./email-simulate-content.md#send-proofs)
* [Test rendering in email clients](./email-test-rendering.md)
<!-- * Generate a spam report -->
