---
title: Generative AI for content
description: Learn to create personalized emails and landing pages with generative AI in [!DNL Journey Optimizer B2B Edition], including prompting best practices.
feature: AI Assistant, Generative AI, Content
level: Beginner
topic: Artificial Intelligence
role: User
---
# Generative AI for content {#generative-ai-content}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-settings"
>title="AI Content Generation"
>abstract="After you have crafted your layout, you can use generative AI tools in [!DNL Journey Optimizer B2B Edition] to enhance your content. This feature simplifies the process of personalization and content improvement by fine-tuning the content according to your descriptive prompt."

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-reference-context"
>title="Reference content"
>abstract="Use _Reference content_ to upload an asset file containing content that provides additional context for generative AI in [!DNL Journey Optimizer B2B Edition], or to select a previously uploaded file. This option ensures that all necessary materials are available to enhance the quality and relevance of generated content."

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-start"
>title="Adobe generative AI terms"
>abstract="Access to this feature is subject to your agreement to the Adobe Experience Cloud Generative AI User Guidelines. Review any output from this feature for accuracy and ensure that it is appropriate for your use case."
>additional-url="https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html" text="Adobe Generative AI User Guidelines"

Generative AI for content in [!DNL Adobe Journey Optimizer B2B Edition], powered by Microsoft Azure OpenAI and Adobe Firefly, provides proactive content variation suggestions for text and images. Optimize your content impact by experimenting with different main titles and images. 

Use the generative AI features for content creation in [!DNL Journey Optimizer B2B Edition] to harness Adobe's generative AI capabilities. Craft personalized text and visuals for emails, SMS messages, landing pages, and more. When you are building a full campaign or simply refining specific assets, these features help you align content seamlessly with your brand guidelines while saving valuable time.

<!--
Generate multiple variants and build an experiment to compare them. Leveraging Journey Optimizer Content Experiment, you can define multiple message treatments to measure which one performs best for your target audience. You can choose to vary the delivery content, or subject. The message audience is randomly allocated to each treatment to determine which one works best in terms of the specified metric. Learn more about Content Experiment in this section. -->

