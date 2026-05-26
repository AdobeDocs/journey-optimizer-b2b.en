---
title: Next Best Path Node
description: Use AI-driven decisioning to route people along the most relevant journey path based on natural language prompts, behavioral data, and real-time profile context in Journey Optimizer B2B Edition.
feature: Account Journeys, AI Assistant
role: User
autotag-review: '2026-05-20T18:52:08.227Z'
TQID: 'https://experienceleague.adobe.com/idPaG-ZNnNwJjN8yVC3Ay1FZ2XPgtQgrSMNIus4fReI'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
subfeature_v2:
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
---
# Next best path node

The _Next best path_ node brings AI-driven split path decisioning directly into the journey canvas. Instead of configuring filter conditions on a [split paths](./split-merge-paths-nodes.md) node, you describe your intent in natural language and let the system determine the most relevant path for each person.

>[!NOTE]
>
>Next best path nodes are available only in person journeys. They are not supported in account journeys.

In B2B buying, a profile may appear to be one type of buyer, but their behavior, firmographic data, and engagement context reveal a more nuanced story. The next best path node evaluates that context to make an intelligent routing decision, while letting you review, modify, or override any AI recommendation before activating the journey.

The AI evaluates each person against your defined path prompts using a combination of inputs:

* **Engagement history** – Email opens, link clicks, web page visits, and other behavioral signals from the current and prior journeys
* **Real-time signals** – High-intent events such as form fills and pricing page visits
* **Profile attributes** – Demographics, job title, persona, and firmographic data
* **Account attributes** – Firmographic and technographic data associated with the person's account

When a person reaches the node, the system fetches profile context, applies constraints, and uses an LLM to select the best-fit path. Each decision is logged with a confidence score and natural-language reasoning for transparency and observability.

If no path is a strong match, or if the prompt references data not available for a profile, the person is routed to the default fallback path.

## Add a next best path node {#add-next-best-path-node}

1. Open the person journey and navigate to the journey map.

1. Click the plus ( **+** ) icon on a path and choose **[!UICONTROL Next best path]**.

   ![Add journey node - next best path](./assets/add-node-next-best-path.png){width="350" zoomable="no"}

   The node is added to the canvas and the AI split configuration panel is displayed on the right. It starts with one path and a default _Other people_ path to route people who do not qualify for any of the defined paths.

   ![Next best path node](./assets/node-next-best-path-new.png){width="500"}

## Configure paths {#configure-paths}

For each path, define a name and a natural language prompt that describes who should be routed there. Prompt input replaces the filter condition UI entirely; there are no attribute conditions to configure.

1. Click **[!UICONTROL Add path]** for each additional path that you want to include for the node.

   To remove a path, click the _Delete_ ( ![Delete icon](../assets/do-not-localize/icon-delete-outline.svg) ) icon on the path card.

1. For each path card in the right panel:

   * Enter a **[!UICONTROL Label]** that reflects the audience or intent for that segment.

   * Enter a **[!UICONTROL Prompt]** in natural language describing who belongs on this path. Focus on intent and outcome, not specific attribute values.

      <!-- To get prompt ideas, click **[!UICONTROL Suggest prompts]**. The system provides several example prompts tailored to the path context that you can use as-is or adapt. -->

      ![Next best path node - example paths](./assets/node-next-best-path-new.png){width="500"}

      **Example prompts for a three-path split:**

      * _Path 1 – HR Leaders:_ Identify people in HR leadership roles most likely to engage with talent management and employee experience content.
      * _Path 2 – Technical Evaluators:_ Identify technical stakeholders most likely to engage with product architecture, integrations, and implementation content.
      * _Path 3 – Business Decision-Makers:_ Identify business stakeholders most likely to engage with ROI, business outcomes, and case study content.

1. If needed, reorder paths to set the priority order for matching.

   Path filtering is evaluated in top-down order. Each person proceeds along the first path that matches.

   Click the up and down arrows at the top right of each path card to move it higher or lower in the list of paths.

   ![Next best path node - reorder paths](./assets/node-next-best-path-reorder-paths.png){width="500"}

