---
title: Fragment Authoring
description: Author reusable content fragments with visual design tools - add structure, assets, personalization, conditional content, and linked URL tracking for emails and templates in Journey Optimizer B2B Prime.
badgeBeta: label="Beta" type="informative" tooltip="This feature is part of a limited beta release."
autotag-review: '2026-07-13T16:38:09.506Z'
TQID: 'https://experienceleague.adobe.com/Zn5L6Bc3x8SuGyjOPDdTWI-oxrrhk06a2f8ZvX2SN4s'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
    internal-label: Content management
subfeature_v2:
  - id: e1663313-7961-4100-bea9-fa9f4edf8493
    internal-label: Fragments
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Fragment authoring

After you [create a fragment](./fragments.md#create-fragments), use the visual design space to author the structure and content components in your fragment.

## Add structure and content {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## Add assets {#add-assets}

In the visual design space, select the _Assets_ ( ![Assets icon](../../assets/do-not-localize/icon-assets-me.svg) ) icon in the left navigation bar to browse and select image assets from the [!DNL Journey Optimizer B2B Prime] asset library.

For steps to select, replace, or upload image assets, see [Use assets for content authoring](./digital-asset-management.md#assets-authoring).

## Navigate the layers, settings, and styles {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## Personalize content {#personalize-content}

[!DNL Journey Optimizer B2B Prime] uses Handlebars syntax for personalization. Tokens are replaced at send time with values from each recipient's profile data.

_To add personalization:_

1. Select the text component and click the _Add personalization_ ( ![Personalize icon](../../user/assets/do-not-localize/icon-personalize.svg) ) icon in the toolbar.
1. In the personalization dialog, browse the schema tree on the left and select a profile attribute. The editor inserts the corresponding Handlebars expression — for example, `{{profile.firstName}}`.
1. Add a fallback value to handle missing data, if needed — for example, `{{profile.firstName | default: "there"}}`.
1. Click **[!UICONTROL Confirm]** or **[!UICONTROL Insert]**. The expression appears inline in the field.

For details about expression editor tools and syntax, see [Personalization editor](./personalization-expressions.md).

## Edit linked URL tracking {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
