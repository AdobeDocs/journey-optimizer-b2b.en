---
title: Create email templates
description: Learn how to create email templates in Journey Optimizer B2B Prime — design from scratch, save an email from a journey as a template, or convert a design image to an email template.
badgeBeta: label="Beta" type="informative" tooltip="This feature is par of a limited beta release."
hide: true
---

# Create email templates

You can create an email template in [!DNL Journey Optimizer B2B Edition Prime] in three ways:

* **Design from scratch** — Build a new template in the template library using the visual email design space.
* **Save from a journey email** — Save an email you have authored in a journey as a reusable template.
* **Convert an image** — Upload a design image and use generative AI to convert it into an editable email template.

>[!NOTE]
>
>In this Beta release, only email templates are supported.

## Design a template from scratch {#design-from-scratch}

1. Navigate to **[!UICONTROL Content Management]** > **[!UICONTROL Templates]**.
1. Click **[!UICONTROL Create template]**.
1. Enter a **[!UICONTROL Template name]** and optional **[!UICONTROL Description]**.
1. Optionally add tags to categorize the template.
1. Click **[!UICONTROL Create]** to open the email design space.
1. Design the email layout using structures and content components. For a full reference on available tools, see [Email authoring](email-authoring.md).
1. Optionally configure [content locking](template-content-locking.md) to restrict which parts of the template authors can edit when using it in a journey.
1. Click **[!UICONTROL Save]**.

## Save a journey email as a template {#save-as-template}

When you design an email in a journey that you want to reuse, save it directly to the template library from within the email design space.

1. In the email design space, open the **[!UICONTROL Save]** dropdown at the top of the editor.
1. Select **[!UICONTROL Save as content template]**.
1. Enter a **[!UICONTROL Template name]** and optional **[!UICONTROL Description]**.
1. Optionally add tags and configure [content locking](template-content-locking.md).
1. Click **[!UICONTROL Save]**.

The original journey email is unaffected. The saved template is available in the template library for all users in the sandbox.

## Convert an image to a template {#image-to-template}

[!DNL Journey Optimizer B2B Edition Prime] can convert a static image — such as a mockup from Figma or Photoshop — into an editable email template using generative AI. This eliminates the need to manually rebuild layouts from design files.

### Requirements

Before you begin:

* Your organization must have signed the Generative AI addendum with Adobe.
* You must have the **[!UICONTROL Generate Content]** permission in addition to **[!UICONTROL Manage content templates]**.
* The image file must meet these specifications:
  * Format: JPEG (.jpg, .jpeg) or PNG (.png)
  * Maximum file size: 10 MB
  * Recommended width: 600–800 pixels
  * Clear, high-quality image with readable text and distinct visual elements

>[!IMPORTANT]
>
>The image must not contain personally identifiable information (PII) or sensitive data.

### Convert an image

1. Navigate to **[!UICONTROL Content Management]** > **[!UICONTROL Templates]**.
1. Click **[!UICONTROL Convert Image to Template]** in the header.
1. Enter a **[!UICONTROL Template name]** and optional **[!UICONTROL Description]**.
1. Optionally select a **[!UICONTROL Brand theme]** to apply your brand's colors, fonts, and spacing to the generated output.
1. Upload your image using drag-and-drop or the file browser.
1. Confirm that the image contains no personal data.
1. Review and accept the Adobe Generative AI User Guidelines (first time only).
1. Click **[!UICONTROL Convert]**.

   Conversion typically completes within five minutes. Complex or large images may take up to ten minutes. You can navigate away — the process continues in the background.

1. When conversion is complete, click the template name to preview and edit the generated content.

>[!NOTE]
>
>The result is not displayed automatically. Refresh the page or return to the template library to see the completed template.

### Edit after conversion

The converted template opens in the email design space as a fully editable email. Use the standard design tools to:

* Edit text and add [personalization](email-authoring.md#personalization) tokens.
* Update or replace images and add links.
* Adjust colors, fonts, and spacing.
* Add, remove, or rearrange content components.
* Configure [content locking](template-content-locking.md).

>[!IMPORTANT]
>
>The generative AI produces static HTML based on the visual image. Review all text for accuracy and add personalization, dynamic content, and tracking manually after conversion.

The converted template is automatically saved to the template library when conversion is complete.

### Tips for best results

Use the following guidelines to get the best results from image-to-template conversion:

**Before conversion:**

* Use the highest-resolution version of your design file.
* Design at standard email widths (600–800 pixels) and include the complete layout — header through footer — in a single image.
* Ensure sufficient contrast between text and backgrounds, and use readable font sizes.

**Design for accurate conversion:**

* Use simple, well-structured layouts with clear separation between sections.
* Follow standard email patterns — header, body, calls to action, footer — rather than complex multi-layered designs.
* Keep visual elements distinct so the AI can correctly identify structural boundaries.

**After conversion:**

* Test rendering across email clients and devices before using the template in a journey.
* Verify alignment with brand colors, fonts, and style guidelines.
* Review and enhance accessibility, including image alt text.