1. Review the default path (last in the path list) and change the label if needed.

   The default path is used when the AI cannot confidently assign a person to any defined path or when the relevant data is unavailable. When a prompt references data that does not exist in the dataset for a given profile, the system routes that profile to the default path and flags the data gap.

### Human-in-the-loop controls {#human-in-the-loop}

AI recommendations are non-binding. Before activating the journey, you can:

* Edit any path prompt to refine the routing logic.
* Add, remove, or reorder paths.
* Override AI suggestions with custom conditions as needed.

AI-driven path assignments do not take effect until you publish the journey.

## Prompt examples by use case {#examples}

The following examples show how to write effective path prompts across common B2B marketing use cases. Use them as starting points and adapt the language to match your journey context and audience data.

### Active research and buying signals {#active-research}

+++Path 1 – Active product researchers

_Identify people actively researching CRM software. Look for repeated product page visits, engagement with comparison content, frequent return visits, and elevated third-party intent signals over the past 30 days._

+++

+++Path 2 – Pricing comparison behavior

_Identify users who have viewed pricing or plan comparison pages multiple times in the last 14 days, especially those users alternating between pricing and feature documentation pages._

+++

+++Path 3 – High intent, no conversion

_Identify high-intent visitors who have engaged with product demos, pricing pages, or integration documentation in the last 21 days but have not submitted a form or converted._

+++

+++Path 4 – Hesitant checkout behavior

_Identify users who started checkout or demo booking flows but did not complete them, and who returned at least once afterward without converting._

+++

### Churn and retention risk {#churn-retention}

+++Path 1 – Churn risk signals

_Identify customers showing signs of churn based on declining product usage, reduced login frequency, support ticket spikes, and decreased marketing engagement over the last 60 days._

+++

+++Path 2 – Disengaging power users

_Identify previously engaged users whose engagement velocity has dropped significantly in the past 30 days compared to their historical baseline._

+++

### Education to evaluation gaps {#education-evaluation}

+++Path 1 – Research to pricing sequence

_Identify users who downloaded an ebook and then visited the pricing page within 7 days but did not request a demo._

+++

+++Path 2 – Webinar without follow-up

_Identify people who attended a webinar and subsequently returned to product pages but never booked a demo or contacted sales._

+++

+++Path 3 – Comparison-led evaluation

_Identify visitors who viewed a competitor comparison article and then visited integration or migration documentation within 14 days._

+++

### Email engagement sequences {#email-engagement}

+++Path 1 – Opens without clicks

_Identify leads who opened three or more marketing emails within 30 days but never clicked through to the website._

+++

+++Path 2 – Clicked but no deeper engagement

_Identify users who clicked from an email to a product page but did not explore additional pages or return within 7 days._

+++

### Trial and conversion patterns {#trial-conversion}

+++Path 1 – Fast converters

_Identify customers who upgraded within 30 days of starting a trial and showed high in-product engagement during the trial period._

+++

+++Path 2 – Trial stalled users

_Identify trial users who logged in during the first week but showed minimal activity afterward and did not convert before trial expiration._

+++

### Multi-channel buyers {#multi-channel}

+++Path 1 – Ad and organic convergence

_Identify users who first engaged via paid ads and later returned through direct or organic channels within 14 days._

+++

+++Path 2 – Event to product evaluation

_Identify accounts that engaged at an in-person or virtual event and subsequently increased product research behavior within 30 days._

+++

+++Path 3 – Social-to-site researchers

_Identify users who engaged with social content and later visited high-intent pages like pricing or demo booking._

+++

### Regional buying signals {#regional-buying}

+++Path 1 – Surge in specific region

_Identify accounts in North America showing increased product research activity and elevated third-party intent signals in the past 30 days compared to their historical baseline._

+++

+++Path 2 – Emerging market momentum

_Identify accounts in APAC where engagement velocity has increased significantly in the past 14 days, even if overall engagement volume is still moderate._

+++

+++Path 3 – Region-specific enterprise interest

