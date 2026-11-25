---
title: Journey Skills for B2B
description: Learn how to prepare journey briefs, review validated draft graphs, configure saved drafts, and inspect account and person journeys through Coworker chat.
feature: Account Journeys, Person Journeys, Agentic AI
role: User
exl-id: 5d2945ab-4f6c-4d9c-b0a1-1a93dc1849f3
autotag-review: '2026-06-05T16:42:46.785Z'
TQID: 'https://experienceleague.adobe.com/SgjavYf2Tp5yO8s3f0DQexRCUILQRsD5bM6UwmbcgyE'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: ff10f619-348f-47e3-99bf-3ce4c817cf2c
    internal-label: Agentic AI
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Journey skills for B2B

Use [!DNL Adobe CX Enterprise Coworker] Chat to find, create, and configure journeys in [!DNL Adobe Journey Optimizer B2B Edition]. Create validated drafts from a brief, change saved draft graphs and re-entry settings, and configure unconfigured nodes. Journey changes apply to saved drafts, not active journeys.

For the lookup, creation, and rules skill identifiers and their supported actions, see the [Coworker journey skills reference](./coworker-overview.md#skills). This article provides brief preparation guidance and journey observability examples:

* [Journey creation guidance](#journey-creation-skills): Prepare a brief and review a draft before creation.
* [Journey observability guidance](#journey-observability-skills): Ask questions about how accounts and people move through active journeys.

For instructions on opening the app and starting conversations, use the [Coworker interface guide](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}.

## Journey creation skills {#journey-creation-skills}

The journey creation skill turns a brief into a validated account or person journey graph. It resolves the named audience to its [!DNL Adobe Experience Platform] audience ID and previews the graph before creating a draft.

You must explicitly approve the preview before [!DNL Coworker] creates the draft. The creation skill does not discover audiences, configure node rules, author message copy, publish, or delete journeys.

### Prepare a brief {#basic-usage}

Describe the draft journey that you want in natural language. Include the following details:

* Journey type: Account or person.
* Existing audience: The name or ID of the audience to use.
* Journey flow: The actions, waits, and branches to include.
* Re-entry settings: Whether and when accounts or people can re-enter.

Include relevant details from your campaign brief so that [!DNL Coworker] can interpret the goal. Refine the request if the preview does not match your intended flow.

![Journey creation prompt in Coworker Chat.](./assets/coworker-chat-b2b-journey-prompt.png){width="800" zoomable="yes"}

### Review and create a draft {#end-to-end-b2b-journey-creation}

Review the journey type, resolved audience, nodes, and paths in the validated preview. Approve creation only when the graph matches your brief.

After approval, [!DNL Coworker] creates the draft and returns its link. Use a follow-up request to configure its unconfigured nodes through the rules skill. Add message copy in the application, then complete the [journey review and publishing steps](../journeys/create-publish-journey.md).

For a complete example, see [Build an account journey](./coworker-overview.md#build-account-journey).

### Multi-stage journeys

For a journey with multiple stages, describe each stage's actions, waits, and branches in the brief. Distinguish the graph structure from the rules and message copy that you configure after draft creation.

To revise a saved draft, request graph or re-entry changes through the creation skill. Use the rules skill for split conditions, actions, events, and the dynamic list audience on unconfigured nodes.

## Journey observability skills {#journey-observability-skills}

The journey observability skills let you ask natural language questions about how accounts and people are moving through your B2B journeys—without digging through journey maps, logs, or dashboards. They cover two main areas: journey progression and data sync observability.

![Journey observability prompt and response in [!DNL CX Coworker]](./assets/journey-observability-prompt-response.png){width="800" zoomable="yes"}

### Account-level journey insight

Trace how a specific account flowed through a journey by asking questions like:

* "Give me basic info on Bodea Cloud accounts."
* "Tell me how account Northstar Services went through the journey ABM Nurture Strategy."
* "When did account Contoso LLC start this journey?"

### Split-path reasoning and counts

Understand why a branch was taken and how many people or accounts followed each path:

* "Why did account QiDemoAccount24 go to the small US California tech path at split node c764a9?"
* "Give me the people count for each path in split node node-459c7c."
* "Show me people in the San Jose path for Account8."

Journey observability skills analyze split logic, account attributes, and activities to explain routing decisions and return per-path counts or people lists.

### People-level journey outcomes

Analyze individual outcomes within an account or across an entire journey—especially useful for buying group analysis and tracing decision maker vs. influencer behavior:

* "Give me people count in each split path for Bodea Next Web Engagement journey."
* "List people in the hidden skip path."
* "Show me people in the San Diego location path for this account."

### Journey lifecycle and timing

Retrieve key timestamps for a journey or specific accounts:

* "When did this journey go live?"
* "When did the first account enter this journey?"
* "When did account QiDemoAccount50 start this journey?"

### External audience and activation visibility

For journeys that push to external channels such as LinkedIn, you can check activation status:

* "Is bsmith@acme.com in the external audience?"
* "List all people activated to LinkedIn through ObservabilityExtAudience01."

### Data sync and pipeline observability

The journey observability skills can also surface data sync health information to help troubleshoot why an account or lead was not included in a journey:

* External audience export job metrics and status
* Batch segmentation schedules and completion times
* Buying group maintenance scheduling
* Job manager stats (completed/failed)