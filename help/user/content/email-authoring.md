---
title: Email authoring
description: Learn how to create personalized email content that is used in Account Journeys.
feature: Email Authoring, Content
---

# Email authoring

Use Adobe Journey Optimizer B2B Edition to send email messages to your customers. You can create, personalize, and preview messages in the Email Designer.

## Add an email action in an account journey

You can set up email deliveries in an Account Journey when you add a new _[!UICONTROL Take an action]_ node and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.
1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Send email]**.
1. For the _[!UICONTROL Email source]_, choose **[!UICONTROL Create new email]**.

   Alternatively, you can also select the `Select email from Adobe Marketo Engage` option to use one of the pre-authored emails in Marketo Engage and send it as a part of the Account Journey.

   >[!NOTE]
   >
   >If this is your first time creating an email, make sure that the email channel is configured from within Adobe Marketo Engage. To learn more, see < need link page >.

   ![Take an action - send an email](assets/journey-node-send-email.png){width="700" zoomable="yes"}

1. At the bottom of the _[!UICONTROL Take an action]_ panel, click **[!UICONTROL Create email]**.

1. In the _[!UICONTROL Create new email]_ dialog, enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

   ![Create new email dialog](assets/create-new-email.png){width="400"}

1. Click **[!UICONTROL Create]**.

   In the _[!UICONTROL Email properties]_ section of the email content page, the _[!UICONTROL From email]_ and _[!UICONTROL Reply to address]_ fields are already configured. You can enter the _[!UICONTROL From name]_ and _[!UICONTROL Description]_ (optional).

## Create the email content

Click **[!UICONTROL Add email content]** at the top of the _[!UICONTROL Email]_ preview panel. 

![Click Add email content ](./assets/add-email-content.png){width="700" zoomable="yes"}

This action launches the Email Designer, choose how you want to design your email from the following options:

* [Design your email from scratch](#design-your-email-from-scratch) using the Email Designer interface.
 
* [Import existing HTML content](#import-existing-html-content) from a file or a .zip folder.

* [Select an existing template](#select-a-template) from a list of built-in or custom email templates.

To configure and personalize the subject line with the expression editor, click the Open personalization dialog icon - and you can personalize using the Marketo Engage tokens.

After you create and personalize the email content, you can export the content for validation or for later use. Click **[!UICONTROL Export HTML]** to save the content as a zip file that includes your HTML and assets.


### Design your email from scratch

1. From the Designer home page, select the **[!UICONTROL Design from scratch]** option.

1. Start your content design by draging an item from the **[!UICONTROL Structures]** and dropping it onto the canvas to construct the layout of your email.

1. Add as many items from _Structures_ as you need and edit the settings for each in the pane on the right.

   Select the n:n column component to define the number of columns of your choice (between 3 and 10). You can also define the width of each column by moving the arrows at the bottom of each column.

   Each column size cannot be less than 10% of the total width of the structure component. You cannot remove a column that is not empty.

1. Expand the **[!UICONTROL Contents]** section and add as many elements as you need into one or more structure components. 

1. If needed, you can make additional customizations for each component in the [!UICONTROL Settings] or [!UICONTROL Style] tabs in the right pane.

   For example, you can change the text style, padding or margin of each component.

1. From the Asset picker, you can directly select assets stored in the Assets library.

   Double-click the folder that contains your assets. Drag and drop the items into a structure component.

1. Insert personalization fields to customize your content from profiles attributes, audience memberships, Contextual attributes, and more. 

1. Click **[!UICONTROL Enable condition content]** to add dynamic content and adapt the content to the targeted profiles based on conditional rules.

1. Select the **[!UICONTROL Links]** tab from the left pane to display all the URLs of your content that will be tracked. You can modify their Tracking Type or Label and add Tags if needed.

If needed, you can further personalize your email by clicking Switch to code editor from the advanced menu. This allows you to edit the email source code, for example to add tracking or custom HTML tags.

>[!CAUTION]
>
>You cannot revert back to the visual designer for this email after switching to the code editor.

When your content is done, click **[!UICONTROL Simulate content]** at the top to check rendering. You can choose the desktop or mobile view.

When ready, click Save.

### Import existing HTML content

This content can be:

* An HTML file with an incorporated style sheet
* A .zip folder including an HTML file, the style sheet (.css) and images.

>[!NOTE]
>
>There are no constraints on the .zip file structure. However, references must be relative and fit with the tree structure of the .zip folder.

To import a file containing HTML content:

1. From the Email Designer home page, select [!UICONTROL Import HTML].

1. Drag and drop the HTML or .zip file containing your HTML content and click [!UICONTROL Import].

   When the HTML content upload is complete, your content is in _Compatibility mode_. In this mode, you can only personalize your text, add links, or include assets to your content.



### Select a template

You can choose from:

* Sample templates. The Journey Optimizer interface offers 20 out-of-the-box email templates that you can choose from.

* Saved templates. 
   
* A custom template that you either created from scratch using the Templates menu or saved from an email in a journey or a campaign using the Save as content template option.


To start building your content with one of the sample or saved templates:

Access the Email Designer from the email Edit content screen.

On the Create your email screen, the Sample templates tab is selected by default.

To use a custom template, go to the Saved templates tab.

The list of all content templates created on the current sandbox displays. You can sort them By name, Last modified and Last created.
Select the template of your choice from the list.

Once selected, you can navigate between all the templates of one category (sample or saved depending on your selection) using the right and left arrrows.

Click Use this template on top right of the screen.

Edit your content as needed in the Email Designer.

## Check alerts

As you design your email message content, alerts are displayed in the interface (on top right of the screen) when key settings are missing.

If you do not see this button, no alert has been detected.

Two types of alerts can happen:

* **_Warnings_** that refer to recommendations and best practices, such as:

   * The opt-out link is not present in the email body: adding an unsubscription link into your email body is a best practice.

      >[!NOTE]
      >
      >Marketing-style email messages must include an opt-out link, which is not required for transactional messages. 

   * Text version of HTML is empty: do not forget to define a text version of your email body, as it will be used when HTML content cannot be displayed.

   * Empty link is present in email body: check that all the links in your email are correct. 

   * Email size has exceeded the limit of 100KB: for optimal delivery, make sure the size of your email does not exceed 100KB. 

* **_Errors_** that prevent you from testing or activating the journey/campaign as long as they are not resolved, such as:

   * The subject line is missing: email subject line is mandatory.

   * The email version of the message is empty: this error is displayed when the email content has not been configured.

## Check and test the email

When your message content is defined, you can use test profiles to preview it, send proofs, and control its rendering in popular desktop, mobile, and web-based clients. If you inserted personalized content, you can preview how this content is displayed in the message using test profile data.

To do this, click **[!UICONTROL Simulate content]** and then add a test profile to check your message using the test profile data.

![Simulate the email content to check your design](./assets/email-designer-simulate-content.png){width="700" zoomable="yes"}