>[!IMPORTANT]
>
>To access these features in [!DNL Journey Optimizer B2B Edition], you must have the _[!UICONTROL AI Assistant]_ > _[!UICONTROL Generate Content]_ permission. For more information about how a product administrator can grant feature permissions, see [Edit roles for product permissions](../admin/user-management.md#edit-roles-for-product-permissions).

AI Assistant tools for content generation are supported with the following asset types:

* [Emails](../content/ai-assistant-emails.md)
* [!BADGE Beta] [Landing pages](../content/ai-assistant-landing-pages.md)

## General guidelines and limitations {#general-guidelines-and-limitations}

Your use of generative AI features is subject to the [Adobe Experience Cloud Generative AI User Guidelines](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}. With Adobe's commitment to transparency in the use of generative AI tools for media creation, Adobe applies [content credentials](https://helpx.adobe.com/firefly/web/get-started/learn-the-basics/content-credentials-overview.html){target="_blank"} for any content or project that includes a [!DNL Firefly]-generated asset when it is downloaded or exported.

Review these general guidelines for using generative AI for content in [!DNL Journey Optimizer B2B Edition]:

* Use well-defined prompts for the generative AI model to interpret with accuracy. The marketing objective or prompt you provide strongly affects the quality of the generated content.

* Upload content reference files to have accurate, on-brand content. Otherwise, content is based on publicly available information. The uploaded content can be in the following file formats: PDF, JPEG, PNG, or ZIP (containing supported file formats). The maximum size for an uploaded file is 50MB. Larger files or a large number of images can work, but this increases the processing time.

* Use a brand specific or custom template to create your email content. Email templates with up to 8-10 images are recommended.

* Make sure to report any problematic outputs using the thumb up, thumb down, or flag icons when selecting variants.

## Prompt best practices for generative AI {#generative-ai-prompting-guide}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai_content_prompt"
>title="Prompt guidance"
>abstract="Explore [!DNL Journey Optimizer B2B Edition] documentation to learn how to create effective prompts that produce high-converting, on-brand marketing content."

This guide helps you structure your requests, communicate intent with clarity, and ensure that the AI produces messaging that aligns with your brand guidelines, audience needs, and campaign goals.

Learn how to write effective prompts that enable AI Assistant to generate high-quality, on-brand marketing content tailored to your objectives. 

### Use the CO-STAR framework {#costar-framework}

For best results with generated content, organize your prompts using the CO-STAR framework. This structured approach provides clarity for exactly what you need.

| Component | What it means | Why it matters |
| --- | ---- | ------ |
| **C - Context** | Background about your campaign, product, or situation | Provides understanding for the bigger picture |
| **O - Objective** | Your specific marketing goal | Drives what the content should achieve |
| **S - Style** | How you want to communicate | Sets the approach |
| **T - Tone** | Emotional style and voice | Shapes how your message feels |
| **A - Audience** | The audience that you are targeting | Ensures that the message resonates with the right people |
| **R - Requirements** | Specific constraints or must-haves | Defines boundaries and critical elements |

### Prompting essentials {#key-takeaways}

<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>Do</th>
<th>Don't</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul><li>Use the CO-STAR framework for structure
<li>Be explicit about fresh vs. existing content
<li>Provide focus for document usage with specific extraction guidance
<li>Make selections for tone, strategy, and locale
<li>Match marketing objectives to content type capabilities
<li>Generate multiple variants for A/B testing</ul>
</td>
<td>
<ul><li>Ask for structural changes, styling, or image editing in prompts
<li>Mention tone/strategy in prompts if available in options
<li>Use vague objectives like _promote the product_
<li>Request conditional element selections
<li>Expect layout modifications through prompts</ul>
</td>
</tr>
</tbody>
</table>

### Content not supported in prompts

>[!TIP]
>
>Use the design tools or [!DNL Adobe Express] for visual/image modifications.

The following requests are **_not supported_** and should be handled through other tools:

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th>&#10005; Email structure modifications</th>
<th>&#10005; Visual styling changes</th>
<th>&#10005; Image editing operations</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>Selecting specific sections to change</li>
<li>Deleting or cloning elements</li>
<li>Conditional selections</li>
<li>Adding or removing layout sections</li>
</ul>
</td>
<td>
<ul>
<li>Text formatting (bold, italic, font size)</li>
<li>Color modifications</li>
<li>Layout styling (borders, padding, margins)</li>
<li>Visual effects (shadows)</li>
</ul>
</td>
<td>
<ul>
<li>Background changes</li>
<li>Adding text overlays or logos</li>
<li>Image cropping or resizing</li>
<li>Color adjustments</li>
<li>Image replacement</li>
</ul>
</td>
</tr>
</tbody>
</table>

### Quality checklist {#quality-checklist}

Before generating content, ensure the following:

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Clear objective**: Clearly states the action, product/service, value, and context.

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Defined target audience**: Specifies the demographic, role, or segment.

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Content type alignment**: Objective matches the selected channel or format.

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Review selections**: Tone, strategy, and locale are chosen, do not include them in the prompt.

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Document focus is specified**: Highlights which content or sections to reference.

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Brand applied**: Appropriate brand guidelines are selected.

![Green check mark](../../assets/do-not-localize/check-box-green.svg) **Realistic scope**: Avoid requests for layout changes, styling, or structural edits.

### Effective marketing objectives {#marketing-objectives}

When crafting marketing objectives, make sure they are clear, actionable, and measurable. Avoid vague or generic statements.

**Examples of good objectives:**

![Green check mark](../../assets/do-not-localize/check-box-green.svg) "Drive sign-ups for the free 30-day trial of the new AI-powered analytics dashboard"

![Green check mark](../../assets/do-not-localize/check-box-green.svg) "Generate leads for the B2B webinar on 'Reducing Cloud Costs by 40%' happening March 15"

![Green check mark](../../assets/do-not-localize/check-box-green.svg) "Promote the limited-time 25% discount on premium subscriptions, ending December 25"

**Examples to avoid:**

![Red cross out](../../assets/do-not-localize/check-box-red.svg) "Promote the product" (too vague)

![Red cross out](../../assets/do-not-localize/check-box-red.svg) "Make people sign deals" (unclear value)

![Red cross out](../../assets/do-not-localize/check-box-red.svg) "Email about new features" (lacks purpose)

#### Structure your objective

Always provide context and the value proposition for producing relevant content. Use the following formula to help you write effective objectives: **Action + Product/Service + Value/Benefit + Urgency/Context**

**Examples of good objectives:**

![Green check mark](../../assets/do-not-localize/check-box-green.svg) "Encourage downloads of the new mobile app that helps users track sustainable living habits with personalized eco-friendly recommendations"

![Green check mark](../../assets/do-not-localize/check-box-green.svg) "Promote registration for the exclusive workshop on advanced data visualization techniques for marketing professionals"

![Green check mark](../../assets/do-not-localize/check-box-green.svg) "Drive attendance to the product launch event showcasing the revolutionary AI writing assistant that saves 5+ hours per week"

**Examples to avoid:**

![Red cross out](../../assets/do-not-localize/check-box-red.svg) "Announce new app" (missing value proposition and context)

![Red cross out](../../assets/do-not-localize/check-box-red.svg) "Get people to sign up for workshop" (lacks specificity about audience and benefit)

![Red cross out](../../assets/do-not-localize/check-box-red.svg) "Promote event" (no clear action, value, or urgency)

#### Example prompts by channel type {#channel-type-practices}

<table style="table-layout: fixed; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Channel</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Email</strong></td>
<td>"Nurture enterprise prospects by showcasing three customer success stories with detailed ROI metrics (Oracle: 45% cost reduction, Accenture: 200% lead increase, Microsoft: 60% time savings). Target IT directors at companies with 1000+ employees"</td>
</tr>
<tr>
<td><strong>Landing Pages</strong></td>
<td>"Convert B2B visitors into qualified leads by demonstrating how the enterprise security solution prevents 99.9% of cyber attacks, with Fortune 500 testimonials and free security audit"</td>
</tr>
</tbody>
</table>

<!-- channels not yet supported
<tr>
<td><strong>SMS</strong></td>
<td>"Alert VIP customers about a 4-hour flash sale on premium electronics with 40% discount, limited to the first 100 customers"</td>
</tr>
<tr>
<td><strong>Push Notifications</strong></td>
<td>"Re-engage users who haven't opened the app in 7 days with personalized content recommendations based on their reading history"</td>
</tr> -->

<!-- Wait on more B2B specific examples

### Industry-specific approaches {#industry-approaches}

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Industry</th>
<th>Example Prompt</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>B2B Technology</strong></td>
<td>"Demonstrate ROI and technical specifications while addressing security concerns for IT decision-makers evaluating our cloud infrastructure solution, emphasizing 99.9% uptime SLA, SOC 2 compliance, and 40% cost savings."</td>
</tr>
<tr>
<td><strong>E-commerce Retail</strong></td>
<td>"Create urgency around limited-stock holiday items while highlighting free shipping and easy returns for last-minute shoppers, emphasizing limited quantities (less than 50 remaining) and 24-hour shipping cutoff."</td>
</tr>
<tr>
<td><strong>Financial Services</strong></td>
<td>"Educate clients about investment portfolio diversification strategies while maintaining regulatory compliance, featuring certified financial advisor insights and risk disclaimers."</td>
</tr>
<tr>
<td><strong>Healthcare & Wellness</strong></td>
<td>"Promote preventive care benefits and annual health screenings while maintaining medical accuracy, featuring board-certified physician recommendations and patient privacy assurances."</td>
</tr>
<tr>
<td><strong>Education & Training</strong></td>
<td>"Emphasize career advancement outcomes and industry certifications while showcasing instructor expertise, highlighting 92% job placement rate and project-based curriculum."</td>
</tr>
<tr>
<td><strong>SaaS Platforms</strong></td>
<td>"Highlight time savings and automation benefits with specific metrics while addressing integration concerns, featuring average 25-hour weekly time savings and integration with 200+ popular tools."</td>
</tr>
</tbody>
</table>
 -->

### New content vs. modification of existing content {#new-vs-modify}

Clearly indicate if your request involves generating new content or updating existing material. This distinction is important because it guides the AI in selecting the appropriate approach and ensures a more accurate and useful outcome.

#### Creating new content

Apply this strategy when you are launching marketing campaigns, unveiling new solutions, or initiating updated/refreshed communication. It ensures that your message starts strong and aligns with your goals.

**How to prompt** &#10148; When creating new content, focus on your marketing objective without referencing existing content.

>[!BEGINSHADEBOX "Examples"]

* **SaaS trial**: "Launch the new CRM software to small business owners, highlighting 50% time savings, 90% faster lead qualification, and offering a 30-day free trial with personalized onboarding"
* **Feature announcement**: "Announce new API integration capabilities that reduce development time by 60% for enterprise customers, targeting technical decision-makers"
* **Event promotion**: "Drive registrations for the webinar on 'Digital Marketing Trends 2024' featuring experts from Google, Meta, and Adobe, emphasizing actionable insights and limited seats (500 max)"

>[!ENDSHADEBOX]

#### Modifying existing content

>[!TIP]
>
>For standard modifications such as elaborate, summarize, or simplify, select **_Refine_** instead of writing custom prompts.

Use a modification prompt when you need to update, refresh, or adapt your current marketing campaigns. This method supports incremental improvements, ensuring your messaging stays relevant without starting from scratch.

**How to prompt** &#10148; When modifying existing content, clearly specify what you want changed and how to change it.

>[!BEGINSHADEBOX "Examples"]

* **Campaign refresh**: "Modify the program launch email to focus on enterprise security features instead of general productivity benefits, targeting IT decision-makers with compliance certifications"
* **Audience pivot**: "Adapt the software demo invitation to target healthcare specifically, replacing generic examples with healthcare use cases and HIPAA compliance benefits"
* **Seasonal update**: "Update the Q3 promotional campaign for Q4 holiday shopping, changing focus from back-to-school to holiday gift giving with fast shipping emphasis"

>[!ENDSHADEBOX]

## Advanced text settings {#text-settings}

In addition to using a clear and well-formed prompt, the text settings in the AI Assistant content tools include text settings that you can use to optimize the generated outputs.

>[!TIP]
>
>Use the _[!UICONTROL Communication strategy]_ and _[!UICONTROL Tone]_ options in the _[!UICONTROL Text settings]_ instead of mentioning these characteristics in your prompt.

### Communication strategy types

Your communication strategy determines how you present your message to maximize impact. Different strategies work better for different goals, whether you are building urgency, establishing trust, or driving immediate action. Choose the strategy that best aligns with your campaign objectives and audience mindset.

| **Strategy** | **Best for** | **Messaging style** | **Examples** |
| ------------ | ------------ | ------------------- | ------------ |
| **Urgent** | Time-sensitive offers, deadlines, immediate action | Creates immediate pressure with time-based language | <li>"Act now: Offer expires at midnight" <li>"Register today before spots fill up" <li>"48-hour flash sale starts now" |
| **FOMO (Fear of Missing Out)** | Limited offers, events, exclusive access | Uses urgency, scarcity, and time-pressure cues | <li>"Only 24 hours left! Limited stock at 40% off" <li>"Last chance: Early bird pricing ends tomorrow" <li>"Only 100 beta spots remaining" |
| **Social Proof** | Trust-building, testimonials, popular products | Leverages others' experiences and validation | <li>"Join 50,000+ satisfied customers" <li>"Rated 4.9/5 stars by industry professionals" <li>"Trusted by Fortune 500 companies" |
| **Scarcity** | Limited inventory, exclusive releases, high-demand items | Emphasizes limited availability and exclusiveness | <li>"Only 5 left in stock" <li>"Limited edition: 100 units available" <li>"Exclusive release: First come, first served" |
| **Incentive** | Promotions, reward programs, special offers | Highlights tangible benefits and rewards | <li>"Get 20% off your first order" <li>"Earn double points this weekend" <li>"Free shipping on orders over $50" |
| **Exclusivity** | Premium products, VIP experiences, members-only offers | Uses premium positioning and special-access language | <li>"Exclusive invitation to a private preview" <li>"Elite membership unlocks advanced analytics" <li>"Join select Fortune 500 companies already using us" |
| **Gamification** | Engagement campaigns, loyalty programs, interactive content | Uses game mechanics and achievement language | <li>"Unlock your next reward level" <li>"Complete challenges to earn badges" <li>"Climb the leaderboard for exclusive prizes" |
| **Informative** | Education, research, complex products, thought leadership | Uses facts, data, insights, and explanation | <li>"5 insights from analyzing 10,000+ interactions" <li>"New research reveals 3 breakthrough approaches" <li>"Complete guide to implementing AI in marketing" |
| **Education & Insights** | Learning content, industry trends, best practices | Provides valuable knowledge and actionable takeaways | <li>"Learn advanced techniques with an expert guide" <li>"Discover 7 strategies top marketers use" <li>"Learn how to optimize your workflow in 5 steps" |

### Set the right tone {#tone}

Tone shapes how your audience perceives and responds to your message. Always select a tone that aligns with your brand voice and the stage of the profile journey.

Review the available tone options, including when each works best and examples of content that fit each style.

| Tonality | Best for | Content example |
| ---- | ----- | ----- |
| Professional | B2B communications, formal announcements | "We're pleased to announce our strategic partnership..." |
| Empathetic | Customer support, sensitive topics | "We understand how frustrating this issue must be for you..." |
| Humorous | Engaging campaigns, lighthearted content | "Warning: May cause serious productivity gains!" |
| Exciting | Product launches, event promotions | "This is the moment that you've been waiting for!" |
| Inspirational | Motivational campaigns, brand purpose | "Together, we can make a difference in the world..." |
| Persuasive | Sales campaigns, conversions | "Don't miss this limited-time opportunity to..." |
| Friendly | Customer engagement, welcome messages | "Glad you're here with us!" |
| Formal | Legal communications, official notices | "This is a notification of the following changes..." |
| Apologetic | Service recovery, issue resolution | "Bodea sincerely apologizes for any inconvenience caused..." |
| Assertive | Leadership content, authoritative messaging | "Here's what you need to do right now..." |
| Storytelling | Brand narratives, emotional connections | "It all started with a simple question..." |
| Conversational | Nurture campaigns, relationship building | "Let's talk about how this program can help you..." |

## Optimized reference content {#reference-content}

>[!TIP]
>
>If you have already uploaded an asset through the **[!UICONTROL Reference content]** menu, you do not need to reference it in your prompt. The system automatically uses any selected documents.

Reference content files provide factual information that enriches your generated content with specific, accurate details. When you upload documents, such as product brochures or white papers, alter your prompt to include which parts have focus:

* **Instead of** _"Use the product brochure"_ **you should use** _"Focus on the advanced security features and compliance certifications, specifically SOC 2 compliance and data encryption"_

* **Instead of** _"Reference the case studies"_ **you should use** _"Highlight ROI results from healthcare clients, specifically the 40% cost reduction at Regional Medical Center"_

* **Instead of** _"Include technical details"_ **you should use** _"Emphasize API integration capabilities and developer benefits, focusing on REST API endpoints and 99.9% uptime SLA"_

### Content refinement

After content is generated, use the **_[!UICONTROL Refine]_** feature to iterate and enhance it with the following options:

* **[!UICONTROL Elaborate]** - AI Assistant can help you expand on specific topics, providing additional details for better understanding and engagement.

* **[!UICONTROL Summarize]** - Lengthy information can overload page viewers. Use AI Assistant to condense key points into clear, concise summaries that grab attention and encourage them to read further.

* **[!UICONTROL Rephrase]** - Rewrite the message while preserving its meaning. This option helps you generate alternative wording, improve flow, or adjust phrasing without changing the core message.

* **[!UICONTROL Use simpler language]** - Simplify the language, ensuring clarity and accessibility for a wider audience.

* **[!UICONTROL Translate]** - Translate the text to another language. (Currently, English is the only supported language.)

* **[!UICONTROL Change tone]** - Adjust the tone of the message to align with your communication style, such as making it more friendly, professional, urgent, or inspirational.

* **[!UICONTROL Change Communication strategy]** - Modify the messaging approach based on your objectives, such as creating urgency, or emphasizing exciting appeal.
