---
title: Coworker in Adobe Journey Optimizer B2B Edition
description: Learn how to use CX Enterprise Coworker to find, create, and configure account and person journeys, review draft previews, and approve journey creation.
feature: Account Journeys, Person Journeys, Agentic AI
role: User
level: Beginner
autotag-review: '2026-11-24T23:47:29.469Z'
TQID: 'https://experienceleague.adobe.com/gkizS-MB6qEMoG1pMqD3tSCBtcEuv-m-GMD5H6Z4JsY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: 9b63d357-750f-5558-9208-62fc8a356785
    internal-label: Approval
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: c2f21a5c-bae4-56c6-97e3-2fc9a0e6c120
    internal-label: Use Cases
subfeature_v2:
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
---

# [!DNL CX Enterprise Coworker] in [!DNL Adobe Journey Optimizer B2B Edition] {#coworker-overview}

Use [!DNL Adobe CX Enterprise Coworker] Chat to complete tasks in [!DNL Adobe Journey Optimizer B2B Edition]. Describe a goal in plain language. [!DNL Coworker] plans the work, carries it out, validates the results, and presents the work for your approval.

Find existing account and person journeys, create new draft journeys, or update saved drafts. [!DNL Coworker] turns your brief into a validated journey graph and previews it before creating the draft. You must explicitly approve the preview before [!DNL Coworker] creates the journey.

[!DNL Coworker] respects your organization's existing [product permissions](../admin/user-management.md#b2b-product-permissions). You can take only actions that you are already permitted to take. Administrators control when you have write access. For access requirements, see [Enable AI access](../ai-coworker/enable-ai-access.md).

[!DNL Coworker] works across the Adobe ecosystem, not only in [!DNL Journey Optimizer B2B Edition]. For its broader capabilities, see the [Adobe CX Enterprise Coworker Chat overview](https://experienceleague.adobe.com/en/docs/coworker/content/chat/overview){target="_blank"}. For instructions on opening the app and starting conversations, use the [Coworker interface guide](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}.

## Journey skills {#skills}

Use these three skills to inspect journeys, build journey graphs, and configure nodes. Skill identifiers are exact technical names.

| Skill | What it helps you do | Outside the skill's scope |
| --- | --- | --- |
| `journey-lookup-ajob2b` | List, count, find, and explain account and person journeys. Inspect nodes, re-entry settings, and the activities, attributes, or event audience that a journey uses. This skill does not change journeys. | Create or change journeys, configure rules, author message copy, manage buying group templates, publish, or delete. |
| `journey-creation-ajob2b` | Turn a brief into a journey. Select the journey type, resolve the audience to its [!DNL Adobe Experience Platform] audience ID, validate the graph, and preview it. Create the draft after explicit approval. Edit a saved draft's graph and re-entry settings. | Look up existing journeys, configure rules, author message copy, manage buying group templates, discover audiences, publish, or delete. |
| `journey-rules-ajob2b` | Configure split conditions, actions, events, and the dynamic list audience on a saved journey's unconfigured nodes. | Change the graph, look up journeys, author email or SMS copy, discover audiences, or publish. |

For additional prompt guidance, see [Journey skills for B2B](./journey-agent.md). To work with account and person audiences, see [Audience skills for B2B accounts and people](./audience-agent-b2b.md).

## Example use cases {#use-cases}

Use separate requests to build a draft, configure its nodes, and inspect existing journeys.

### Build an account journey {#build-account-journey}

Create an account nurture journey from a brief, then configure its nodes.

Example prompt: _Create an account journey for the Enterprise Target Accounts audience that sends a welcome email, waits three days, then sends a case study email._

1. Describe the audience and journey flow in [!DNL Coworker] Chat.
1. Review the validated journey graph and preview. [!DNL Coworker] resolves the named audience to its [!DNL Experience Platform] audience ID.
1. Explicitly approve the preview. [!DNL Coworker] creates the draft and returns its link.
1. Ask [!DNL Coworker] to configure the draft's unconfigured nodes.
1. Open the draft in [!DNL Journey Optimizer B2B Edition] to add message copy and review the journey.

The result is a draft journey, not a published journey. Complete the [journey review and publishing steps](../journeys/create-publish-journey.md) in the application.

### Inspect and update journeys {#inspect-update-journeys}

Review your journey inventory, then refine a saved draft's split conditions and re-entry settings.

Example lookup prompt: _How many account journeys are live? Show me where journey 14251 has accounts waiting._

1. Ask [!DNL Coworker] for journey counts by state, or find a journey by name or ID.
1. Review the journey details and account counts at each node.
1. Identify the saved draft that you want to update.
1. Ask [!DNL Coworker] to configure its split condition. For example: _For draft journey 14252, make the high intent branch require a pricing page visit._
1. Request the re-entry change. For example: _For draft journey 14252, prevent accounts from re-entering for 30 days._

Changes apply to the saved draft. Publishing is a separate step. For configuration details, see [Split and merge paths](../journeys/split-merge-paths-nodes.md) and [Journey re-entry](../journeys/journey-re-entry.md).

## MCP tools {#mcp-tools}

[!DNL Coworker] uses the following Model Context Protocol (MCP) tools for journey tasks. Read tools inspect existing information, the check tool validates a graph, and write tools change journey settings or drafts.

| Tool | Supported action | Type |
| --- | --- | --- |
| `list_account_journeys` | Return a paginated list of account journeys. | Read |
| `list_person_journeys` | Return a paginated list of person journeys. | Read |
| `count_account_journeys` | Count account journeys by state. | Read |
| `count_person_journeys` | Count person journeys by state. | Read |
| `get_journey` | Read journey nodes and re-entry settings. | Read |
| `get_journey_rules` | Read the configuration targets of a journey's unconfigured nodes. | Read |
| `get_journey_node_catalog` | Return `ruleset_types`, which are valid inputs for rule data. | Read |
| `validate_journey_graph` | Validate an authored draft graph. | Check |
| `create_journey` | Preview the journey with `confirm=false`. After explicit approval, create the draft and return its link. | Write |
| `update_journey` | Change the graph of a saved draft journey. | Write |
| `set_journey_reentry` | Change re-entry settings. | Write |
| `set_journey_split_conditions` | Set split branch conditions. | Write |
| `apply_journey_rules` | Apply `rule_data` for conditions, actions, events, and the dynamic list audience to a journey. | Write |
