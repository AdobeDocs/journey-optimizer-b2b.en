---
title: Email authoring
description: Use the email design tools in Journey Optimizer B2B Prime, including email templates, fragments, personalization, dark mode, and validation.
autotag-review: '2026-06-12T22:51:19.543Z'
TQID: 'https://experienceleague.adobe.com/-mtyiJ98caCTuTKaZbzYrYKiQoxolq-hMw7p5h7bNpY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: e7bdffdc-2950-4be5-8c23-84240a995090
    internal-label: Design tools
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Email authoring

In [!DNL Adobe Journey Optimizer B2B Prime], the email design space provides a visual canvas where marketers compose email. The email design tools in the left and top panels (structures, content components, templates, fragments, and more) support building from scratch with drag and drop. You can also choose to start from a template, paste raw HTML, or assemble messages from reusable visual fragments.

>[!IMPORTANT]
>
>For administrator setup of subdomains, authentication, IP pools, and email channel configurations, see [Email deliverability and channel configuration](../admin/configuration-email-deliverability.md).

In [!DNL Journey Optimizer B2B Prime], every email is associated with a _[!UICONTROL Send Email]_ action within a journey. The full workflow from journey design to email definition happens in one continuous experience. When you [add a _Send email_ node](../marketing/action-nodes.md#add-an-action-node) to a person journey, click **[!UICONTROL Create email]** to start the email content design process.

This action launches the email design space, where you can choose how you want to design your email from the following options:

* [Design your email from scratch](#build-from-scratch) using the visual design interface. Build the email layout component by component using drag-and-drop on a blank canvas. This method is best for creating new templates or one-off emails.

* Import HTML into the code editor or work side-by-side with the visual canvas. Full HTML import workflow with .html and .zip uploads is on the Beta roadmap.

* [Select an existing template](#create-from-template) from a list of built-in or custom email templates. This method is best for repeatable email use cases.

<!-- * Upload a design prototype (JPG, PNG, PDF, or Figma export) and have AI Assitant convert it into a responsive HTML email. (Image to HTML (Img2HTML) -->

## Email design tools {#email-design-tools}

* **Top toolbar:** Save, Back, Switch to code editor, preview controls.
* **Left rail:** Structures (column layouts), Contents (text, button, image, divider, social, HTML), Fragments, Templates, Navigation tree (DOM-style hierarchy of the email).
* **Center canvas:** WYSIWYG editor with desktop and mobile preview.
* **Right rail:** Settings and Styles for the currently selected component, including content properties, background, border, padding, and personalization.

## Email design best practices {#design-best-practices}

Following HTML and CSS best practices helps ensure consistent rendering across email clients.

| Approach | Guidance |
| -------- | -------- |
| **Recommended** | Static, table-based layouts · HTML tables and nested tables · Template widths of 600–800 px · Simple inline CSS · Web-safe fonts |
| **Use with care** | Background images (limited client support) · Custom web fonts (always define a fallback font) · Layouts wider than 800 px · Image maps |
| **Avoid** | JavaScript, iframes, or Flash · Embedded audio or video · HTML forms · Div-based layouts |

>[!NOTE]
>
>Email content must also meet applicable digital accessibility requirements. Structure headings logically, provide alt text for all images, and verify color contrast in both light and dark modes.

## Create an email from a journey {#email-from-journey}

1. Click the **[!UICONTROL Edit email]** button to proceed to the email configuration step.
1. On the next screen, select a previously created channel configuration from the **[!UICONTROL Email configuration]** drop-down. Only Active configurations are listed.
1. Enter a Label for the action (visible on the journey canvas) and an internal Email name.
1. Enter the Subject line.
1. Optionally toggle **[!UICONTROL Enable URL tracking]** for this email node.
1. Click **[!UICONTROL Edit content]** to open the email design space.

### The Edit Content screen {#edit-content-screen}

From this screen you confirm sender details (inherited from the channel configuration), set the subject line, and open the email design space to author the body. The preheader is configured in the email design space (see [Setting the preheader](#preheader)).

* **From Name, From Email, BCC:** Inherited from the channel configuration. Read-only on this screen.
* **Subject line:** Required. Personalization is supported.
* **Edit email body:** Opens the email design space.

>[!NOTE]
>
>Email size is capped at 100 KB per ISP best practice. Prime warns you in the editor if you exceed this. Errors (missing subject, missing body, deleted channel configuration) prevent the journey from being activated until they are resolved.

## Designing from scratch {#design-from-scratch}

### Step-by-step: build an email from scratch {#build-from-scratch}

1. From the journey email node, click **[!UICONTROL Edit content]** → **[!UICONTROL Edit email body]**.
1. On the Create your email screen, click **[!UICONTROL Design from scratch]**.
1. Click **[!UICONTROL Confirm]** to open a blank canvas.
1. From the left rail, drag a **[!UICONTROL Structure]** (1-column, 1:1, 2:2, n:n column) onto the canvas.
1. Drag **[!UICONTROL Content]** components into the columns of the structure: Text, Button, Image, Divider, Social, HTML.
1. Click any component on the canvas to select it. The right rail shows Settings and Styles tabs.
1. Use the **[!UICONTROL Settings]** tab to configure component-specific options (text content, image source, button URL).
1. Use the **[!UICONTROL Styles]** tab to configure padding, border, background, font, color.
1. Use the **[!UICONTROL Navigation tree]** icon in the left rail to jump between components in a deeply nested email.
1. Toggle between Desktop and Mobile preview using the icons in the top toolbar.
1. Click **[!UICONTROL Save]** (or use the Save dropdown for additional save options).
1. Click **[!UICONTROL Back]** to return to the email properties.

### Available content components {#content-components}

| Component | Description |
| --------- | ----------- |
| **Text** | Rich text with formatting (bold, italic, font size, color, alignment, lists, links). |
| **Button** | Clickable CTA. Supports background color, border, padding, hover behavior, and personalized URLs. |
| **Image** | Insert from Marketo Design Studio (asset picker). Supports alt text, alignment, link, and click tracking. |
| **Divider** | Horizontal rule with configurable thickness and color. |
| **Social** | Pre-styled social media icons with link configuration. |
| **HTML** | Raw HTML block for advanced content. Useful for embedding hand-coded markup. |

### Structures and column layouts {#structures}

Structures define the email's column grid. Available structures include: 1 column, 1:1 (two equal columns), 1:2 / 2:1 (asymmetric two-column), 1:1:1 (three equal columns), and n:n (custom multi-column). Use structures to control how content reflows on mobile devices — most structures collapse to single-column on narrow screens by default.

>[!TIP]
>
>Keep your email structure simple. Two- or three-column layouts deliver consistent rendering across email clients (especially Outlook and Gmail). Deeply nested structures may render unpredictably.

### Setting the preheader {#preheader}

The preheader is the snippet of text shown after the subject line in inbox previews. In Prime, the preheader is configured on the visual canvas in the email design space — not on the email properties screen alongside the subject line.

1. Open the email in the email design space.
1. In the canvas, locate the preheader area at the top of the email body.
1. Click into the preheader text region and enter your preheader copy.
1. Apply formatting and personalization tokens as needed using the rich-text controls.
1. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Keep your preheader between 40 and 100 characters. It should complement the subject line (not repeat it) and give the recipient an extra reason to open the email.

## Working with templates {#templates}

Templates are reusable email layouts. They speed up email creation, enforce brand consistency, and make team collaboration easier.

### Template types {#template-types}

* **Sample templates (out-of-the-box).** Around 20 ready-made templates covering common use cases (account-based outreach, event invitations, nurture, product announcements). Available immediately for every customer.
* **Saved templates (custom).** Templates created by your team — either built from scratch under **[!UICONTROL Content Management]** → **[!UICONTROL Templates]**, or saved from an existing email using the "Save as template" option.

### Create an email from a template {#create-from-template}

1. From the journey email node, click **[!UICONTROL Edit content]** → **[!UICONTROL Edit email body]**.
1. On the Create your email screen, the **[!UICONTROL Sample templates]** tab is selected by default.
1. Browse the gallery. Use the search box to filter by name or category.
1. Switch to the **[!UICONTROL Saved templates]** tab to view templates created by your team.
1. Click a template thumbnail to preview it.
1. Click **[!UICONTROL Use this template]** to apply it. The template content opens on the canvas in the email design space.
1. Customize text, images, and links. The structure inherited from the template can be modified just like a from-scratch email.
1. Click **[!UICONTROL Save]** → **[!UICONTROL Back]** to return to the email properties.

### Create a reusable template {#create-reusable-template}

1. Navigate to **[!UICONTROL Content Management]** → **[!UICONTROL Templates]**.
1. Click **[!UICONTROL Create template]**.
1. Enter a name and description. Select **[!UICONTROL Email]** as the channel.
1. Click **[!UICONTROL Create]**. The email design space opens for editing.
1. Build the template (from scratch, from an existing template, or by pasting HTML).
1. Optionally enable **[!UICONTROL Governance settings]**:
   * Allow structure and content edition — controls whether email authors can change the template's structure or only its content.
   * Lock specific components — make individual components read-only when used in an email.
1. Click **[!UICONTROL Save]**. The template is now available to all users in the Saved templates gallery.

### Save an email as a template {#save-as-template}

1. Open an existing email in the email design space.
1. In the **[!UICONTROL Save]** dropdown menu, click **[!UICONTROL Save as template]**.
1. Enter a name and description.
1. Optionally configure Governance settings.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>Saved templates and their email content are independent. Editing a template does not retroactively update emails created from it. To propagate changes across many emails, use Visual fragments instead of templates.

## Visual fragments {#visual-fragments}

A visual fragment is a reusable block of content — a header, footer, CTA, legal disclaimer, set of social links — that can be inserted into many emails. When you update a fragment, the change automatically propagates to every email that uses it. Fragments are the recommended way to enforce brand consistency and centralize content updates.

### Create a visual fragment {#create-fragment}

1. Navigate to **[!UICONTROL Content Management]** → **[!UICONTROL Fragments]**.
1. Click **[!UICONTROL Create fragment]**.
1. Select **[!UICONTROL Visual fragment]** as the type. Enter a name and description.
1. Click **[!UICONTROL Create]**. The email design space opens for editing.
1. Drag structures and content components onto the canvas to build the fragment (for example, a 1-column structure with a logo image, a heading, and a navigation link list).
1. (Optional) Mark fields as **[!UICONTROL Editable]** to make them customizable per use:
   * Select a component, then in the right rail open the **[!UICONTROL Editable Fields]** section.
   * Add fields with default values (for example, an image source field with a default logo URL, a text field with a default headline).
   * Email authors using the fragment can override these fields without breaking the fragment's structure.
1. Click **[!UICONTROL Save]**.

### Insert a fragment into an email {#insert-fragment}

1. Open the email in the email design space.
1. In the left rail, click **[!UICONTROL Fragments]**.
1. Browse or search for the desired fragment.
1. Drag the fragment onto the canvas at the desired location.
1. If the fragment has Editable Fields, configure the values in the right rail.
1. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Use fragments for any content that must remain consistent across emails — your branded header, legal footer, social-link bar, unsubscribe block. When the legal team updates the disclaimer, you change one fragment and every email is updated.

## Personalization {#personalization}

Prime uses Handlebars syntax for personalization. Tokens are replaced at send time with values from each recipient's profile data.

### Where you can personalize {#where-you-can-personalize}

* **Subject line** — most common personalization point.
* **Preheader** — set inside the visual canvas; supports profile attribute tokens.
* **Email body text** — first names and other profile attributes inserted inline.
* **Button URLs** — append per-recipient parameters.

>[!NOTE]
>
>Only profile attributes are available in the Personalization Editor in this release.

### Insert a personalization token {#insert-token}

1. In the email design space (or on the email properties screen for the subject line), click the field where you want to insert a token.
1. Click the personalization icon (often labeled **[!UICONTROL Open personalization dialog]** or **[!UICONTROL Add expression]**).
1. In the personalization dialog, browse the schema tree on the left. Profile attributes (first name, last name, email, job title, and other profile fields) are listed.
1. Select an attribute. Prime inserts the corresponding Handlebars expression — for example, `{{profile.firstName}}`.
1. Add a fallback value to handle missing data: `{{profile.firstName | default: "there"}}`.
1. Click **[!UICONTROL Confirm]** or **[!UICONTROL Insert]**. The expression appears inline in the field.

### Common personalization patterns {#personalization-patterns}

Use Handlebars expressions such as the following (personalization uses the same syntax described in [Step-by-step: insert a personalization token](#insert-token)):

* **`{{profile.lastName}}`** — Insert the recipient's last name.
* **`{{profile.jobTitle}}`** — Reference the recipient's job title in body copy.
* **`{{profile.firstName}}, ready to take the next step?`** — Combine token and static text inline.

For a first-name greeting with a fallback when the value is missing, use the `default` helper as shown in the earlier personalization steps (for example, first name with default `"there"`).

### Handlebars helpers {#handlebars-helpers}

Beyond `default`, the personalization editor includes built-in Handlebars helpers for conditional logic, text transformation, and date formatting. Use the editor's function browser to explore available helpers and insert them with the correct syntax.

>[!TIP]
>
>In the email design space, type `{{` directly in any text field to trigger an inline autocomplete dropdown listing available profile attributes — no need to open the full personalization dialog for quick insertions.

### AI-assisted expressions {#ai-personalization}

The AI Assistant in the personalization editor can generate Handlebars expressions from a plain-language description, explain what an existing expression does, and identify potential issues. Use it to accelerate expression authoring, especially for conditional logic or date-formatting helpers.

## Adding assets from Marketo Design Studio {#marketo-assets}

Prime makes your existing Marketo Design Studio assets available in the email design space. You can browse and insert these images into your emails directly from the asset picker.

>[!IMPORTANT]
>
>Asset availability in Prime is based on a **one-time copy** of your assets from Marketo Design Studio. Re-uploading or modifying assets in Marketo after the initial copy will **not** be reflected in Prime. Image uploads directly into Prime are also not supported in this release. Native digital asset management within Prime — including upload, folder navigation, search, and image editing — is part of the Beta scope.

### Supported file types {#asset-file-types}

* **Fully supported (visible in picker, embeddable inline):** JPG, PNG, GIF, WebP.
* **Accessible with caveat:** SVG (with a warning that some email clients do not render SVG).
* **Not supported in this release:** TIFF, PDF, DOCX, XLSX, PPTX, CSS, JS, HTML, TXT, binary files, PSD, AI, INDD.

### Insert an image from Marketo Design Studio {#insert-image}

1. In the email design space, drag an **[!UICONTROL Image]** content component onto the canvas (or click an existing image to replace it).
1. In the right rail, click **[!UICONTROL Marketo Engage Assets]**.
1. The asset picker opens. Browse folders or search by file name.
1. Select the desired asset.
1. Click **[!UICONTROL Select]**. The image is inserted into your email from the copy of the asset available within Prime.
1. In the right rail, configure:
   * Alt text (recommended for accessibility and for clients that block images by default).
   * Alignment.
   * Link target — make the image clickable.
1. Click **[!UICONTROL Save]**.

## Dark mode {#dark-mode}

Dark mode rendering is supported via CSS `prefers-color-scheme` media queries. The email design tools include a dark mode preview and options to define custom styling for supporting email clients — helping you validate that text remains readable, logos are visible, and brand colors hold up against dark backgrounds.

For detailed guidance on previewing, configuring custom dark mode settings, email client support, and testing best practices, see [Dark mode for email content](./email-dark-mode.md).

## Validating email content {#validation}

Before your journey can be activated, the email content must be valid. Prime surfaces content-level alerts on the email and on the journey canvas. This section covers the alerts you may see and how to resolve them.

### Common content alerts and how to resolve them {#content-alerts}

| Alert | What it means | How to resolve |
| ----- | ------------- | -------------- |
| **Subject line is missing** | The Subject line field is empty. | Open the email and enter a subject line on the Edit content screen. Personalization tokens are allowed but the field cannot be empty. |
| **Email body is empty** | The canvas in the email design space has no content. | Click **[!UICONTROL Edit email body]** to open the email design space. Drag at least one Structure and one Content component onto the canvas, then click Save. |
| **Channel configuration not selected** | No Email configuration has been chosen for the email node. | On the email properties screen, select an Active channel configuration from the **[!UICONTROL Email configuration]** drop-down. |
| **Channel configuration deleted** | The previously selected channel configuration has been deleted or is no longer Active. | Open the email properties and select another Active channel configuration. If none are available, an administrator must create or reactivate one. |
| **Email size exceeds 100 KB** | Total email size (HTML, inline CSS, encoded content) is larger than the 100 KB ISP best-practice cap. | Reduce the email size: replace large inline images with externally-hosted images from Marketo Design Studio, remove unused inline CSS, simplify nested structures. |
| **Unresolved personalization token** | A Handlebars token references a profile attribute with no fallback, and the attribute may be missing for some recipients. | Add a fallback using the Handlebars `default` helper as described in [Personalization](#personalization). Alternatively, restrict the journey audience to profiles where the attribute is guaranteed. |
| **Image not loaded** | An image component references an asset that is no longer available. | Click the image, open the asset picker, and re-select the asset from Marketo Design Studio. |

### Review and resolve alerts {#resolve-alerts}

1. Open the journey containing the email node. Email nodes with unresolved alerts are flagged with a red badge on the canvas.
1. Click the email node to open the property rail.
1. Review the **[!UICONTROL Alerts]** section on the property rail. Each alert links to the field or screen where the issue can be resolved.
1. Resolve each alert in turn — for example, enter a missing subject line, select a channel configuration, or open the email design space to fix the content.
1. After resolving all alerts, click **[!UICONTROL Save]** on the email node.
1. Confirm the red badge on the email node clears.

>[!NOTE]
>
>Alerts must be cleared before the journey can proceed. Warnings are non-blocking but should be reviewed (for example, an email that uses a token without a fallback may render with empty values for some recipients).
