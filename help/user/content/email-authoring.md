---
title: Email Authoring
description: Learn how to create personalized email content that is used in Account Journeys.
feature: Email Authoring, Content
exl-id: 0f4ae644-ade7-49a0-935c-7f4779c25ffb
---
# Email authoring

Use Adobe Journey Optimizer B2B Edition to send email messages to your customers. You can create, personalize, and preview messages in the Email Designer.

## Add an email action in an account journey

You can set up email deliveries in an Account Journey when you add a _[!UICONTROL Take an action]_ node and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.
1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Send email]**.
1. For the _[!UICONTROL Email source]_, choose **[!UICONTROL Create new email]**.

   Alternatively, you can also select the _[!UICONTROL Select email from Adobe Marketo Engage]_ option to use one of the pre-authored emails in Marketo Engage and send it as a part of the Account Journey.

   >[!NOTE]
   >
   >If you are creating an email for the first time, make sure that the email channel is configured from within Adobe Marketo Engage. To learn more, see [Ensure Email Deliverability](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability) in the Marketo Engage documentation.

   ![Take an action - send an email](assets/journey-node-send-email.png){width="700" zoomable="yes"}

1. At the bottom of the _[!UICONTROL Take an action]_ panel, click **[!UICONTROL Create email]**.

1. In the dialog, enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

   ![Create new email dialog](assets/create-new-email.png){width="400"}

1. Click **[!UICONTROL Create]**.

   In the _[!UICONTROL Email properties]_ section of the email content page, the _[!UICONTROL From email]_ and _[!UICONTROL Reply to address]_ fields are already configured. You can enter values for the _[!UICONTROL From name]_ and _[!UICONTROL Description]_ (optional) fields.

## Create the email content

Click **[!UICONTROL Add email content]** at the top of the _[!UICONTROL Email]_ preview panel. 

![Click Add email content ](./assets/add-email-content.png){width="700" zoomable="yes"}

This action launches the Email Designer, where you can choose how you want to design your email from the following options:

* [Design your email from scratch](#design-your-email-from-scratch) using the Email Designer interface.
 
* [Import existing HTML content](#import-existing-html-content) from a file or a .zip folder.

* [Select an existing template](#select-a-template) from a list of built-in or custom email templates.

To configure and personalize the subject line with the expression editor, click the _Personalization_ icon and add any of the Marketo Engage tokens.

After you create and personalize the email content, you can export the content for validation or for later use. Click **[!UICONTROL Export HTML]** to save the content as a .zip file that includes your HTML and assets.

>[!TIP]
>
>Use AI Assistant in Adobe Journey Optimizer B2B Edition, powered by generative AI to elevate your content to the next level. AI Assistant can help you optimize the impact of your deliveries by generating entire emails, targeted text content, and getting AI Assistant recommendations for images that resonate with your audience. [Learn more](./ai-assistant-emails.md)

### Design your email from scratch {#design-from-scratch}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_email"
>title="Add Structure components"
>abstract="Structure components define the layout of the email. Drag and drop a **Structure** component into the canvas to start designing your email content."

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_landing_page"
>title="Add Structure components"
>abstract="Structure components define the layout of the landing page. Drag and drop a **Structure** component into the canvas to start designing the content of your landing page."

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_email"
>title="About Content components"
>abstract="Content components are empty content placeholders that you can use to create the layout of an email."

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_landing_page"
>title="About Content components"
>abstract="Content components are empty content placeholders that you can use to create the layout of a landing page."

1. From the Designer home page, select the **[!UICONTROL Design from scratch]** option.

{{$include /help/_includes/content-design-components.md}}

If needed, you can further personalize your email by clicking **[!UICONTROL Switch to code editor]** from the advanced menu. The code editor allows you to edit the email source code, such as adding tracking or custom HTML tags.

>[!CAUTION]
>
>You cannot revert back to the visual designer for this email after switching to the code editor.

When your content is done, click **[!UICONTROL Simulate content]** at the top to check rendering. You can choose the desktop or mobile view.

When you are satisfied with the content, click **[!UICONTROL Save]**.

### Import existing HTML content

{{$include /help/_includes/content-design-import.md}}

### Select a template

You can choose from:

* Sample templates. The Journey Optimizer interface offers 20 out-of-the-box email templates that you can choose from.

* Saved templates. 
   
* A custom template that you either created from scratch using the _Templates_ menu or saved from an email in a journey using the _[!UICONTROL Save as content template]_ option.

_To start building your content with one of the sample or saved templates:_

1. Access the _Email Designer_ from the email content editing workspace.

   On the _[!UICONTROL Create your email]_ page, the **[!UICONTROL Sample templates]** tab is selected by default.

1. To use a custom template, select the **[!UICONTROL Saved templates]** tab.

   The list of all content templates created on the current sandbox is displayed. You can sort them By name, Last modified, or Last created.

1. Select the template of your choice from the list.

1. After you select a category, you can navigate between all the templates of that category (sample or saved depending on your selection) using the right and left arrows.

1. Click **[!UICONTROL Use this template]** on the top-right of the page.

1. Edit the content as needed in the _Email Designer_.

## Check alerts

As you design your email message content, alerts are displayed in the interface (top-right of the page) when key settings are missing.

If you do not see this button, there are no detected issues.

Two types of alerts can be detected:

* **_Warnings_** that refer to recommendations and best practices, such as:

   * `The opt-out link is not present in the email body`: adding an unsubscription link into your email body is a best practice.

      >[!NOTE]
      >
      >Marketing-style email messages must include an opt-out link, which is not required for transactional messages. 

   * `Text version of HTML is empty`: do not forget to define a text version of your email body, which is used when HTML content cannot be displayed.

   * `Empty link is present in email body`: check that all the links in your email are correct. 

   * `Email size has exceeded the limit of 100KB`: for optimal delivery, make sure that the size of your email does not exceed 100KB. 

* **_Errors_** that prevent you from testing or activating the journey/campaign as long as they are not resolved, such as:

   * `The subject line is missing`: email subject line is mandatory.

   * `The email version of the message is empty`: this error is displayed when the email content has not been configured.

## Check and test the email {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_email_preview_simulate"
>title="Check how your content is rendering"
>abstract="When your content is defined, you can preview it and check if the rendering is correct for the channel that you are using."

When your message content is defined, you can use test profiles to preview it, send proofs, and control its rendering in popular desktop, mobile, and web-based clients. If you inserted personalized content, you can preview how this content is displayed in the message using test profile data.

To preview the email content, click **[!UICONTROL Simulate content]** and then add a test profile to check your message using the test profile data.

![Simulate the email content to check your design](./assets/email-designer-simulate-content.png){width="700" zoomable="yes"}
