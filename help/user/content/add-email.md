---
title: Add an Email to Your Journey
description: Learn to add, define, and optimize email actions in Adobe Journey Optimizer B2B. Enhance your account journeys with targeted email communications.
feature: Email Authoring, Account Journeys
role: User
exl-id: 21a6ce0f-b59d-4be2-abc3-fda5c6a6334f
---
# Add an email to your journey

Use Adobe Journey Optimizer B2B Edition to send email messages to your customers through account journeys. You can choose to create, personalize, and preview messages in the email design space. Alternatively, you can choose to send an email that is already defined in the connected Marketo Engage instance.

>[!NOTE]
>
>If you are sending an email for the first time, make sure that the email channel is configured from within Adobe Marketo Engage. To learn more, see [Protocols for tracking and email delivery](../start/email-protocols.md).

## Add an email action node in a journey

You can set up email deliveries in a journey when you [add a _[!UICONTROL Take an action]_ node](../journeys/action-nodes.md) and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.

1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Send email]**.

1. For the _[!UICONTROL Email source]_, choose how you want to source the email to send.

   ![Take an action - send an email](assets/journey-node-send-email.png){width="700" zoomable="yes"}

   * Choose **[!UICONTROL Create new email]** to author the email natively in Journey Optimizer B2B Edition. 

     This option allows you to manage the email content natively in Journey Optimizer B2B Edition. Click **[!UICONTROL Create email]** to open the _Create new email_ dialog. You can create a new email content asset or duplicate an existing email content asset.

     +++New email

     When you want to create an email using an empty canvas or an email template, use the _[!UICONTROL New email]_ option. 

     1. In the dialog, choose **[!UICONTROL New email]**.

     1. Enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

        ![Create new email dialog - new email](assets/create-new-email.png){width="400"}

     1. Click **[!UICONTROL Create]**.

        In the _[!UICONTROL Email properties]_ section of the email content page, the _[!UICONTROL From email]_ and _[!UICONTROL Reply to address]_ fields are already configured. You can enter values for the _[!UICONTROL From name]_ and _[!UICONTROL Description]_ (optional) fields.

     1. Click **[!UICONTROL Edit email]** to define the email [settings](#define-the-email-settings) and design the [content](./email-authoring.md).

     +++

     +++Duplicate existing email

     When you want to create an email using an existing email from the current journey or from another journey, use the _[!UICONTROL Duplicate existing email]_ option. You can make changes to the duplicated email according to your objective for the journey node.

     1. In the _[!UICONTROL Create new email]_ dialog, choose **[!UICONTROL Duplicate existing email]**.

     1. For **[!UICONTROL Existing email to duplicate]**, click the _Selection_ icon ( ![Selection icon](../assets/do-not-localize/icon-email-select.svg) ) and select the email that you want to duplicate and use for the journey node.

         You can filter the list of emails by entering a text string in the search field to match the email name.

         ![Select email](assets/create-new-email-duplicate-select-email.png){width="600" zoomable="yes"}

         Select the checkbox for the email that you want to duplicate and click **[!UICONTROL Select]**. 

     1. Enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

         ![Create new email dialog - duplciate existing email](assets/create-new-email-duplicate.png){width="400"}

     1. Click **[!UICONTROL Create]**.

         In the _[!UICONTROL Email properties]_ section of the email content page, the _[!UICONTROL From email]_ and _[!UICONTROL Reply to address]_ fields are already configured. You can enter values for the _[!UICONTROL From name]_ and _[!UICONTROL Description]_ (optional) fields.

     1. If needed, click **[!UICONTROL Edit email]** to modify the email [settings](#define-the-email-settings) and [content](./email-authoring.md).

     +++

   * Choose **[!UICONTROL Select email from Adobe Marketo Engage]** to use one of the pre-authored emails in Marketo Engage and send it as a part of the journey.

      If you have more than one workspace available in the connected Market Engage instance, select the workspace. Then, select the approved email that you want to send for the journey node.

     ![Select Marketo Engage email](./assets/email-select-marketo.png){width="500" zoomable="yes"}

     With this option, the node is set and the email content does not need further definition in the journey.

## Define the email settings

With the **[!UICONTROL Details]** tab selected in the _Summary_ panel on the right, scroll to the bottom to view and set the email options.

![Email settings](./assets/email-summary-details-settings.png){width="600" zoomable="yes"}

| Option | Description |
| ------ | ----------- |
| [!UICONTROL From name] | The sender name used in the email header. Enter the name of the sender as you want it to appear to the recipient. Click the _Personalize_ icon ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) to use a personalization token in the field. |
| [!UICONTROL From email] | The sender address used in the email header. The default value is populated from the [email channel delivery settings](../admin/configure-channels-emails.md#delivery-settings). Click the _Personalize_ icon ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) to use a personalization token in the field. |
| [!UICONTROL Reply-to address] | The sender address used in the email header. The default value is populated from the [email channel delivery settings](../admin/configure-channels-emails.md#delivery-settings) ([!UICONTROL From Label]). Enter the email address that you want to populate if the recipient uses the reply function (it can be different or the same as the sender address). Click the _Personalize_ icon ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) to use a personalization token in the field.|
| [!UICONTROL Subject line] | The text displayed in the subject field for the email. The default value is populated from the text that you entered in the _[!UICONTROL Create new email]_ dialog. You can change the text if needed. Click the _Personalize_ icon ( ![Personalize icon](../assets/do-not-localize/icon-personalize.svg) ) to use a personalization token in the field.<!-- Click the AI Assistant button ( ![AI Assistant icon](../../assets/do-not-localize/icon-gen-ai.svg){width="30" zoomable="no"} ) to generate the subject line based on the current email content.--> |
| [!UICONTROL Operational email] | Select the checkbox if you want to designate the email as operational. Operational emails are excluded from opt-out/unsubscribe lists, and from communication limits. Select this option only when the recipient cannot consider the email message to be an unsolicited commercial message (SPAM).  |
| [!UICONTROL Include view as web page] | Select the checkbox to include a link to a web page that is generated from the email message content. Email messages have more limited capabilities than web pages, so it is useful for JavaScript, extended CSS, and forms. The text used to generate the link is configured in the [email channel delivery settings](../admin/configure-channels-emails.md#delivery-settings) ([!UICONTROL View as web page HTML] and [!UICONTROL View as web page text]).  |
| [!UICONTROL Disable open tracking] | Select the checkbox when you do not want to track email open activity. With the function disabled, email open activity counts are incremented only when a unique person opens the email. You can [manage tracking for email content links](./email-authoring.md#content-authoring---link-tracking) when you design the email body content. |
| [!UICONTROL Preheader] | Select the checkbox to include a preheader. A preheader is the short summary text that is displayed after the subject line in some email clients. It usually provides a short summary of the email, and is typically a single sentence. Enter the summary text in the field<!-- , or click the AI Assistant button ( ![AI Assistant icon](../../assets/do-not-localize/icon-gen-ai.svg){width="30" zoomable="no"} ) to generate summary text based on the current email content -->. |
| [!UICONTROL Fields used as CC addresses] | If available, select up to 25 Lead or Company fields that are set up in Marketo Engage using the `Email` type.  |

## Check alerts

As you design your email message content, alerts are displayed in the interface (top-right of the page) when key settings are missing. If you do not see this button, there are no detected issues.

![Email alerts](./assets/email-alerts.png){width="600" zoomable="yes"}

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
