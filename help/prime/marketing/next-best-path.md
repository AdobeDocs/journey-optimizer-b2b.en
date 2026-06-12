---
title: Next Best Path Node
description: Use the Next best path node in Journey Optimizer B2B Prime for AI-driven journey routing with natural language prompts, path simulation, confidence scores, and live split path results.
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
---
# Next best path node

In Journey Optimizer B2B Prime, the *Next best path* node brings AI-driven split path decisioning directly into the journey canvas. Instead of configuring filter conditions on a [split paths](./split-merge-paths-nodes.md) node, you describe your intent in natural language and let the system determine the most relevant path for each person.

In B2B buying, a profile may appear to be one type of buyer, but their behavior, firmographic data, and engagement context reveal a more nuanced story. The next best path node evaluates that context to make an intelligent routing decision, while letting you review, modify, or override any AI recommendation before activating the journey.

## Path decisioning {#path-decisioning}

There are three steps to go from intent to activation.

* **Step 1: Define paths** — Add a Next Best Path node into your journey, name each path, and write a natural language prompt describing who should progress down the path. You can add or remove paths at any time.

* **Step 2: Simulate** — Pick a sample audience and run a simulation. You see profile counts per path, confidence scores, and the AI reasoning so that you can validate the logic before activating.

   >[!NOTE]
   >
   >Simulation runs only against sample data and never affects live journey execution.

* **Step 3: Activate** — Publish the journey against your real audience. The AI evaluates each person at runtime, assigns the best-fit path in real time, and a default fallback ensures that no one hits a dead end.

### AI decisioning inputs {#ai-decisioning-inputs}

When a person reaches the node, the system fetches profile context, applies constraints, and uses an LLM to select the best-fit path. The AI evaluates each person using a combination of the following inputs:

* **Engagement history** – Email opens, link clicks, web page visits, and other behavioral signals from the current and prior journeys
* **Real-time signals** – High-intent events such as form fills and pricing page visits
* **Profile attributes** – Demographics, job title, persona, and firmographic data
* **Account attributes** – Firmographic and technographic data associated with the person's account

### AI context building {#ai-context-building}

Underlying the routing decision, the AI constructs an inferred layer for each profile. It combines demographic and firmographic data, account details, and behavioral signals (such as persona details, problem intent, and product intent) into a contextual summary for that person. Using this enriched context, the AI can route each person to the optimal path and provide both a confidence score and the natural-language reasoning behind each decision.

Each decision is logged with a confidence score and natural-language reasoning for transparency and observability.

If no path is a strong match, or if the prompt references data not available for a profile, the person is routed to the default fallback path.

## Add a next best path node {#add-node}

1. Open the person journey and navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **Next best path**.

   The node is added to the canvas and the AI split configuration panel opens on the right. It starts with one path and a default *Other people* path to route people who do not qualify for any of the defined paths.

## Configure paths {#configure-paths}

For each path, define a name and a natural language prompt that describes who should be routed there. Prompt input replaces the filter condition UI entirely; there are no attribute conditions to configure.

1. Click **Add path** for each additional path you want to include.

   To remove a path, click the *Delete* icon on the path card.

1. For each path card in the right panel:

   * Enter a **Label** that reflects the audience or intent for that segment.

   * Enter a **Prompt** in natural language describing who belongs on this path. Focus on intent and outcome, not specific attribute values.

     **Example prompts for a three-path split:**

     * *Path 1 – HR Leaders:* Identify people in HR leadership roles most likely to engage with talent management and employee experience content.
     * *Path 2 – Technical Evaluators:* Identify technical stakeholders most likely to engage with product architecture, integrations, and implementation content.
     * *Path 3 – Business Decision-Makers:* Identify business stakeholders most likely to engage with ROI, business outcomes, and case study content.

1. If needed, reorder paths to set the priority order for matching.

   Path filtering is evaluated in top-down order. Each person proceeds along the first path that matches. Click the up and down arrows at the top right of each path card to move it higher or lower in the list.