_Identify enterprise-sized accounts in EMEA engaging with compliance, data residency, or security documentation in the past 21 days._

+++

+++Path 4 – Underpenetrated territory

_Identify high-fit accounts in assigned sales territories that have shown intent signals but that sales has not yet contacted._

+++

### Behavioral timing signals {#behavioral-timing}

+++Path 1 – After-hours researchers

_Identify users repeatedly engaging with product and pricing pages outside of normal business hours in their local timezone._

+++

+++Path 2 – Compressed research window

_Identify accounts showing unusually high engagement density within a short 72-hour window across multiple product areas._

+++

+++Path 3 – End-of-quarter activity spike

_Identify accounts with a surge in evaluation-stage activity during the last 30 days of the fiscal quarter._

+++

## Simulate decisioning before publishing {#simulate}

Use simulation to test how the AI evaluates your prompts against a real audience before the journey goes live. It is available only while the journey is in _Draft_ status and has no effect on any published journey. Use it to validate routing logic and build confidence in the AI recommendations.

### Run a simulation {#run-simulation}

1. Select the next best path node and click the _Simulate_ ( ![Simulate icon](../../assets/do-not-localize/icon-simulate-outline.svg) ) icon at the top of the right panel.

   ![Next best path - click simulate icon](./assets/node-next-best-path-simulate-select.png){width="500"}

1. In the dialog, choose the audience to use for the simulation:

   * **[!UICONTROL Original person lists]** – Use the audience from the audience node. Specify a sample size when the full audience exceeds the simulation threshold.
   * **[!UICONTROL Dynamic and static lists]** – Use a [!DNL Marketo Engage] static or dynamic list.
   * **[!UICONTROL Test records]** – Use AI-suggested test profiles.

   ![Next best path - Simulate - choose audience](./assets/node-next-best-path-simulate-dialog.png){width="300"}   

   >[!NOTE]
   >
   >If the selected audience exceeds the simulation threshold, the system runs the simulation on a 100-profile sample. An indicator in the UI shows that results are sample-based.
   >
   >If the selected audience is not yet materialized, simulation is blocked. An inline warning directs you to materialize the audience first.

1. Click **[!UICONTROL Simulate]**.

### Review simulation results {#review-simulation-results}

After the simulation runs, the right panel displays how profiles were distributed across each path and the AI reasoning behind those assignments:

| Result | Description |
| ------ | ----------- |
| **Profiles** | The number of profiles routed to the path. |
| **Split** | The percentage of profiles routed to the path. |
| **Confidence** | The AI confidence level for the path assignment. Confidence reflects data freshness, signal strength and consistency, and the historical success of similar routing patterns. |
| **Prompt** | The prompt that was evaluated for the path. |
| **AI reasoning** | A natural-language explanation of why profiles were collectively assigned to this path. |

![Next best path - Simulate - Results for path](./assets/node-next-best-path-simulate-path-result.png){width="400"} 

>[!NOTE]
>
>When available data or scope limits a decision, the results include information about the limitation. For example, when a required attribute is not present in the dataset, the results include an explicit indicator explaining how the missing data impacted the results.

Use the results to refine prompts and confirm that the routing reflects your intended outcome. You can modify path prompts and re-run the simulation as many times as needed before publishing.

## Publish and monitor the journey {#publish-and-monitor}

After validating the simulation results:

1. Connect the people audience to the journey entry node.

1. [Publish the journey](./create-publish-journey.md#publish-a-journey).

After the journey is live, the next best path node runs at execution time. As each person reaches the node, the AI evaluates them in real time using the latest signals and routes them to the most relevant path.

For a published journey, open the journey map and select the next best path node to view the **[!UICONTROL Live results]** section in the right panel. Live results show:

* The percentage distribution of profiles across each path
* The confidence score for each path assignment
* Path-level and profile-level reasoning, with expandable detail for individual profiles

Live results are also available in the Journey Console and through the [Journey Observability skill](../agents/journey-agent.md#journey-observability-skill) in the AI Hub.
