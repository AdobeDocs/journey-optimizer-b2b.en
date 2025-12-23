---
title: Web Experience Design
description: Design web experiences with visual and non-visual editors - add modifications, manage content updates, enable click tracking, and personalize content in Journey Optimizer B2B Edition.
feature: Content Design Tools, Channels
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
---
# Web experience design

After you [create a web experience](./web-experiences.md#create-a-web-experience), use the visual design space to define the modifications that you want to apply to your web pages.

>[!IMPORTANT]
>
>Before you design a web experience, make sure that you have the Adobe Experience Cloud Visual Editing Helper browser extension installed for your web browser. This extension is required to open, author, and preview your web pages reliably into the Journey Optimizer B2B Edition content design space. For more information, see [Install the Visual Editing Helper extension](./web-experiences.md#install-the-visual-editing-helper-extension).

## Web design tools

Journey Optimizer B2B Edition provides two types of editors for creating web modifications:

| Editor | Description | Best for |
| ------ | ----------- | -------- |
| [Visual editor](#visual-editor) | A WYSIWYG (What You See Is What You Get) editor that displays your website and allows you to select and modify elements directly. It requires the [Visual Editing Helper extension](./web-experiences.md#install-the-visual-editing-helper-extension) in Google Chrome or Microsoft Edge web browser. | Making visual changes to visible page elements, such as text, images, buttons, and banners. |
| [Non-visual editor](#non-visual-editor) | A code-based editor for applying modifications that cannot be made through the visual editor. | Targeting elements that are difficult to select visually, applying advanced CSS changes, or making modifications to hidden elements. |

In the web experience properties, use the **[!UICONTROL Visual editor]** option to select the type of editor that you want to use.

<!--add screen -->

## Visual editor {#visual-editor}

The visual editor loads the web pages within an iframe, where you can select elements and apply modifications directly in the page preview.

### Open the visual editor

1. From the web experience details page, click **[!UICONTROL Edit web experience]**.

   The visual editor loads your website based on the web channel configuration.

   <!-- ![Web experience visual editor](./assets/web-experience-visual-editor.png){width="800" zoomable="yes"} -->

1. Use the site navigation bar at the top to browse to the specific page you want to modify.

   >[!NOTE]
   >
   >Ensure that the page matches the URL patterns defined in your web channel configuration. Click View configuration details at the top right to view the URL or page matching rules for the selected web channel configuration.

   <!-- ![View web channel configuration details](./assets/web-experience-view-congiguration-details.png){width="400" zoomable="yes"} -->

### Add new elements

Select a component and then hover over an element that is adjacent to where you want to add it.

Click one of the displayed buttons to place the component:

* ***[!UICONTROL Insert before]**  - Insert the component before the selected element.
* ***[!UICONTROL Insert after]**  - Insert the component after the selected element.

### Modify elements

In the visual editor, use any of the following methods to select an element:

* **_Click directly_** - Click an element in the displayed page to select it. A blue border indicates the selected element.

* **_Browse mode_** - Toggle the _Browse mode_ to navigate to a page on the site without selecting elements. When you find the page and element that you want to modify, toggle back to _Design_ mode and click the element.

<!-- ![Select an element to modify](./assets/web-experience-select-element.png){width="700" zoomable="yes"} -->

### Apply modifications

When you select an element, a contextual toolbar appears with modification options:

| Action | Description |
| ------ | ----------- |
| **[!UICONTROL Edit text]** | Change the text content of the selected element. |
| **[!UICONTROL Edit image]** | Replace the image source or add an image to the element. |
| **[!UICONTROL Edit link]** | Modify the link URL and target behavior. |
| **[!UICONTROL Edit style]** | Apply CSS styling changes such as colors, fonts, sizing, and spacing. |
| **[!UICONTROL Hide]** | Hide the selected element from view. |
| **[!UICONTROL Delete]** | Remove the selected element from the page. |
| **[!UICONTROL Replace]** | Replace the entire selected element with new content. |

<!-- ![Contextual toolbar for selected element to be modified for the web experience](./assets/web-experience-select-element.png){width="700" zoomable="yes"} -->

#### Edit text

1. Select a text element on the page.

1. Click **[!UICONTROL Edit text]** in the contextual toolbar.

1. Enter the new text content.

1. (Optional) Use the [text formatting options](./content-components.md#text), such as bold, italic, and alignment. 

1. Click outside the text element to apply the change.

#### Edit image

1. Select an image element on the page.

1. Click **[!UICONTROL Edit image]** in the contextual toolbar.

1. Choose one of the following options:

   * **[!UICONTROL Select an asset]** - Browse and select an image from your assets library.
   * **[!UICONTROL Enter URL]** - Enter the URL of an externally hosted image.

1. Adjust the image alt text if needed.

   Use the [image styling options](./content-components.md#image) in the right panel as needed.

1. Click **[!UICONTROL Apply]** to save the change.

#### Edit styles

1. Select any element on the page.

1. Click **[!UICONTROL Edit style]** in the contextual toolbar.

1. Modify the available style properties:

   * **Background** - Set background color or image.
   * **Border** - Configure border style, width, and color.
   * **Size** - Adjust width and height.
   * **Spacing** - Set margin and padding values.
   * **Typography** - Change font family, size, weight, and color.

1. Click **[!UICONTROL Apply]** to save the style changes.

For more information about styling options for page elements, see [Content components](./content-components.md).

## Non-visual editor {#non-visual-editor}

Use the non-visual editor when you need to make modifications that cannot be easily accomplished in the visual editor. This code-based approach gives you precise control over element targeting and modification.

<!-- ![Non-visual editor interface](./assets/web-experience-non-visual-editor.png){width="800" zoomable="yes"} -->

### Access the non-visual editor

1. From the web experience visual design space, click **[!UICONTROL Non-visual editor]** in the toolbar.

1. The non-visual editor opens in a side panel, displaying a list of modifications.

### Add a modification

1. Click **[!UICONTROL Add modification]**.

1. Select the modification type:

   | Type | Description |
   | ---- | ----------- |
   | **[!UICONTROL CSS Selector]** | Target elements using a CSS selector string. |
   | **[!UICONTROL Page]** | Apply modifications to page-level elements, such as `<head>` or `<body>`. |

   <!-- | **[!UICONTROL Custom code]** | Insert custom HTML, CSS, or JavaScript. | -->

1. Configure the modification parameters:

   * **[!UICONTROL CSS Selector]** - Enter a valid CSS selector to target specific elements.
   * **[!UICONTROL Action]** - Choose the action to perform (edit, hide, delete, insert, replace).
   * **Con[!UICONTROL ]tent** - Provide the content or styling to apply.

1. Click **[!UICONTROL Add]** to create the modification.

### CSS selector modifications

CSS selector modifications allow you to target elements precisely using standard CSS selector syntax.

**Example selectors:**

| Selector | Targets |
| -------- | ------- |
| `#hero-banner` | Element with ID "hero-banner" |
| `.cta-button` | All elements with class "cta-button" |
| `header nav a` | Links within the navigation, inside the header |
| `[data-offer="premium"]` | Elements with a specific data attribute |

### Custom code modifications

For advanced scenarios, use custom code modifications to inject HTML, CSS, or JavaScript directly into the page.

>[!CAUTION]
>
>Custom code runs in the visitor's browser. Ensure that your code is secure, tested, and does not negatively impact page performance or user experience.

## Manage modifications {#manage-modifications}

>[!CONTEXTUALHELP]
>id="ajo-b2b_web_designer_modifications"
>title="Easily manage all your changes"
>abstract="Using this pane, you can navigate through and manage all the adjustments and styles you added to your web page."

All modifications you create are tracked and can be managed from the modifications panel.

### View modifications

1. Click the **[!UICONTROL Modifications]** icon in the left toolbar to view all modifications.

1. Each modification shows:

   * The target element or selector
   * The modification type (edit, hide, insert, etc.)
   * A preview of the change

### Edit a modification

1. In the modifications list, click the modification you want to edit.

1. Update the modification settings as needed.

1. Click **[!UICONTROL Apply]** to save your changes.

### Delete a modification

1. In the modifications list, hover over the modification you want to remove.

1. Click the _Delete_ ( ![Delete icon](../assets/do-not-localize/icon-delete.svg) ) icon.

1. Confirm the deletion when prompted.

### Reorder modifications

Modifications are applied in the order that they appear in the list. If you have multiple modifications that affect the same element, the order may impact the final result.

1. Drag and drop modifications in the list to change the order.

1. The preview updates to reflect the new modification order.

## Preview modifications

Before publishing, preview how your modifications appear to visitors.

### Device preview

1. Use the device preview options at the top of the visual editor to view your modifications on:

   * Desktop
   * Tablet
   * Mobile

1. The preview updates to show how modifications render on each device size.

### Page navigation

1. Use the URL bar to navigate to different pages within your web channel configuration.

1. Verify that modifications apply correctly to the targeted pages based on your URL matching rules.

## Click tracking for web experiences {#web-click-tracking}

Track user interactions with modified elements to measure engagement and gather insights. The click tracking data is available in your engagement reports and can be used to measure the effectiveness of your web experience modifications.

When your web experience is activated (live), you can also build reports using the Adobe Customer Journey Analytics (which requires a product subscription). To improve your web experience monitoring, you can also track the clicks on any specific element of your website. Tracking allows you to display the number of clicks for that element in the web reports.

For more information about Customer Journey Analytics and building web reports, see the [Customer Journey Analytics documentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing).

1. Select a modified element in the web experience editor, such as an image or link.

1. In the element properties, enable **[!UICONTROL Track clicks]**.

1. Enter a **[!UICONTROL Click event name]** to identify this interaction in your reports.

   <!-- ![Set uo click tracking for web experience click tracking](./assets/web-experience-visual-editor.png){width="600" zoomable="yes"} -->

1. (Optional) Add custom event data to capture with the click.
