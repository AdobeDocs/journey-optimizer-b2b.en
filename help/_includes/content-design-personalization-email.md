---
title: Content authoring - personalization
description: Reused section about using personalization for content authoring
---
# Content authoring - personalization

Journey Optimizer B2B Edition uses an inline simple syntax that allows you to create expressions with personalized content enclosed by curly braces `{{}}`. You can add multiple expressions in the same content or field without restrictions.

For example, you might add a personalization expression as `Hello {{lead.firstName}} {{lead.lastName}}`. When processing the content, Journey Optimizer B2B Edition replaces the expression with the data contained in the Experience Platform database. So, the first example becomes _Hello John Doe_.

See [Content personalization](../user/content/personalization.md) for more comprehensive information about using personalization tools in Journey Optimizer B2B Edition.

>[!NOTE]
>
>Journey Optimizer B2B Edition follows _camel case_ syntax for personalization tokens in emails to match the other Adobe Experience Platform applications for a consistent experience. This token format is fully compatible with the [Handlebars templating language](https://handlebarsjs.com/guide/#what-is-handlebars){target="_blank"}. Any tokens that were added prior to this change are automatically updated.

The following example outlines steps to personalize content using person and system tokens.

1. Select the text component and click the _Add personalization_ ( ![Add personalization icon](../assets/do-not-localize/icon-personalization-field.svg) ) icon in the toolbar.

   ![Click the Personalize icon](../assets/content-design-shared/visual-designer-personalize-icon.png){width="600"}

   This action opens the _Edit Personalization_ dialog.

1. Add a token by clicking the plus ( **+** ) symbol next to it.

   If you want to add the token with a fallback (default text that appears when that field is not available for a lead), click the _More_ icon ( **...** ) and choose **[!UICONTROL Insert with fallback text]**.

   ![Construct personalized text using tokens](../assets/content-design-shared/visual-designer-personalize-dialog-handlebar.png){width="700" zoomable="yes"}

1. Add any additional tokens or other static text that you want to include.

1. Click **[!UICONTROL Save]**.

   The personalization scripting is displayed in the visual design space. You can select it to make changes when needed. 

   ![Select personalization script](../assets/content-design-shared/visual-designer-select-personalization-script.png){width="600"}
