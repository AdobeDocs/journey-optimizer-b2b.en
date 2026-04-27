---
title: Design accessible content
description: Learn how to design accessible content for your emails and landing pages in Journey Optimizer B2B Edition
feature: Email Authoring, Landing Pages
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: email, design, accessibility
exl-id: 744e94f4-195f-4277-877d-09275f40ce23
---
# Design accessible content {#accessible-content}

The [European accessibility act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32019L0882){target="_blank"} is a directive designed to enhance the internal market for accessible products and services by eliminating barriers caused by differing national rules across Member States.

This regulation states that all digital communications, including emails, newsletters, PDFs, and downloadable content, should be accessible. When creating content for your recipients, you are therefore required to follow specific guidelines such as using accessible fonts, readable formats, and providing alternative text for images. 

The [!DNL Journey Optimizer B2B Edition] design tools enable marketers to build content both for **_emails_** and **_landing pages_**. Use these tools to comply with this directive, based on Web Content Accessibility Guidelines (WCAG) 2.1, level AA.

The following sections outline the best practices for designing accessible content with [!DNL Journey Optimizer B2B Edition]. This information focuses on designing content that is accessible to all your recipients, so that people with disabilities can read, understand, and interact with your email messages and landing pages.
  
## Ensure text readability {#text-readability}

