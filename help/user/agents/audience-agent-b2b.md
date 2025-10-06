---
title: Audience Agent B2B
description: Audience Agent B2B in Journey OptimizerB2B Edition uses intent analysis and persona mapping to create buying groups and accelerate B2B marketing workflows. 
feature: Audiences, AI Assistant
role: User
hidefromtoc: yes
---
# Audience Agent B2B

Powered by [Adobe Experience Platform Agent Orchestrator](https://experienceleague.adobe.com/en/docs/experience-cloud-ai/experience-cloud-ai/agents/agent-orchestrator), Audience Agent B2B is available in Journey Optimizer B2B Edition. Using this agent enhances efficiency and effectiveness in exploring and scaling audiences, accelerating buying group creation and seamless workflows for journey activation:

* **_Prioritize target audiences by intent_** - Infer personas based on product intent for various audiences and streamline campaign planning, reducing time spent on audience validation.

* **_Leverage AI to detect buying groups_** - Use AI, structured, unstructured data, and unified first-party data to streamline buying group discovery and creation.

![Audience Agent B2B in full page mode](./assets/audience-agent-full.png){width="700" zoomable="yes"}

## Audience Agent capabilities

| Area | What it does | Business value |
| ---- | ------------ | -------------- |
| Intent analysis | <li> Measure account intent strength (such as low, medium, and high) for specific products. <li>Compare product interest trends over time (such as top products in the last _n_ days). <li>Identify accounts actively showing interest in specific products. <li>Surface engagement patterns that combine account activity with persona coverage. | <li>Helps teams focus on the right accounts at the right time. <li>Improves pipeline quality by prioritizing accounts with genuine purchase signals. <li>Enables proactive engagement before competitors act. |
| Persona mapping | <li>Detect and rank top personas by product intent. <li>Identify personas involved in buying one or multiple products. <li>Map personas to functional roles (Champion, Decision Maker, Influencer, etc.) with justification. <li>Validate why a given person is considered a champion. | <li>Ensures sales engages the true decision-makers and influencers. <li>Reduces wasted effort on low-impact contacts. <li>Increases win rates by aligning outreach with buyer power dynamics. |
| Buying group evaluation | <li>Assess buying group size (e.g., groups with more than n members). <li>Measure persona coverage across accounts (e.g., below x%). <li>Track role distribution and coverage gaps within buying groups. <li>Highlight accounts with champions identified in recent deals. | <li>Reveals coverage gaps that could stall deals. <li>Strengthens multi-threading strategies by ensuring full role representation. <li>Improves deal health tracking through group-level engagement insights. |

## Prompt Examples

These prompt samples demonstrate some of ways you can use the agent:

* Show the trend window: earliest and latest updated for account product intent per product.
* For `<product>`, list buying groups with product intent and scores.
* For `<product>`, list personas and roles with their opportunity metrics (win rate, membership rate, counts).
* For accounts in `<industry>`, what is the average account persona coverage for `<product>`?
* Which accounts have low intent for any product but still have open opportunities (worth nurturing)?
* Which accounts added new intent signals for `<account_name>` this week?