1. Review the default path (last in the path list) and change the label if needed.

   The default path is used when the AI cannot confidently assign a person to any defined path or when the relevant data is unavailable. When a prompt references data that does not exist in the dataset for a given profile, the system routes that profile to the default path and flags the data gap.

>[!BEGINSHADEBOX]

**Human-in-the-loop controls**

AI recommendations are non-binding. Before activating the journey, you can:

* Edit any path prompt to refine the routing logic.
* Add, remove, or reorder paths.
* Override AI suggestions with custom conditions as needed.

AI-driven path assignments do not take effect until you publish the journey.

>[!ENDSHADEBOX]

## Prompt examples by use case {#prompt-examples}

The following examples show how to write effective path prompts across common B2B marketing use cases. Use them as starting points and adapt the language to match your journey context and audience data.

+++Active research and buying signals

**Path 1 – Active product researchers**
*Identify people actively researching CRM software. Look for repeated product page visits, engagement with comparison content, frequent return visits, and elevated third-party intent signals over the past 30 days.*

**Path 2 – Pricing comparison behavior**
*Identify users who have viewed pricing or plan comparison pages multiple times in the last 14 days, especially those alternating between pricing and feature documentation pages.*

**Path 3 – High intent, no conversion**
*Identify high-intent visitors who have engaged with product demos, pricing pages, or integration documentation in the last 21 days but have not submitted a form or converted.*

**Path 4 – Hesitant checkout behavior**
*Identify users who started checkout or demo booking flows but did not complete them, and who returned at least once afterward without converting.*

+++

+++Churn and retention risk

**Path 1 – Churn risk signals**
*Identify customers showing signs of churn based on declining product usage, reduced login frequency, support ticket spikes, and decreased marketing engagement over the last 60 days.*

**Path 2 – Disengaging power users**
*Identify previously engaged users whose engagement velocity has dropped significantly in the past 30 days compared to their historical baseline.*

+++

+++Education to evaluation gaps

**Path 1 – Research to pricing sequence**
*Identify users who downloaded an ebook and then visited the pricing page within 7 days but did not request a demo.*

**Path 2 – Webinar without follow-up**
*Identify people who attended a webinar and subsequently returned to product pages but never booked a demo or contacted sales.*

**Path 3 – Comparison-led evaluation**
*Identify visitors who viewed a competitor comparison article and then visited integration or migration documentation within 14 days.*

+++

+++Email engagement sequences

**Path 1 – Opens without clicks**
*Identify leads who opened three or more marketing emails within 30 days but never clicked through to the website.*

**Path 2 – Clicked but no deeper engagement**
*Identify users who clicked from an email to a product page but did not explore additional pages or return within 7 days.*

+++

+++Trial and conversion patterns

**Path 1 – Fast converters**
*Identify customers who upgraded within 30 days of starting a trial and showed high in-product engagement during the trial period.*

**Path 2 – Trial stalled users**
*Identify trial users who logged in during the first week but showed minimal activity afterward and did not convert before trial expiration.*

+++

+++Multi-channel buyers

**Path 1 – Ad and organic convergence**
*Identify users who first engaged via paid ads and later returned through direct or organic channels within 14 days.*

**Path 2 – Event to product evaluation**
*Identify accounts that engaged at an in-person or virtual event and subsequently increased product research behavior within 30 days.*

**Path 3 – Social-to-site researchers**
*Identify users who engaged with social content and later visited high-intent pages like pricing or demo booking.*

+++

+++Regional buying signals

**Path 1 – Surge in specific region**
*Identify accounts in North America showing increased product research activity and elevated third-party intent signals in the past 30 days compared to their historical baseline.*

**Path 2 – Emerging market momentum**
*Identify accounts in APAC where engagement velocity has increased significantly in the past 14 days, even if overall engagement volume is still moderate.*

**Path 3 – Region-specific enterprise interest**
*Identify enterprise-sized accounts in EMEA engaging with compliance, data residency, or security documentation in the past 21 days.*

**Path 4 – Underpenetrated territory**
*Identify high-fit accounts in assigned sales territories that have shown intent signals but that sales has not yet contacted.*

