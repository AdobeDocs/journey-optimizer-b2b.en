---
title: Content Scoring
description: Evaluate email content with brand alignment scoring - validate colors, fonts, logos, and writing style against brand guidelines in Journey Optimizer B2B Edition.
badge: label="Beta" type="Informative"
feature: Content, Brand Identity
role: User
level: Beginner, Intermediate
exl-id: 686d5ce0-c597-48e1-a51f-e91e95a942d5
---
# Content scoring {#content-scoring}

The content evaluation and scoring help you to create, review, and manage content that adheres to the guidelines [defined in the selected brand](./brands-manage-create.md#brand-definitions) and the general quality standards. Running an evaluation ensures consistency in tone, messaging, and visual identity across your email campaigns, while also serving as a quality check before your content goes live.

>[!AVAILABILITY]
>
>A [user agreement](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"} is required before you can use AI-powered features in Adobe Journey Optimizer B2B Edition. For more information, contact your Adobe representative.
>
>See [Brand-related permissions](./brands-overview.md#brand-related-permissions) for information about how product administrators can enable these features.

## Run an evaluation

1. After you create the email content, click the _Brand alignment_ ( ![Brand alignment icon](../assets/do-not-localize/icon-brand-compliance.svg) ) icon on the right to open the _Brand alignment_ right panel in the email design space.

   The [default brand](./brands-manage-create.md#default-brand) is automatically selected.

   ![Access the Brand alignment tools](./assets/brands-alignment-sidebar.png){width="600" zoomable="yes"}

   You can click the _Full screen_ ( ![Full screen icon](../assets/do-not-localize/icon-full-screen.svg) ) icon at the top of the panel to display the brand alignment tools in full-screen mode.

1. If needed, click the **[!UICONTROL Brand]** menu arrow ( ![Down arrow](../assets/do-not-localize/icon-down-menu.svg) ) to choose another published brand.

1. Click **[!UICONTROL Evaluate score]** to score the content alignment with the selected brand.

   The system evaluates the content against the guidelines for the selected brand and displays the resulting score.

   ![Evaluation scores in the right panel](./assets/brands-alignment-evaluation.png){width="600" zoomable="yes"}

## Brand alignment score {#brand-score}

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_score_overview"
>title="Brand selection"
>abstract="Select your brand to ensure that your content is crafted in alignment with its specific guidelines, standards, and identity, maintaining consistency and brand integrity."

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_score"
>title="Brand alignment score"
>abstract="Your brand alignment score measures how well your content adheres to the brand guidelines to ensure consistency in colors, fonts, logo, imagery, and writing style."

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_colors_score"
>title="Colors score"
>abstract="Colors score"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_fonts_score"
>title="Fonts score"
>abstract="Fonts score"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_logos_score"
>title="Logos score"
>abstract="Logos score"

>[!AVAILABILITY]
>
>This capability is currently available as a public beta.

When your brand is well-defined and published, assess your brand alignment score directly within the email design space to ensure that the content aligns with your brand guidelines:

The score is calculated according to identified violations in the evaluated email content:

* 100 = Perfect - No violations found
* 80-99 = Good - Minor violations only
* 60-79 = Fair - Some significant violations
* Below 60 = Poor - Major violations need attention

You can review the evaluation results in more detail to help you identify violations and improve your category alignment scores (_High_, _Medium_, and _Low_) and review the details. 

For the **[!UICONTROL Writing style]** or **[!UICONTROL Visual content]**, click the _Expand_ ( ![Expand arrow](../assets/do-not-localize/icon-expand-right.svg) ) arrow to display the details for the evaluation.

![Brand alignment evaluation details](./assets/brands-alignment-evaluation-details.png){width="600" zoomable="yes"}

Click the _Full screen_ ( ![Full screen icon for detailed insights](../assets/do-not-localize/icon-full-screen.svg) ) icon for a detailed view of each score insight.

Select any flagged guideline to view specific feedback and suggestions.

![Brand alignment evaluation details in full-screen view](./assets/brands-alignment-evaluation-details-full-screen.png){width="700" zoomable="yes"}

You can make changes to the content and click **[!UICONTROL Re-evaluate score]** to run another evaluation and check for an improved result.

## Content quality score {#quality-score}

>[!CONTEXTUALHELP]
>id="ajo-b2b_quality_score_overview"
>title="Content quality"
>abstract="Assess general content quality to identify potential issues with readability, content cohesiveness, and effectiveness. The quality assessment is independent of your brand guidelines."

>[!NOTE]
>
>Content quality evaluation is independent of brand guidelines. Even if a brand is selected, its guidelines are not applied to the quality check. The brand selection is only relevant for brand alignment scoring.

In addition to brand alignment, you can assess general content quality to identify potential issues with readability, content cohesiveness, and effectiveness, independent of your brand guidelines. 

Scroll to the **[!UICONTROL Content quality]** section to review the quality insights and recommendations.

![Content quality evaluation](./assets/content-scoring-quality-insights.png){width="600" zoomable="yes"}

Select any flagged item to view specific feedback and actionable suggestions for improvement. Scores are based on the following categories:

* **[!UICONTROL CTA effectiveness]**: Evaluates how well your call-to-action motivates readers to take the desired action.
* **[!UICONTROL Subject Line]**: Assesses clarity, relevance, and attention-grabbing quality to encourage email opens.
* **[!UICONTROL Readability]**: Measures how easy and engaging your content is for readers to understand.
* **[!UICONTROL Spam Check]**: Identifies common spam triggers that may impact deliverability.
* **[!UICONTROL Content Cohesiveness]**: Ensures your content flows smoothly and stays on topic.
* **[!UICONTROL Proofreading]**: Checks for spelling, grammar, and clarity issues.

Click the _Full screen_ ( ![Full screen icon for detailed insights](../assets/do-not-localize/icon-full-screen.svg) ) icon for a detailed view of your quality score.

![Full screen view of the content quality evaluation](./assets/content-scoring-quality-full-screen.png){width="700" zoomable="yes"}

Based on the recommendations, you can edit your content to enhance readability, content cohesiveness, and overall quality. Click **[!UICONTROL Re-evaluate score]** after making changes to refresh the quality score.