Leverage the **[!UICONTROL Styles]** tab of the **[!UICONTROL Text]** component to ensure that your text is readable, such as using a proper color contrast and simple fonts. For more information about text component styling, see [_Content components_](content-components.md#text)

![Text component Styles tab showing font, size, and color options](assets/accessible-text-styles.png){width="700" zoomable="yes"}

For fonts and text, follow these guidelines: 

### Font selection

* Use sans-serif fonts, such as Arial, Verdana, Tahoma, Helvetica, or Open Sans.
* Avoid serif, cursive, or decorative fonts in body content.
* Stick to a limited font set for consistency and fallback (for example: `font-family: Arial, Helvetica, sans-serif;`).

### Font sizing

* Ensure a minimum font size of 16px for body text.
* Use a proper hierarchy for headings. 

### Color contrast

* Maintain a contrast ratio of at least 4.5:1 between text and background.
* For large text (≥24px or bold 18px), ensure at least a 3:1 contrast.
* Avoid light gray or pastel text on white backgrounds.
* Do not rely on color alone to convey meaning, but instead use underlines, icons, etc.

### Text accessibility

* Avoid text in images.
* Do not use all caps in body text.
* Ensure that text can be zoomed up to 200% without breaking the layout.

## Ensure visual accessibility {#visual-accessibility}

To make sure your content is visually accessible, follow these best practices:

* Avoid using color-only indicators for important information.
* Use text labels or icons to ensure clarity.
* Optimize your design for mobile and responsive layouts, ensuring buttons are large and properly spaced.
* Regularly test across devices and screen sizes to maintain accessibility. 

In [!DNL Journey Optimizer B2B Edition], the size and spacing of the different elements in your content can be further refined using the styling parameters and attributes from the visual design space **[!UICONTROL Styles]** pane.

For example, you can update the background, or change the margins, padding, and alignment to improve the visual accessibility of your content.

![Styles pane with background, margins, padding, and alignment settings](assets/accessible-styles.png){width="700" zoomable="yes"}

The [!DNL Journey Optimizer B2B Edition] visual design tools enable you to preview and optimize design for different devices and screen sizes. At any time, you can **[!UICONTROL Switch to live view]** to check how your content might render on various device sizes.

![Live view toggle showing desktop, tablet, and mobile preview options](assets/accessible-live-view.png){width="700" zoomable="yes"}

>[!CAUTION]
>
>The live view is a generic preview designed to compare how the rendering might look across various device sizes. The final rendering may vary according to the recipient's email client or web browser.

## Use alternative text for images {#alt-text}

Use the **[!UICONTROL Image]** component to provide alternative text for images. For more information about image component settings, see [_Content components_](content-components.md#image)

![Image component settings panel with Alternative text field highlighted](assets/accessible-alt-text.png){width="700" zoomable="yes"}

For effective alternative text in digital products, follow these guidelines:

* Describe the image's purpose concisely and contextually.
* Avoid redundant phrases like "Image of ..." and use empty alt text for decorative images.
* For icons with meaning, provide meaningful labels, and for complex images, use a brief alt text plus a longer description elsewhere.

## Use readable format {#readable-format}

In the visual design space, use the relevant [structure](structure-components.md) and [content](content-components.md) components to organize your content in a clear, logical and concise way that is accessible to all. Set the options in the **[!UICONTROL Styles]** pane using structural inheritance best practices.

![Email design space showing structure and content components for organized layouts](assets/accessible-components.png){width="700" zoomable="yes"}

* Use structured, semantic HTML with proper headings, paragraphs, lists, and tables.
* Ensure that content follows a logical left-to-right, top-to-bottom flow.
* Use clear, concise language.
* Provide alternative formats for PDFs and infographics.
* Allow text resizing and reflow, and ensure that typography is readable with adequate color contrast in all formats.

## Ensure content readability {#readability}

To be readable, your content must be clear, well-structured, and usable by everyone, including people with visual, cognitive, or reading difficulties and those using assistive technologies. Some points to consider when creating accessible content include:

* Keep sentences to around 20 words or less. 
* Edit your copy to be direct and to the point. 
* Use active voice to keep the sentence structure simpler. 
* Avoid slang, jargon, or regional words that some people might not know.

To evaluate your content readability, use the popular [Flesch Reading Ease test](https://support.microsoft.com/en-us/office/get-your-document-s-readability-and-level-statistics-85b4969e-e80a-4777-8dd3-f7fc3c8b3fd2){target="_blank"} in Microsoft Word. It calculates how easy your content is to read on a scale of 0-100.

## Test your content {#test}

To verify the content accessibility, you can use the testing capabilities provided by [!DNL Journey Optimizer B2B Edition]. They are not specifically designed to check if your content is fully accessible, but they can provide a first level of verification.

* Preview your content using test profiles.

* Use the [Render email](email-test-rendering.md) option that leverages Litmus to simulate your designs across major email clients (Apple Mail, Gmail, Outlook) and see if text, colors and images make your content accessible.

* Send proofs to test the rendering of your content before sending it to your real audience.

![Content simulation interface with test profile preview options](assets/accessible-simulate.png){width="800" zoomable="yes"}

To check if your content is reliably accessible in a more consistent way, use external tools such as:

* The [WebAim contrast checker](https://webaim.org/resources/contrastchecker/){target="_blank"} and the [WAVE web accessibility evaluation tool](https://wave.webaim.org/){target="_blank"} to evaluate contrast and compliance;

* Assistive technologies like screen readers (for example: [NVDA](https://www.nvaccess.org/download/){target="_blank"}, or [VoiceOver](https://support.apple.com/en-ie/guide/iphone/iph3e2e415f/ios){target="_blank"} on iPhone) to experience emails from the perspective of visually impaired users.
 
## Use dark mode {#dark-mode}

Dark mode enhances visual accessibility for users with light sensitivity or visual impairments, for an improved viewing experience. 

![Design settings for dark mode](assets/email-color-mode-dark-text-settings.png){width="700" zoomable="yes"}

For dark mode design, use transparent PNG or SVG images and set appropriate meta tags and CSS. Provide accessible fallback styling if dark mode is not supported. Finally, test all content and UI elements in both light and dark modes.

For more information about using _Dark mode_ in the email design space, see [_Dark mode for email content_](./email-dark-mode.md).

## Use specific attributes for accessibility {#attributes}

HTML attributes help assistive technologies interpret structure, language, and relationships in your content. The following sections cover language and text direction, tables used for layout versus data, and link text that screen readers announce to users.

### Language attributes {#language}

When creating designs, include the `lang` (language) and `dir` (text direction) attributes in the content body. These attributes help assistive technologies such as screen readers to interpret and present your content in an appropriate manner.

* The `lang` attribute indicates the language of the email to assistive technologies, ensuring that words are pronounced correctly.

    +++Examples

    Example for English: 

    ```
    <body lang="en">
    ```

    Example for French: 

    ```
    <body lang="fr">
    ```

    +++

* The `dir` attribute specifies text direction. Most languages, including English and French, are read left-to-right (ltr), whereas languages such as Arabic and Hebrew are read right-to-left (rtl).

    +++Examples

    Example for English (left-to-right): 

    ```html
    <body lang="en" dir="ltr">
    ```

    Example for Arabic (right-to-left): 

    ```html
    <body lang="ar" dir="rtl">
    ```

    +++

Screen readers rely on the `lang` attribute to apply the correct pronunciation rules. Text direction ensures content flows naturally for left-to-right or right-to-left languages. Without these attributes, users may experience confusing reading order or mispronunciation. Consequently, always wrap your email body with the appropriate `lang` and `dir` attributes.

>[!TIP]
>
>If your email contains multiple languages, assign the appropriate language attributes to specific sections (such as `<table>` or `<td>` blocks) to ensure that each part is read correctly. 

### Tables {#tables}

In HTML contents, tables are often used for layout. By default, screen readers treat every `<table>` as a data table, announcing rows, columns, and structure. This structure can be confusing if the table is only used for formatting. 

Add `role="presentation"` (or `role="none"`) to layout tables to ensure assistive technologies skip their structure and focus only on the actual content.

+++Example – Layout table (with `role="presentation"`)

```html
<table role="presentation" border="0" cellpadding="0" cellspacing="0" width="100%"> 
  <tr> 
    <td align="center"> 
      <h1>Hello World</h1> 
      <p>Welcome to this newsletter</p> 
    </td> 
  </tr> 
</table>
```

The screen readers read: 
"Hello World. Welcome to this newsletter." *(No mention of rows, columns, or table)*

+++

+++Example – Data table (without `role="presentation"`)

```html
<table border="1" cellpadding="5" cellspacing="0"> 
  <tr> 
    <th scope="col">Name</th> 
    <th scope="col">Score</th> 
  </tr> 
  <tr> 
    <td>Alice</td> 
    <td>95</td> 
  </tr> 
  <tr> 
    <td>Bob</td> 
    <td>88</td> 
  </tr> 
</table> 
```

The screen readers read: 
"Table with 2 columns and 3 rows." 

"Name, Alice. Score, 95." 

"Name, Bob. Score, 88."

+++

>[!TIP]
>
>Use `role="presentation"` exclusively for layout tables. For data tables, retain the semantic `<table>` structure so screen readers can correctly announce headers and relationships. 

### Text for links and buttons {#links}

Screen readers read out links using their text. If a link is labeled only _Click here_ or _Read more_, users of assistive technologies don't know the destination. To ensure accessibility, they need descriptive text that clearly indicates the target or action.

Use the design tools to add a link to your content and edit the label to make it discernible (visible) and descriptive (clear about purpose). Avoid vague labels like _here_ or _more_.

![Link settings panel showing URL field and descriptive label options](assets/accessible-link.png){width="700" zoomable="yes"}

+++Example – Good link (descriptive): 

```
<p>Learn more in the  
<a href="https://adobe.com/release-notes">August release notes</a>. 
</p>
```

The screen readers read: 
"Link, August release notes."

+++

+++Example – Bad link (not descriptive)

```
<p>Learn more about our new features.  
  <a href="https://adobe.com/release-notes">Click here</a>. 
</p>
```

The screen readers read: 
"Link, click here." *(Provides no context out of reading order)*

+++

## Provide keyboard navigation and focus support {#keyboard}

For landing pages, providing keyboard navigation and focus support allows people who cannot use a mouse to access and interact with content. It also improves overall usability by giving all users a clear and consistent way to move through information.

* Keyboard navigation and focus
    * Ensure all interactive elements (such as buttons, checkboxes, and links) have `tabindex="0"` so they are included in the natural tab order. 
    * Allow navigation using the tab and arrow keys (↑ ↓ ← →), which should visibly highlight the focused element. 
* Custom focus styling 
    * Apply clear and distinguishable styles for focusing on actionable elements: 
        +++Example (CSS)

        ```
        [tabindex="0"] : focus { 
        outline: 2px solid #00AEEF;  /* Cyan border */ 
        background-color: #20CEFF;   /* Optional background */ 
        }
        ```
        
        +++

    * Ensure that focus indicators meet the WCAG 2.2 focus appearance standards, including: 
        * Minimum area: 2 CSS pixel thick outline.
        * Contrast ratio: ≥ 3:1 between focused and unfocused state. 

* Keyboard activation support 
    * Ensure checkboxes and buttons respond to the Enter and Space keys. 
    * Validate the interaction using the keyboard alone: 
        * Enter or Space should toggle checkboxes.
        * Enter or Space should trigger the buttons.
