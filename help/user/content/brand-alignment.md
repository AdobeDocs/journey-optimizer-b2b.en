---
title: Brand alignment scoring
description: Learn how to create, validate, and manage on-brand content using a brand alignment score.
badge: label="Beta" type="Informative"
feature: Content, Brand Identity
hide: yes
hidefromtoc: yes
role: User
level: Beginner, Intermediate
---
# Brand alignment scoring {#brand-score}

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_score_overview"
>title="Brand selection"
>abstract="Select your brand to ensure that your content is crafted in alignment with its specific guidelines, standards, and identity, maintaining consistency and brand integrity."

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_score"
>title="Brand alignment score"
>abstract="Your brand alignment score measures how well your content adheres to the brand guidelines, ensuring consistency in colors, fonts, logo, imagery and writing style."

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_colors"
>title="Colors score"
>abstract="Colors score"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_fonts"
>title="Fonts score"
>abstract="Fonts score"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_logos"
>title="Logos score"
>abstract="Logos score"

The brand alignment evaluation and scores help you to create, review, and manage content that adheres to the guidelines [defined in the selected brand](./brands-manage-create.md#brand-definitions). It ensures consistency in tone, messaging, and visual identity across your email campaigns, while also serving as a quality check before your content goes live.

>[!AVAILABILITY]
>
>This capability is currently available as a private beta, with progressive availability planned for all customers in future releases.
>
>A [user agreement](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"} is required before you can use AI-powered features in Adobe Journey Optimizer B2B Edition. For more information, contact your Adobe representative.
>
>See [Brand-related permissions](./brands-overview.md#brand-related-permissions) for information about how product administrators can enable these features.

## Validate your brand alignment

When your brand is well-defined and published, assess your brand alignment score directly within the email design space to ensure that the content aligns with your brand guidelines:

1. After you create the email content, click the _Brand alignment_ ( ![Brand alignment icon](../assets/do-not-localize/icon-brand-compliance.svg) ) icon on the right to open the _Brand alignment_ right panel in the email design space.

  The [default brand](./brands-create-manage.md#set-a-default-brand) is automatically selected.

  ![Access the Brand alignment tools](./assets/brands-alignment-sidebar.png){width="600" zoomable="yes"}

  You can click the _Full screen_ ( ![Full screen icon](../assets/do-not-localize/icon-full-screen.svg) ) icon at the top of the panel to display the brand alignment tools in full-screen mode.

1. If needed, click the **[!UICONTROL Brand]** menu arrow ( ![Down arrow](../assets/do-not-localize/icon-down-menu.svg) ) to choose another published brand.

1. Click **[!UICONTROL Evaluate score]** to score the content alignment with the selected brand.

   The system evaluates the content against the guidelines for the selected brand and displays the resulting score.

   ![Brand alignment evaluation score](./assets/brands-alignment-evaluation.png){width="600" zoomable="yes"}

## Review the evaluation

The score is calculated according to identified violations in the evaluated email content:

* 100 = Perfect - No violations found
* 80-99 = Good - Minor violations only
* 60-79 = Fair - Some significant violations
* Below 60 = Poor - Major violations need attention

You can review the evaluation results in more detail to help you identify violations and improve your category alignment scores (_High_, _Medium_, and _Low_) and review the details. For the **[!UICONTROL Writing style]** or **[!UICONTROL Visual content]**, click the _Expand_ ( ![Expand arrow](../assets/do-not-localize/icon-expand-right.svg) ) arrow to display the details for the evaluation.

![Brand alignment evaluation details](./assets/brands-alignment-evaluation-details.png){width="600" zoomable="yes"}

Select any flagged guideline to view specific feedback and suggestions.

You can make changes to the content and click **[!UICONTROL Re-evaluate score]** to run another evaluation and check for an improved result.
