---
title: Expert Mode for Email Template Design
description: Use Expert mode to directly view and edit the raw HTML source of your email template content in the email design space in Journey Optimizer B2B Edition.
feature: Email Authoring, Templates, Content Design Tools
role: User
---
# Expert mode for email template design

Expert mode provides an advanced HTML view that lets experienced users directly view and edit the raw source code for email template content. This mode is ideal when you want to insert sophisticated expressions, such as conditional logic, directly into the source. It is also helpful for making structural adjustments that go beyond what the visual design tools expose.

>[!NOTE]
>
>_Expert mode_ is different from the code editor option that is available when you start a new design. The code editor does not allow you to change to the visual design space. With _Expert mode_, you can toggle back and forth between the HTML source view and the visual design view at any time.

## Important limitations

Before you use _Expert mode_ for [email template authoring](./email-template-authoring.md), make sure that you understand the following limitations:

* **No validation** — The _Expert mode_ HTML editor does not perform syntax checking or layout verification. Review your code carefully before saving.

* **Content updates** — Future system changes may affect or overwrite modifications made to default markup in expert mode. Check your content after product updates to ensure that it renders as expected.

* **Limited support** — Adobe cannot troubleshoot rendering issues or content errors that result from custom code modifications made in _Expert mode_.

* **Preview restrictions** — Content simulation (preview with profiles) is only available in desktop view, not directly from the HTML source view.

## Work in expert mode

In _Expert mode_, you have direct access to the full HTML source of your email template content:

* View and modify any part of the raw HTML markup.
* Insert advanced [personalization expressions](./personalization.md) directly into the source.
* Add [conditional content](./conditional-content.md) logic using expression syntax.
* Add custom HTML attributes, tracking tags, or other markup that is not available through the visual editor controls.

![Expert mode showing raw HTML source of the email content](./assets/email-expert-mode-view.png){width="800" zoomable="yes"}

### Access expert mode

Expert mode is accessible from the toolbar at the top of the visual design space.

1. Open or [create an email template](./email-templates.md#create-an-email-template) and open the design space to edit the content.

1. In the design space, click the _[!UICONTROL HTML]_ ( ![HTML icon](../assets/do-not-localize/icon-code.svg) ) icon in the toolbar.

   <!-- ![Click the HTML icon in the email design toolbar](./assets/email-expert-mode-toolbar.png){width="600" zoomable="yes"} -->

   If this is your first time opening expert mode (or a month or more has elapsed), a warning message is displayed. Review the information and click **[!UICONTROL OK]** to proceed.

   <!-- ![Review the expert mode warning and click OK to continue](./assets/email-expert-mode-warning.png){width="500"} -->

   The design canvas switches to the raw HTML source view.

1. Review the code and add the desired changes to the email content.

   Content simulation and saving are not available in expert mode for compatibility reasons. You can switch back to the desktop view to preview your content and save your changes. Any edits you make are preserved when you switch between the HTML source view and the viisual design view.

1. Save your changes when you exit the design space.

   >[!IMPORTANT]
   >
   >Make sure to enter correct HTML and CSS code; Adobe does not provide syntax validation or support for custom code.

### Return to the visual design view

Click the _[!UICONTROL Desktop]_ icon in the toolbar to switch from expert mode (the HTML source view) to the visual design canvas. Your edits are preserved when you switch views.
