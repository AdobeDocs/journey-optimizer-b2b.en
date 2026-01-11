---
title: Web Experience Design
description: Design web experiences with visual and non-visual editors - add modifications, manage content updates, enable click tracking, and personalize content in Journey Optimizer B2B Edition.
feature: Content Design Tools, Channels
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
---
# Web experience design

After you [create a web experience](./web-experiences.md#create-a-web-experience), use the content design space to define the modifications that you want to apply to your web pages.

>[!BEGINSHADEBOX]

**Prerequisites**

Before you can design web experiences, ensure that the following requirements are met:

* A product administrator has configured one or more web channels to define the URLs (pages) to be included for a web experience. For more information, see [Web channel configurations](../admin/configure-channels-web.md).

* Your website has the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview) (`alloy.js`) implemented for visitor identification and content delivery. Adobe Experience Platform Web SDK version 2.16 or above is required.

* You have the necessary [permissions](../admin/user-management.md#b2b-product-permissions) to create and manage web experiences in a journey:
   * _[!UICONTROL Campaigns]_ > _[!UICONTROL Manage Campaigns]_ - Required to add or update a web personalization action node.
   * _[!UICONTROL Campaigns]_ > _[!UICONTROL View Campaigns]_ - Required to view details for a Web personalization action nodes.
   
>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Before you design a web experience, make sure that you have the Adobe Experience Cloud Visual Editing Helper browser extension installed for your web browser. This extension is required to open, author, and preview your web pages reliably into the Journey Optimizer B2B Edition web experience design space.<br/>
>
>Google Chrome and Microsoft Edge are currently the only browsers that support the extension and authoring web experiences in Journey Optimizer B2B Edition. For more information, see [Install the Visual Editing Helper extension](./web-experiences.md#install-the-visual-editing-helper-extension).

## Web experience editors

Journey Optimizer B2B Edition provides two types of editors for designing web modifications:

| Editor | Description | Best for |
| ------ | ----------- | -------- |
| [Visual editor](#visual-editor) | A WYSIWYG (_What You See Is What You Get_) editor that displays your website and allows you to select and modify elements directly. It requires the [Visual Editing Helper extension](./web-experiences.md#install-the-visual-editing-helper-extension) in Google Chrome or Microsoft Edge web browser. | Making visual changes to visible page elements, such as text, images, buttons, and banners. |
| [Non-visual editor](#non-visual-editor) | A code-based editor for applying modifications that cannot be made through the visual editor. | Targeting elements that are difficult to select visually, applying advanced CSS changes, or making modifications to hidden elements. |

In the web experience properties, use the **[!UICONTROL Visual editor]** option to determine the type of editor. Enable the option to use the visual editor, or disable it to use the non-visual editor.

![Visual editor option enabled](./assets/web-experience-design-visual-editor-option.png){width="400"}

## Visual editor {#visual-editor}

>[!CONTEXTUALHELP]
>id="ajo-b2b_web_experience_browse"
>title="Use the Browse mode"
>abstract="In this mode, you can navigate to the exact page that you want to personalize for the selected web channel configuration."

The visual editor loads the web pages within an iframe, where you can select elements and apply modifications directly in the page preview. Complete the following steps to use the visual editor for designing your web experience:

1. With the _[!UICONTROL Content]_ tab displayed in the web experience details page, click **[!UICONTROL Edit web experience]** in the right panel.

   The visual editor loads your website based on the web channel configuration.

   ![Web experience visual editor](./assets/web-experience-design-visual-editor.png){width="800" zoomable="yes"}

1. If needed, click **[!UICONTROL Browse]** at the top right and use the site navigation bar to load the specific page that you want to modify.

   You can also enter the page URL in the field at the top.

   >[!NOTE]
   >
   >Ensure that the loaded page matches the URL patterns defined in your web channel configuration. Click **[!UICONTROL View configuration details]** at the top right to view the URL or page matching rules for the selected web channel configuration.

   ![Browse mode in the visual editor](./assets/web-experience-design-visual-editor-browse.png){width="700" zoomable="yes"}

    <!-- If the web channel configuration is defined using page matching rules, use the left and right arrows to sequence through the matched pages -- right now these buttons don't do anything -->

    Click **[!UICONTROL Design]** at the top right to load the page in the design space.

1. To define how you want the displayed page to be modified for the web experience, you can:

   * [Insert new components](#insert-new-components) (divider, HTML, image, heading, paragraph, or link) to the page for the web experience.

   * Select any existing element from the page, such as an image, button, paragraph, text, container, heading, or link, and [modify it for the web experience](#modify-elements).

   * [Add click tracking](#click-tracking-for-web-experiences) for elements to measure engagement and gather insights.

1. Repeat step 2 to load other pages that you want to include in the web experience and repeat step 3 to define the page modifications.

1. [Review your modifications](#manage-modifications) and make any adjustments that are needed.

1. When your modifications are complete, click the left arrow above the editor to return to the web experience properties. 

### Modify elements

Click an element in the displayed page to select it. A blue border indicates the selected element and a contextual toolbar appears with modification options.

![Select an element to modify](./assets/web-experience-design-select-element.png){width="700" zoomable="yes"}

The toolbar options depend on the selected component type:

| Action | Description |
| ------ | ----------- |
| **[!UICONTROL Text options]** | Change the text element class or text styling of the selected element. |
| **[!UICONTROL Choose image]** | Replace the image source or add an image to the element. |
| **[!UICONTROL Edit link / Add link]** | Modify or add a link URL. |
| **[!UICONTROL Arrange]** | Move the selected element backward or forward within the display. |
| **[!UICONTROL Add personalization]** | Insert personalization. |
| **[!UICONTROL Click track element]** | Add click tracking for the element. |
| **[!UICONTROL Delete]** | Remove the selected element from the page. |

For a selected element, the properties in the right panel change to reflect the available styling and actions. Click an action icon at the top of the panel to duplicate, click-track, delete, or hide the selected element.

![click an action icon for the selected element](./assets/web-experience-design-visual-editor-element-properties-icons.png){width="300"}

+++Text elements

1. Select a text element on the page.

1. Enter new text content, or select a text string and enter your replacement text.

1. (Optional) Use the [text formatting options](./content-components.md#text), such as bold, italic, and alignment. 

1. Click outside the text element to apply the change.

For more information about text styling options for text components, see [Content components](./content-components.md#text).

+++

+++Image elements

1. Select an image element on the page.

1. Click the _[!UICONTROL Choose image]_ icon in the contextual toolbar or the right panel.

1. Browse and select an image from your assets library.

1. Use the [image styling options](./content-components.md#image) in the right panel as needed.

+++

+++Button elements

1. Select a button element on the page.

1. (Optional) Enter new text for the button, or select the text string and enter your replacement text.

   You can use personalization to alter the button text using data from account or person profiles.

1. Use the [button styling options](./content-components.md#button) in the right panel as needed.

+++

+++ Container elements

1. Select a container element on the page.

1. Use the [container styling options](./content-components.md#container) in the right panel as needed.

+++

### Insert new components

When you select the **+** icon in the design left navigation for the visual editor, you can add the following components types to the page as a web experience modification:

* **[!UICONTROL Divider]** - Use this component to insert a dividing line to organize the layout and content of your email. You can adjust styling attributes such as the line color, style, and height from the properties in the right panel. See [Divider](./content-components.md#divider) in _Content components_ for more information.
* **[!UICONTROL HTML]** - Use this component to copy-paste HTML code in the existing structure. It enables you to create free modular HTML components to reuse some external content. See [HTML](./content-components.md#html) in _Content components_ for more information.
* **[!UICONTROL Image]** - Use this component to insert an image file into the page. You can adjust styling attributes such as the width and height from the properties in the right panel. See [Image](./content-components.md#image) in _Content components_ for more information.
* **[!UICONTROL Heading]** - Use this component to insert heading class text. You can adjust styling attributes such as the text color, style, font, and size from the properties in the right panel. See [Text](./content-components.md#text) in _Content components_ for more information.
* **[!UICONTROL Paragraph]** - Use this component to insert a standard text element. You can adjust styling attributes such as the text color, style, font, and size from the properties in the right panel. See [Text](./content-components.md#text) in _Content components_ for more information.
* **[!UICONTROL Link]** - Use this component to insert a freestanding text link to a specified URL. You can adjust styling attributes such as the text color, style, alignment, and size from the properties in the right panel.

Select a component type on the left and then hover over an element that is adjacent to where you want to add it.

![Visual editor interface - new component](./assets/web-experience-design-visual-editor-insert-component.png){width="800" zoomable="yes"}

Click one of the displayed buttons to place the component:

* ***[!UICONTROL Insert before]** - Insert the component before the selected element.
* ***[!UICONTROL Insert after]** - Insert the component after the selected element.

To unselect a component type for insertion, click **[!UICONTROL ESC]** in the contextual blue banner displayed at the top of the page.

## Non-visual editor {#non-visual-editor}

Use the non-visual editor when you need to make modifications that cannot be easily accomplished in the visual editor. This code-based approach gives you precise control over element targeting and modification. Complete the following steps to use the non-visual editor for designing your web experience:

1. With the _[!UICONTROL Content]_ tab displayed in the web experience details page, click **[!UICONTROL Add modification]** in the right panel.

   The non-visual editor loads a page based on the web channel configuration. 

   ![Non-visual editor interface](./assets/web-experience-design-non-visual-editor.png){width="800" zoomable="yes"}

1. Define the first modification that you want to make.

   The left side panel displays a list of existing modifications (if any). Click **[!UICONTROL Add]** to define a new modification. If there are no modifications defined, the panel defaults to the _[!UICONTROL Add Modification]_ options.

   * Choose the **[!UICONTROL Modification type]**:

      | Type | Description |
      | ---- | ----------- |
      | [**[!UICONTROL CSS Selector]**](#css-selector-modifications) | Target elements using a CSS selector string. |
      | [**[!UICONTROL Page]**](#page-modifications) |Insert custom HTML, CSS, or JavaScript into page-level elements, such as `<head>` or `<body>`. |

   * Configure the modification parameters according to the type:

      * **[!UICONTROL CSS Selector]** - Enter a valid CSS selector to target specific elements.
      * **[!UICONTROL Action type]** - Choose the action to perform (edit, hide, delete, insert, replace).
      * **[!UICONTROL Content]** - Provide the content or styling to apply.

1. Click **[!UICONTROL Save]** to apply the modification.

### CSS selector modifications

CSS selector modifications allow you to target elements precisely using standard CSS selector syntax.

1. Choose **[!UICONTROL CSS Selector]** as the modification type.

1. Enter the selector in the **[!UICONTROL CSS Element Selector]** field.

  <!-- This field helps you find and select the HTML elements (or nodes in the DOM tree). -->

    **Example selectors:**

    | Selector | Targets |
    | -------- | ------- |
    | `#hero-banner` | Element with ID `hero-banner` |
    | `.cta-button` | All elements with class `cta-button` |
    | `header nav a` | Links within the navigation, inside the header |
    | `[data-offer="premium"]` | Elements with a specific data attribute |

1. Choose an **[!UICONTROL Action Type]** and specify the required information / content.

   * **[!UICONTROL Set Content]** - Enter the text in the **[!UICONTROL Content]** field for the element identified by the _[!UICONTROL CSS Element Selector]_ value.

   * **[!UICONTROL Set Attribute]** - Specify an attribute to be associated with the current CSS selector so that the element can be identified by this attribute. Enter a name in the **[!UICONTROL Attribute name]** field and a value in the **[!UICONTROL Content]** field. If the attribute already exists, the value is updated; otherwise, a new attribute is added with the specified name and value.

   ![Non-visual editor css selector modification](./assets/web-experience-design-non-visual-editor-modification-css-selector.png){width="800" zoomable="yes"}

1. (Optional) Click **[!UICONTROL Add personalization]** and use the [personalization editor](./personalization.md#personalization-editor) to create a customized personalization for the content.

### Page modifications

You can add custom code using the Page `<head>` modification type. The `<head>` element is a container for metadata (data about data) and is placed between the `<html>` tag and the `<body>` tag. In this case, code does not wait for body or page-load events - it is executed at the beginning of the page load.

The `<head>` element is commonly used to add JavaScript or CSS code to the top of the page. Selectors for subsequent visual actions depend on the HTML elements added in this tab.

>[!NOTE]
>
>Custom code runs in the visitor's browser. Ensure that your code is secure, tested, and does not negatively impact page performance or user experience.

1. Choose **[!UICONTROL Page `<head>`]** as the modification type.

1. Add your custom code in the **[!UICONTROL Content]** box.

    >[!CAUTION]
    >
    >You can only add `<script>` and `<style>` elements to the `<head>` section. Adding `<div>` tags and other elements might cause remaining `<head>` elements to populate within the `<body>`.

   ![Non-visual editor page-head modification](./assets/web-experience-design-non-visual-editor-modification-page-head.png){width="800" zoomable="yes"}

1. (Optional) Click **[!UICONTROL Add personalization]** and use the [personalization editor](./personalization.md#personalization-editor) to create a customized personalization for the content.

## Manage modifications {#manage-modifications}

>[!CONTEXTUALHELP]
>id="ajo-b2b_web_experience_modifications"
>title="Easily manage all your changes"
>abstract="Using this pane, you can navigate through and manage all the adjustments and additions defined for the web page."

All modifications that you create are tracked and can be managed from the **[!UICONTROL Modifications]** panel of both the visual editor and non-visual editor. Click the _[!UICONTROL Modifications]_ ( ![Modifications icon](../assets/do-not-localize/icon-web-exp-modifications.svg) ) icon in the left toolbar to view all modifications.

Each modification record includes:

* The target element or selector
* The modification type (such as edit, hide, or insert)
* A preview of the change

![Modifications panel](./assets/web-experience-design-modifications-list.png){width="500"}

### Edit a modification

1. In the _[!UICONTROL Modifications]_ list, find the modification that you want to edit.

1. Click the _More menu_ ( **...** ) icon and choose **[!UICONTROL Edit]**.

1. Update the modification properties as needed.

1. Click **[!UICONTROL Save]** to save your changes.

### Delete a modification

1. In the _[!UICONTROL Modifications]_ list, find the modification that you want to remove.

1. Click the _More menu_ ( **...** ) icon and choose **[!UICONTROL Delete modification]**.

1. Confirm the removal when prompted.

<!-- ### Reorder modifications

Modifications are applied in the order that they appear in the list. If you have multiple modifications that affect the same element, the order may impact the final result.

Drag and drop modifications in the list to change the order. The preview updates to reflect the new modification order. -->

## Preview your modifications

Before publishing, preview how your modifications appear to visitors.

Use the device preview options at the top of the visual editor to view your modifications on:

* Desktop
* Tablet
* Mobile

![Change the device sizing for the preview](./assets/web-experience-design-device-view.png){width="550"}

The preview updates to show how modifications render on each device size. 

### Page navigation

1. Use the URL bar to navigate to different pages within your web channel configuration.

1. Verify that modifications apply correctly to the targeted pages based on your URL matching rules.

## Click tracking for web experiences {#web-click-tracking}

Track user interactions with elements to measure engagement and gather insights. The click tracking data is available in your engagement reports and can be used to measure the effectiveness of your web experience modifications.

When your web experience is activated (live), you can also build reports using the Adobe Customer Journey Analytics (which requires a product subscription). To improve your web experience monitoring, you can also track the clicks on any specific element of your website. Tracking allows you to display the number of clicks for that element in the web reports.

For more information about Customer Journey Analytics and building web reports, see the [Customer Journey Analytics documentation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-landing).

1. Select an element in the web experience editor, such as an image or link.

1. In the element properties or contextual toolbar, click the _[!UICONTROL Click track element]_ icon.

   ![Enable click tracking for web experience elements](./assets/web-experience-design-visual-editor-click-tracking-icons.png){width="600" zoomable="yes"}

1. Open the Click track list in the left panel and modify the  **[!UICONTROL Tracked actions]** value to identify this interaction in your reports.

   ![Set click tracking identification for web experience](./assets/web-experience-design-visual-editor-click-tracking-identifier.png){width="600" zoomable="yes"}
