---
title: Fragment Authoring
description: Learn how to author content fragments that can be reused for your emails and template designs for efficiency and to maintain design and branding standards.
feature: Content
exl-id: d29754cf-6721-489c-bff8-cde034456db2
---
# Fragment authoring

After you [create a fragment](./fragments.md#create-fragments), use the visual editor to author the structural and content components in your fragment.

## Add structure and content {#design-fragment}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_fragment"
>title="Add Structure components"
>abstract="Structure components define the layout of the fragment. Drag and drop a **Structure** component into the canvas to start designing the content of your fragment."

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_fragment"
>title="About Content components"
>abstract="Content components are empty content placeholders that you can use to create the layout of a fragment."

{{$include /help/_includes/content-design-components.md}}

## Add assets

{{$include /help/_includes/content-design-assets.md}}

## Navigate the layers, settings, and styles

{{$include /help/_includes/content-design-navigation.md}}

## Personalize content

{{$include /help/_includes/content-design-personalization.md}}

## Enable fragment customization

When an email or email template author adds the fragment, the fragment content is locked by default. Any changes to the published fragment are automatically propagated to all content assets where the fragment is used. When you designate a parameter for a component in the fragment as editable, the email or template author can specify a custom field value that is specific to their needs. This customization flag is limited to image, text, and button visual components.

For example, if you design a reusable banner that includes a clickable button, you can designate the URL parameter for the button as editable. Email authors can then use a URL that is more specific to their email campaign. With these customizable fields, Marketers can manage and personalize content without the need to create entirely new content blocks or disrupt the inherited updates from the original fragment.

1. In the visual content editor, select the image, text, or button element where you want to enable customization.

1. In the component details on the right, select the **[!UICONTROL Editable fields]** tab.

1. Click the **[!UICONTROL Enable edition]** option toggle and set the editable fields.

   ![Enable editable fields for a fragment image component](./assets/fragment-editable-fields-image.png){width="700" zoomable="yes"}

   You can enable customization for the displayed fields, which depend on the component type and the parameters defined in the fragment.

   Change the toggle to an enabled state for each field where you want to allow customization.

1. Click **[!UICONTROL Overview]** to review all the editable fields and their default values.

   ![Review the editable fields and their default values](./assets/fragment-editable-fields-image-overview.png){width="700" zoomable="yes"}

1. Save your changes.

## Edit linked URL tracking

{{$include /help/_includes/content-design-links.md}}