+++

+++Webinar audience targeting

**Path 1 – HR leaders interested in AI**
*Identify people who have engagement on HR sites (shrm.org, hbr.org/topic/human-resource-management), interested in Journey Optimizer over the last 30 days, who are likely to attend a webinar on "AI in HR Operations". They should have also shown some interest in AI products.*

**Path 2 – Finance professionals interested in AI**
*Identify people who have engagement on Finance sites (wsj.com/finance, investopedia.com), interested in Marketo over the last 30 days, who are likely to attend a webinar on "AI in Financial Planning". They should have also shown some interest in AI products.*

**Path 3 – Risk and research practitioners interested in AI**
*Identify people who have engagement on Risk/Research sites (mckinsey.com/capabilities/risk-and-resilience, forrester.com/research), interested in GenStudio over the last 30 days, who are likely to attend a webinar on "AI in Risk Management". They should have also shown some interest in AI products.*

+++

+++Behavioral timing signals

**Path 1 – After-hours researchers**
*Identify users repeatedly engaging with product and pricing pages outside of normal business hours in their local timezone.*

**Path 2 – Compressed research window**
*Identify accounts showing unusually high engagement density within a short 72-hour window across multiple product areas.*

**Path 3 – End-of-quarter activity spike**
*Identify accounts with a surge in evaluation-stage activity during the last 30 days of the fiscal quarter.*

+++

## Simulate decisioning before publishing {#simulate}

Use simulation to test how the AI evaluates your prompts against a real audience before the journey goes live. Simulation is available only while the journey is in *Draft* status and has no effect on any published journey.

### Run a simulation {#run-simulation}

1. Select the next best path node and click the *Simulate* icon at the top of the right panel.

1. In the dialog, choose the audience to use for the simulation:

   * **[!UICONTROL Original person lists]** – Use the audience from the audience node. Specify a sample size when the full audience exceeds the simulation threshold.
   * **[!UICONTROL Dynamic and static lists]** – Use a Marketo Engage static or dynamic list.
   * **[!UICONTROL Test records]** – Use AI-suggested test profiles.

   >[!NOTE]
   >
   >* If the selected audience exceeds the simulation threshold, the system runs the simulation on a 100-profile sample. An indicator in the UI shows that results are sample-based.
   >* If the selected audience is not yet materialized, simulation is blocked. An inline warning directs you to materialize the audience first.

1. Click **[!UICONTROL Simulate]**.

### Review simulation results {#review-results}

After the simulation runs, the right panel displays the distribution of profiles across each path and the AI reasoning behind those assignments:

| Result | Description |
|---|---|
| **Profiles** | The number of profiles routed to the path. |
| **Split** | The percentage of profiles routed to the path. |
| **Confidence** | The AI confidence level for the path assignment. Confidence reflects data freshness, signal strength and consistency, and the historical success of similar routing patterns. |
| **Prompt** | The prompt that was evaluated for the path. |
| **AI reasoning** | A natural-language explanation of why profiles were collectively assigned to this path. |

>[!NOTE]
>
>When available data or scope limits a decision, the results include information about the limitation. For example, when a required attribute is not present in the dataset, the results include an explicit indicator explaining how the missing data impacted the results.

Use the results to refine prompts and confirm that the routing reflects your intended outcome. You can modify path prompts and re-run the simulation as many times as needed before publishing.

## Publish and monitor the journey {#publish-monitor}

After validating the simulation results:

1. Connect the people audience to the journey entry node.

2. [Publish the journey](./journeys-overview.md).

After the journey is live, the next best path node runs at execution time. As each person reaches the node, the AI evaluates them in real time using the latest signals and routes them to the most relevant path.

For a published journey, open the journey map and select the next best path node to view the **_[!UICONTROL Live results]_** section in the right panel. Live results show:

* The percentage distribution of profiles across each path
* The confidence score for each path assignment
* Path-level and profile-level reasoning, with expandable detail for individual profiles

Live results are also available in the Journey Console and through the Journey Observability skill in the AI Hub.