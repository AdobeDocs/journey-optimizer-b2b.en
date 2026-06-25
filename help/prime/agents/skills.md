---
title: AI Assistant Skills
description: Review AI Assistant skills in Journey Optimizer B2B Prime — packaged workflows for programs, journeys, audiences, scoring, content, and send-time optimization.
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
autotag-review: '2026-06-24T23:55:36.649Z'
TQID: 'https://experienceleague.adobe.com/iIi07OBWKxxa-oW-A6VrlkoTS02kmCx8kfMaCe-C-4o'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: ff10f619-348f-47e3-99bf-3ce4c817cf2c
    internal-label: Agentic AI
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# AI Assistant skills

A _skill_ is a packaged workflow the agent knows how to run — the building blocks behind both the `/` menu and natural-language requests. Each skill bundles step-by-step instructions and the specific tools needed for one job (for example, "publish a journey", "compare two people lists", "build a scoring model"). 

>[!NOTE]
>
>Each skill is classified according to whether the skill mutates the [!DNL Journey Optimizer B2B Prime] or [!DNL Marketo Engage] state (**Write**), only queries/analyzes/generates (**Read**), or has co-equal query + mutation functions (**Read+Write**).

## Programs and planning {#programs-planning}

| Skill | What it does | Access | Product surface | Impact / data flow |
|---|---|---|---|---|
| `falco-program-creation` | End-to-end [!DNL Journey Optimizer B2B Prime] program creation — program, subfolders, tokens, lists, journeys. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime]. See _[Create a program from a brief](./program-from-brief.md)_. |
| `adapt-program` | Generate migration stories from [!DNL Marketo Engage] programs for [!DNL Journey Optimizer B2B Prime] adaptation. | Read | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Marketo Engage], writes [!DNL Journey Optimizer B2B Prime] |
| `folder-creation` | Create organizational folders in the asset tree. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `program-creation` *(Build Programs)* | Create Marketo programs from a campaign brief. | Write | [!DNL Marketo Engage] | Reads + writes [!DNL Marketo Engage] |
| `program-planning` *(Plan Campaigns)* | Transform briefs into setup/implementation documents. | Read | [!DNL Marketo Engage] | Reads [!DNL Marketo Engage] |
| `program-qa` *(Validate Programs)* | Validate/audit programs (rules-only, test plan, or brief). | Read | [!DNL Marketo Engage] | Reads [!DNL Marketo Engage] |

## Journeys {#journeys}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `journey-creation` | Create and edit person journeys from natural language. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `journey-edit-dates` | Change a journey's start/end date without publishing. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `journey-publish` | Publish/launch/schedule people journeys. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `journey-stop` | Abort, close, stop, halt, or kill journeys. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `journey-reentry` | Configure re-entry: allow/disallow, cooldown, max entries. | Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `journey-trafficcontrol` | Run a traffic-control simulation showing profile routing. | Read | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Journey Optimizer B2B Prime] (simulation) |
| `journey-observability` | Debug/monitor progression — paths, timing, splits, stalls, dwell. | Read | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Journey Optimizer B2B Prime] + [!DNL Marketo Engage] (static-list check) |

## Audiences and people {#audiences-people}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `audience-creation` | Adapt a [!DNL Marketo Engage] smartlist, create a people list, or add/update rules. | Write | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Marketo Engage] + reads/writes [!DNL Journey Optimizer B2B Prime].  See _[Create audiences for programs](./audience-creation.md)_. |
| `people-list-comparison` | Compare two people lists and show overlapping members. | Read | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Journey Optimizer B2B Prime] |
| `import-leads` | Inspect CSV data quality and commit imports to [!DNL Marketo Engage]. | Read+Write | Both | Reads + writes [!DNL Marketo Engage] |
| `lead-investigation` *(Investigate Leads)* | Investigate a lead's activity, scoring, qualification, lifecycle. | Read | [!DNL Marketo Engage] | Reads [!DNL Marketo Engage] |

## Content and channels {#content-channels}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `content-personalization` | Browse/preview templates and edit content / generate variants. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `asset-tokens` | Full token CRUD on programs/folders/journeys. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `fcs-channels` | Channel lookups and CRUD + publish/stop/delete. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |

## Scoring and signals {#scoring-signals}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `scoring-studio` | List/get scoring models and build/publish them. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] (scoring service); reads [!DNL Marketo Engage] lead fields/activity types. See _[Create custom scoring models](./lead-scoring-model.md)_. |
| `engagementconfiguration` | Show engagement config and edit/update weights. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `intentconfiguration` | Show intent config and set/update weights. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `intent-query` | Query and explain intent scores by person/segment/list. | Read | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Journey Optimizer B2B Prime] |

## Send-time optimization {#sto}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `send-time-optimization` | Check STO status and enable/disable on an email node. | Read+Write | [!DNL Journey Optimizer B2B Prime] | Reads + writes [!DNL Journey Optimizer B2B Prime] |
| `send-time-report` | Fetch/display the STO performance report. | Read | [!DNL Journey Optimizer B2B Prime] | Reads [!DNL Journey Optimizer B2B Prime] |

## Knowledge {#knowledge}

| Skill | What it does | Access | Product | Backend (data flow) |
|---|---|---|---|---|
| `product-knowledge` | Answer how-to/concept questions from [!DNL Journey Optimizer B2B Prime] documentation on Experience League. | Read | Both | Reads external docs — no product data |

## Cross-backend {#cross-backend}

These skills span more than one backend:

- **`adapt-program`** — `gather_program_assets` reads [!DNL Marketo Engage] (`get_program`, `get_smart_campaign`, `list_emails`), then writes via `falcomcp_create_journey` — classic cross-backend.
- **`audience-creation`** — reads [!DNL Marketo Engage] smart lists (`get_smart_list` / `get_smart_campaign`), then writes [!DNL Journey Optimizer B2B Prime] people lists.
- **`journey-observability`** — [!DNL Journey Optimizer B2B Prime] reads plus a `check_lead_in_marketo_static_list` [!DNL Marketo Engage] read.
- **`scoring-studio`** — reads [!DNL Marketo Engage] lead fields/activity types alongside [!DNL Journey Optimizer B2B Prime] scoring service.

All `falco-mcp_*` and journey/token/scoring/STO/FCS tools hit [!DNL Journey Optimizer B2B Prime] services; CSV/program/lead tools hit [!DNL Marketo Engage].
