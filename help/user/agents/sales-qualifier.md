---
title: Sales Qualifier
description: Automate B2B prospect qualification and outreach with Sales Qualifier. It provides AI-powered research, email drafting, CRM integration, and AI outbound workflows for BDRs.
feature: Agentic AI, Sales Insights, Account Journeys
role: User
exl-id: cc590444-41df-44fe-830b-92241718ee81
autotag-review: '2026-06-05T16:42:16.451Z'
TQID: 'https://experienceleague.adobe.com/VNgs0cTpjCTG7JpFjFErnVMmRtR-gmw-iRRHZanZDUs'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
  - id: fc1ff3b2-6614-41ad-a113-de48597598fd
    internal-label: Sales Experience
  - id: f979fe0e-02fe-4599-b492-7b3df1d4e7dc
    internal-label: Intelligent Insights
subfeature_v2:
  - id: fe583b80-65a2-48c2-b4e1-9ea8fbac0a8a
    internal-label: CRM integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
---
# Sales Qualifier

Sales Qualifier is an AI-driven application that you can use with Adobe Journey Optimizer B2B Edition. It implements the Account Qualification Agent and is designed to streamline workflows for Business Development Representatives (BDRs). Sales Qualifier automates prospect qualification, outreach, and buyer engagement workflows across channels. It reduces manual BDR load and accelerates pipeline velocity for Enterprise B2B companies.

BDRs can use the browser and email plugins to access business intelligence directly within CRMs or Outlook. The following video provides a short demonstration of the Sales Qualifier and Account Qualification Agent.

>[!VIDEO](https://video.tv.adobe.com/v/3476550)

## Application home

Sales Qualifier is included with [!UICONTROL Journey Optimizer B2B Edition], but it is a separate app within the Adobe Experience Platform.

![Sales Qualifier home screen](./assets/home-screen.png){width="800" zoomable="yes"}

### Account Qualification Agent

The Account Qualification Agent (AQA) is the core of the Sales Qualifier. The AQA uses AI to read your accounts and determine which ones are ready for the next step. It assists with research, email drafting, and CRM-informed context when your organization has connected the CRM.

<!--
## Edit the left navigation bar

At the bottom left of the application, click the _Edit_ ( ![Edit icon](../assets/do-not-localize/icon-edit.svg) ) icon to control which elements are visible in the left navigation. You can also drag and drop them to reorder as you want.
-->

### Basic agent usage

Adobe AI agents use _natural language queries_, which means they use the same language in the text prompt as you do when speaking with a person. The more detailed you are, the better the results.

Using natural language, you can ask the agent to:

* `Tell me the latest financial results of Bodea`
* `Tell me more about hiring at TechNova`
* `Tell me about the new AI features in Bodea LumaSecure4`

Iterate your outbound workflows by refining your prompts to get the results you need. For example:

* _Draft a follow-up email drawing from context like earnings calls or reports._ Up to 120 words. Subject line: Captivating, incorporating a key theme. Intro: Start with a direct quote from context sources. Body: Connect to pain points and value propositions. CTA: Propose a short call to explore further._

* _The goal of this email is to start a conversation and build credibility._ Draft an email under 120 words that has a consultative and empathetic tone. Avoid an overly familiar or sales approach and do not use the phrases "hope you are well," "just checking in," or "please."_

### Product access and user groups

Access to Sales Qualifier features is managed through two user groups in Adobe Admin Console. Product administrators must set up the groups during onboarding before users can access the application.

#### Sales Qualifier users

Users must be members of the `Sales Qualifier` user group to access the Sales Qualifier application.

1. In Adobe Admin Console, create a user group named `Sales Qualifier`.
1. Assign the **Default Production All Access** AEP profile to the group.
1. Add users who need access to Sales Qualifier.

#### Sales Qualifier administrators

Administrators who configure [CRM connections](#integrations-and-crm), the [Knowledge Center](#knowledge-center), and global email opt-out settings must also be members of the `Sales Qualifier Admins` user group.

1. In Adobe Admin Console, create a user group named `Sales Qualifier Admins`.
1. Add the administrators to both the `Sales Qualifier` and `Sales Qualifier Admins` groups.

Membership in both groups makes **[!UICONTROL Admin Settings]** visible under **[!UICONTROL Administration]** in the left navigation. Standard users can use the configured fields, filters, and playbook, and the configured opt-out footer is applied to their outbound emails. They cannot change these settings.

>[!NOTE]
>
>User group names must match exactly as shown in the preceding steps.

## Prospects

Select **[!UICONTROL Prospects]** in the left navigation to view a list of the leads that you can access. The list provides a quick review of information, such as lead status and last activity.

![Prospects table displaying lead status and last activity for prospect management](./assets/prospects.png){width="800" zoomable="yes"}

### Build your prospect list

The prospect list combines people from more than one source:

* **CRM-sourced prospects** – When you connect a CRM, it automatically imports leads owned by the connected user. See [Integrations and CRM](#integrations-and-crm).
* **Imported prospects** – Import a lead list from a CSV file.
* **Manually added prospects** – Add an individual person directly in the app.

To add prospects that do not come from your CRM:

1. On the **[!UICONTROL Prospects]** page, select **[!UICONTROL Add prospects]**.
1. Choose **[!UICONTROL Import CSV]** or **[!UICONTROL Add manually]**.

   * For a CSV import, upload the file and map its columns to prospect fields.
   * To add a person manually, enter their details in the form.

1. Select **[!UICONTROL Save]**.

### Filter and find prospects

Select the _Filter_ ![Filter icon](../../assets/do-not-localize/icon_filter-outline.svg) icon to narrow the list. You can filter by:

* Lead status
* Engagement score
* Interesting moments flagged by marketing
* Star score and flame score
* Associated deals

Administrators can also make mapped CRM fields available as filters. In **[!UICONTROL Admin Settings]**, they turn on **[!UICONTROL Filterable]** for the fields that reps use to find prospects. See [Map CRM fields](#map-crm-fields-inbound-mapping).

### Review prospect details

Select a prospect to open their profile. Review the signals that matter before you reach out:

* **Activity list** – A chronological list of the prospect's activities, with an **AI activity summary** at the top that highlights the most relevant recent behavior.
* **Timeline view** – A visual timeline of engagement across channels.
* **Viewed content** – Open the actual content a prospect viewed, such as a web page or asset, directly from an activity.

## Accounts

Select **[!UICONTROL Accounts]** in the left navigation to work with the accounts you sell into. Sales Qualifier brings together firmographic detail, pipeline, and engagement so that you can prioritize outreach at the account level.

The account overview summarizes essentials like revenue, industry, company size, and headquarters. Alongside these details, each account surfaces:

* **Open opportunities** – The open opportunities associated with the account, sourced from your connected CRM, so that you can align outreach with active pipeline.
* **Top engaged members** – The contacts at the account with the most recent engagement, so that you know who to prioritize within the buying group.
* **CRM inputs** – Account fields, opportunities, and owner information surfaced from your connected CRM. See [Integrations and CRM](#integrations-and-crm) for how this data is mapped.

### Account deep dive

To start a deep dive, open an account. The Account Qualification Agent (AQA) prioritizes the signals that are most relevant to your organization's selling strategy, so that you can quickly understand where the account stands and decide what to do next.

## Outbound workflows

>[!NOTE]
>
>Outbound workflows created by product administrators are shared with all users in your organization.

An _outbound workflow_ is the structure Sales Qualifier uses to run a goal-driven cadence. You define an outreach goal and targeting criteria and the AI proposes a multi-touch cadence and writes personalized email content for each prospect. You review and approve each email before enrollment activates the cadence so that messages send only during your configured window.

An outbound workflow connects four elements:

* **Goal** – The outcome you want from the outreach (for example booking a discovery call or driving event registration).
* **Targeting filters** – Conditions that determine which prospects are eligible.
* **Cadence of touchpoints** – The ordered sequence of steps, each on a scheduled day. Touchpoints can be **emails**, **phone calls**, or **LinkedIn InMails**.
* **Personalized email content** – For each email touchpoint, the AI drafts content using the prospect profile, account context, engagement history, and recent news.

The goal drives everything downstream: the AI uses it to suggest targeting filters, design the cadence, draft touchpoint prompts, and shape personalization for every generated email.

![Outbound workflow Overview tab](./assets/outbound-workflow-overview.png){width="800" zoomable="yes"}

### Key concepts

| Concept | Description |
| --- | --- |
| **Workflow** | A reusable outbound activity defined by a goal, targeting filters, cadence, and settings. |
| **Goal** | What the outreach should accomplish. |
| **Touchpoint** | One step in the cadence (email, phone call, or LinkedIn InMail), scheduled relative to enrollment. |
| **Touchpoint prompt** | Instructions the AI follows when generating email body and subject for a prospect—tone, length, focus, and call to action. |
| **Cadence** | The full sequence of touchpoints: how many, in what order, and on which days. |
| **Targeting filter** | A condition that limits the workflow to a subset of prospects. |
| **Draft** | A generated email that is ready for review but not yet approved. |
| **Reasoning** | The AI's explanation of how it wrote a given email (which signals and data sources it used). |
| **Enrollment** | Approving a prospect's drafts, which activates the cadence and queues emails to send during the workflow's send window. |

The following sections describe the full lifecycle: creating a workflow in the wizard, reviewing generated emails, approving prospects, and managing workflows over time.

### Create an outbound workflow

Workflow creation is a five-step wizard: **Goal**, **Targeting**, **Generate touchpoints**, **Settings**, and **Add prospects**. Each step builds on the last; your initial goal shapes every subsequent decision.

1. In the left navigation, select **[!UICONTROL Outbound workflow]**.

1. On the **[!UICONTROL Browse]** tab, click **[!UICONTROL + Create workflow]** in the upper-right corner.

#### Step 1: Define your goal

The goal is the most important input: it tells the AI what success looks like and anchors targeting, cadence, and email generation.

1. Choose **[!UICONTROL Start from scratch]** to write your own goal, or **[!UICONTROL Start from template]** to use a saved template.

   ![Create outbound workflow Start from scratch](./assets/outbound-workflow-create-start-from-scratch.png){width="700" zoomable="yes"}

1. Choose one of the **[!UICONTROL Recommended goals]** as a starting point, or enter your own goal.

1. Click **[!UICONTROL Next: Targeting]**.

Goals work best when they state a **concrete outcome**, not only a topic. To give the AI more to work with, use a goal like `Book a 15-minute discovery call with marketing leaders evaluating campaign automation` instead of `Promote campaign automation`.

#### Step 2: Configure targeting filters

Targeting filters define which prospects are eligible. When you add prospects later, only those prospects who match these filters appear in the selection list.

1. Click the down arrow to display the **[!UICONTROL Add a filter]** list and select a filter to apply.

   ![Create outbound workflow Targeting filters](./assets/outbound-workflow-create-targeting-filter-list.png){width="700" zoomable="yes"}   

1. Set values for the filter.

1. Add more filters if you need to narrow the audience.

   ![Create outbound workflow Targeting added filters with values](./assets/outbound-workflow-create-targeting-filters-values.png){width="600" zoomable="yes"} 

1. Click **[!UICONTROL Next: Generate touchpoints]**.

#### Step 3: Generate and review touchpoints

After targeting is set, the AI builds the **_cadence_**: it analyzes your goal and targeting, defines the touchpoint sequence, and writes a **_touchpoint prompt_** for each step. You see a multi-step cadence with each touchpoint on a specific day. The cadence can mix email, phone call, and LinkedIn InMail steps.

![Outbound workflow generated touchpoint cadence and prompts](./assets/outbound-workflow-create-touchpoints.png){width="700" zoomable="yes"} 

To read its prompt, expand an email touchpoint. This instruction guides the AI when writing each prospect's email, including tone, length, focus, and _call to action_.

**Regenerate the cadence**

If the cadence is not what you want, click **[!UICONTROL Regenerate]** and enter a refinement instruction. For example:

* `Make it 3 touchpoints across 2 weeks`
* `Lead with an executive briefing offer in the first email`
* `Add a nurture touch focused on a relevant case study`

The AI rewrites the full cadence based on your instruction.

To adjust a single email touchpoint without regenerating the whole cadence, edit the prompt text directly in its text area.

**Use a playbook in your prompts**

If your organization has built a playbook in the [Knowledge Center](#knowledge-center), you can direct the AI to draw from it when writing emails. In the prompt, name the document and the context you want the AI to use—for example, `Use the ABC positioning guide from the Knowledge Center and focus on the security value proposition`. The generated emails then reflect the messaging in that playbook.

When the cadence and prompts look right, click **[!UICONTROL Next: Settings]**.

Refining touchpoint prompts before per-prospect generation matters: those prompts are the core instructions the AI uses for every prospect later. Time spent here scales across all generated emails.

#### Step 4: Configure workflow settings

The **Settings** step controls how the workflow runs.

![Outbound workflow settings](./assets/outbound-workflow-create-settings.png){width="700" zoomable="yes"} 

1. Review the **[!UICONTROL Workflow name]** and change it if you want a clearer label.
1. In **[!UICONTROL Max prospects per workflow]**, confirm the upper limit on how many prospects the workflow can manage at once.
1. Set the **[!UICONTROL Send window]** for the hours when outbound emails are allowed to send.
1. Turn on **[!UICONTROL Skip Weekends]** to move any touchpoint that falls on a weekend to the next business day.
1. To stop follow-up touchpoints automatically once a prospect books a meeting, turn on **[!UICONTROL Meeting Booking Pause]**.
1. Confirm that the **[!UICONTROL Timezone]** matches your audience.
1. Click **[!UICONTROL Save and add prospects]**.

The opt-out footer is configured globally by an administrator and applies to outbound emails independently of the workflow settings. See [Global opt-out sync](#global-opt-out-sync).

#### Step 5: Add prospects and start email generation

Saving opens the prospect selection view, already filtered by your Step 2 targeting.

![Outbound workflow add prospects](./assets/outbound-workflow-create-add-prospects.png){width="700" zoomable="yes"}

1. Review the list.

   Rows typically include prospect name, account, email, job title, engagement status, and prospect status.

1. Adjust filters here if you need to expand or narrow the list.
1. Select prospects using the checkboxes.
1. Click **[!UICONTROL Next: Review touchpoints]** to start **per-prospect** email generation.

The AI generates personalized emails for every selected prospect for **each email touchpoint** in the cadence. Phone and LinkedIn InMail touchpoints remain in the cadence as scheduled steps. Generation can run in the background—use **[!UICONTROL Notify when ready]** if you want to continue other work while it completes.

For each prospect, the AI combines each touchpoint prompt with prospect-specific data (person, account, engagement history, recent news) to produce subject line and body.

### Review and refine generated emails

When generation finishes, the workflow detail view shows a banner to review drafts. Review is required and nothing sends until you approve.

![Outbound workflow review generated emails](./assets/outbound-workflow-create-review-generated-emails.png){width="700" zoomable="yes"}

1. In the workflow detail view, click **[!UICONTROL Review drafts]** in the banner.
1. The **[!UICONTROL Review touchpoints]** step has two tabs:
   * **[!UICONTROL Ready for Review]** – Emails that have finished generating.
   * **[!UICONTROL Generating]** – Emails still being written.
1. In the prospect list on the left, click a name to load that prospect's touchpoints on the right.
1. Use the chevron (**>**) on a touchpoint to expand and read the full subject line and body.

#### Read the AI reasoning

For each generated email, **[!UICONTROL Reasoning]** explains how the AI crafted that message, including signals, attributes, and sources that shaped the content and call to action. Review this information and validate personalization before you approve.

![Outbound workflow generated email AI reasoning](./assets/outbound-workflow-create-review-generated-email-reasoning.png){width="600" zoomable="yes"}

#### Edit emails directly

For small edits (wording, tone, a single sentence):

1. On the expanded touchpoint, click the _Edit_ icon to open the editor.
1. Edit the subject line or body.
1. Click **[!UICONTROL Save]**.

#### Refine emails with AI

For larger changes (restructure, shift emphasis, or reframe the message), use **[!UICONTROL Generate with AI]**. The AI agent rewrites the email while keeping personalization context.

1. In the email editor, click **[!UICONTROL Generate with AI]**.

   ![Outbound workflow generated email refinement with AI](./assets/outbound-workflow-create-review-generated-email-edit-regenerate.png){width="600" zoomable="yes"}

1. Enter a clear instruction, for example:
   * `Make it shorter and more direct. Keep it under 100 words.`
   * `Focus more on the prospect's role and how the solution helps them specifically.`
   * `Change the call-to-action to suggest a 15-minute introductory call instead.`
1. Review the revision and tweak manually if needed.
1. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Direct edits suit wording and tone. Use _[!UICONTROL Generate with AI]_ to rewrite the email from scratch.

### Approve and enroll prospects

Approval activates the cadence for a prospect. Until a prospect is approved and enrolled, the system does not send emails to them.

1. In the left prospect list, select the prospects whose emails you have reviewed and are ready to send.
1. Click **[!UICONTROL Approve and enroll prospects]** (lower-right).

![Outbound workflow select and approve prospects](./assets/outbound-workflow-create-approve-enroll-prospects.png){width="700" zoomable="yes"}

Approved emails send during the workflow **send window** in the configured **timezone**, on each touchpoint's scheduled day relative to enrollment. Prospects you do not approve remain in **[!UICONTROL Ready for Review]** until you act. After approval, the workflow runs according to the cadence you defined.

### Manage existing workflows

On the _[!UICONTROL Outbound workflow]_ page, the **[!UICONTROL Browse]** tab lists every workflow. Each card shows the goal, configured touchpoints, and performance metrics. Use this view to monitor active workflows, return to drafts that still need review, or open a workflow to add more prospects.

### Outbound workflow best practices

* **Invest in the goal.** Downstream targeting, cadence, and emails all trace back to the goal. Specific, outcome-focused goals outperform vague ones.
* **Finalize touchpoint prompts before per-prospect generation.** After bulk generation, changes are typically made one prospect at a time.
* **Use Reasoning as a quality check.** If the wrong signal is emphasized—or an obvious one is missing—edit the email or revisit the touchpoint prompt and regenerate the cadence.
* **Match the editing tool to the change.** Direct edits for wording and tone; **[!UICONTROL Generate with AI]** for restructuring or reframing.
* **Approve only what you have reviewed.** Expand touchpoints, read the content, and refine where needed before enrollment.

### Global opt-out sync

Administrators can append a light-touch unsubscribe footer that uses pre-approved [!DNL Marketo] verbiage to every outbound email. When a prospect selects the opt-out link, Sales Qualifier permanently suppresses the prospect from further emails and syncs the opt-out status back to the connected CRM. See [Configure global email opt-out](#configure-global-email-opt-out).

## Email outbox

The Email outbox panel lists all the automated emails that you have sent.

<!--
## Meeting bookings

This panel displays all meetings set up through automation.

## Chat inbox

This panel displays all your chat threads.

![Panel showing chat threads with contact and thread summaries for sales automation](assets/chat-inbox.png)

You can interact with clients, and see summaries for the contact and the thread so that you can quickly know where you are in the thread.

-->

## Tasks

The _Tasks_ area in Sales Qualifier gives Business Development Representatives (BDRs) a dedicated space to manage and process their outbound workflow actions. The outbound workflow engine automatically generates tasks that represent the specific actions a BDR needs to take with each prospect — phone calls, LinkedIn InMails, and email reviews.

The task management experience is a **processing queue**, not a to-do list. You can open a task, take action, mark it complete, and move to the next one — all without leaving the page.

Select **[!UICONTROL Tasks]** in the left navigation bar to open the full tasks page. This page is the primary workspace for processing tasks one by one.

![Tasks page showing the task queue and detail panel](./assets/tasks.png){width="800" zoomable="yes"}

<!--
**Homepage feed** - The homepage displays a running feed of your most urgent tasks, with overdue items at the top followed by today's tasks. Each item in the feed has an "Open" button that takes you directly to that task in the Tasks page with the detail panel already loaded.
-->

### Task types

All tasks are tied to outbound workflow steps. There are three types:

**Phone Call** — Created when a cadence reaches a phone call step. The task panel shows agent-generated pitch points and an inline notes field for capturing call notes.

**LinkedIn InMail** — Created when a cadence reaches a LinkedIn InMail step. The task panel shows an AI-generated subject line and message body that you can copy and send outside the product.

**Email Review** — Created once the system finishes generating personalized emails for a prospect enrolled in a workflow. You review and approve the emails before outbound begins for that prospect. Each prospect gets a separate Email Review task; if you enroll 10 prospects in a workflow, you see up to 10 Email Review tasks as generation completes.

### Task management

The Tasks page is split into two panels:

* **Left — Task list:** Your queue of tasks, ordered and filtered based on your selected view and sort settings.
* **Right — Task work panel:** Details for the selected task, including prospect information, workflow context, task-specific content, and action controls.

Selecting any task in the left panel loads its details into the right panel without navigating away from the page.

#### Queue controls

The work panel includes **Next** and **Previous** controls to move through your task queue in order. The queue respects whatever sort and filter settings you apply to the list. So if you're working through overdue phone call tasks sorted by due date, _Next_ and _Previous_ move through exactly that set.

When you mark a task complete, the panel automatically advances to the next task in the queue.

#### Notes

For Phone Call and LinkedIn InMail tasks, an inline notes field is available in the work panel. Notes auto-save when you click away so that you do not lose them when you navigate to another task before marking the current one complete.

#### Task actions

Use the following actions to manage your tasks:

* **[!UICONTROL Mark Complete]** - The primary action. Use this action after you've executed the task — made the call, sent the InMail, or reviewed and approved the emails. On completion, the task is recorded as **Completed** and the queue advances automatically.

* **[!UICONTROL Skip Touchpoint]** - Available from the overflow menu in the work panel. Use this option when you cannot complete this step, but the prospect remains a valid target in the workflow.
   * The prospect advances to the next step in the cadence. Future tasks still generate on schedule.
   * Select a reason: *Bad contact info*, *Bad timing*, *Content not relevant*, or *Other* (with a freetext field).
   * The task status is set to **Skipped** and logged with the reason and timestamp.
   * If this was the last step in the workflow, the prospect's workflow run ends. The task is still logged as Skipped (not Removed).

* **[!UICONTROL Remove from Workflow]** - Available from the overflow menu in the work panel. Use this when the prospect no longer belongs in this workflow.

   When you remove a prospect from a workflow:
   * All pending and future tasks for that prospect within this workflow are cancelled.
   * The prospect's enrollment status changes to **Removed by BDR**.
   * Select a reason: *Left company*, *Duplicate*, *Wrong fit*, *Already converted*, or *Other* (with a text field).
   * A confirmation dialog appears: *"This action will cancel all remaining touchpoints for [Prospect] in [Workflow Name]. Continue?"*
   * The task status is set to **Removed**. All cancelled sibling tasks are also marked **Removed**.

>[!NOTE]
>
>Skip and Remove reason data informs analytics, including channel skip rates, workflow removal rates, and top reasons. This helps improve workflow quality and informs performance analysis over time.

**Automatic skipping**

Stagnant LinkedIn InMail and phone call tasks are skipped automatically if they remain incomplete for two days. Automatic skipping keeps a prospect moving through the cadence without stalling the run, and it does not affect the email timeline. Scheduled email touchpoints continue to send as planned.

### Task status

Each task moves through the following states:

| Status | Description |
|---|---|
| **Pending** | Created but the preceding workflow step hasn't completed yet. Not visible in your task list. |
| **Upcoming** | The preceding step is complete, but the due date is in the future. Visible and actionable — you can complete it early if the moment is right. |
| **Open** | Due today. Visible and actionable. |
| **Overdue** | Past due date, not yet completed. Visible, actionable, and visually flagged. |
| **Completed** | You executed and marked the task complete. |
| **Skipped** | You skipped this touchpoint. The prospect advances in the workflow. |
| **Removed** | You removed the prospect from the workflow. All sibling tasks are cancelled. |
| **Cancelled** | System-cancelled due to a workflow change or prospect removal. |

### List views

Use the tabs at the top of the task list to switch between views:

* **Today** *(default)* — Tasks due today that haven't been completed.

* **Overdue** — Tasks whose due date has passed and are still open. Address these tasks first.

* **Upcoming** — Tasks with a future due date where the preceding workflow step has already been completed. These tasks are visible early so you can plan ahead or act sooner if the timing is right (for example, if you're already on a call with a prospect). The scheduled due date is displayed so you know the intended timing.

* **Completed** — A record of tasks you've completed, skipped, or removed. Useful for review and audit purposes.

### Filtering and search

There are multiple ways to filter the task list:

* Filter by task type using a multi-select list. Selecting multiple types shows tasks matching *any* of the selected types (Phone Call **or** Email Review, for example).

* Filter by task status. Selecting multiple statuses shows tasks matching any of the selected statuses.

* Filter across groups using **AND** logic. For example, `Type = Phone Call and Status = Overdue` shows only overdue call tasks.

Use the search bar to find tasks by prospect name, company name, or engagement name. Search applies alongside any active filters. Text-match only — exact partial matches, no fuzzy search.

### Sorting

Use the **Sort by** control to choose how the task list is ordered. Sorting also determines the order in which Next and Previous move through the queue.

| Sort Option | Behavior |
|---|---|
| **Due Date (Ascending)** *(default)* | Oldest due date first. Overdue tasks appear before today's tasks. |
| **Due Date (Descending)** | Latest due date first. |
| **Created Date (Newest)** | Most recently created tasks first. |
| **Created Date (Oldest)** | Oldest created tasks first. |
| **Task Type** | Grouped by type in order: Phone Call → LinkedIn InMail → Email Review. Within each group, sorted by due date ascending. |

### Overdue tasks

A task becomes overdue the day after its due date if it hasn't been completed. Overdue tasks:

* Appear in the **Overdue** view and at the top of the homepage feed.
* Are visually flagged with an "Overdue" badge in the task list.
* Remain fully actionable — you can complete, skip, or remove them.

### Upcoming tasks

Upcoming tasks are created the moment a prospect completes a workflow step, even if the next step due date is still in the future. This visibility gives you early insight into your pipeline so you can plan ahead or act early when the opportunity arises.

Upcoming tasks show their scheduled due date, so you always know when they're intended to be addressed. Completing an upcoming task early is fully supported — the workflow engine records the actual completion date and advances the prospect normally.

### Task completion

Task completion isn't limited to the Tasks page.

**Engaged Prospect view:** Touchpoint previews on an engaged prospect's page include a _Mark complete_ action alongside a content preview and optional notes field. Completing a task here updates its status in the Tasks page immediately. This view doesn't trigger auto-advance behavior — it's a view-and-act surface, not a queue-processing surface.

**Salesforce (CRM Plugin):** The Sales Qualifier plugin in Salesforce displays task status (upcoming, pending, completed, overdue, skipped) within the outbound workflow card. In the current version, the CRM card is **read-only** — you can see task status but must complete tasks from within Sales Qualifier.

### Empty states

* **Today with no tasks:** You see a _You're all caught up for today_ message. If upcoming tasks exist, a prompt appears as _You have [N] upcoming tasks — view upcoming_.
* **Overdue tasks present:** A prompt encourages you to address overdue tasks first.

## Meeting booking

Sales Qualifier turns engaged conversations into booked meetings without leaving the outbound flow. When you connect your calendar, Sales Qualifier generates a personal booking link that prospects use to schedule time with you.

* **Booking links** – Configure your calendar connection and availability in [Profile settings](#profile-settings). Your booking link can be added to your email signature so that it appears in outbound emails.
* **Automatic insertion in a cadence** – Sales Qualifier inserts your booking link at suitable points in a cadence, so that the invitation to meet appears when it is most relevant. You can override the placement manually.
* **Booking pause** – When a prospect books a meeting, **[!UICONTROL Meeting Booking Pause]** stops further follow-ups automatically. See [Configure workflow settings](#step-4-configure-workflow-settings).

Track booking outcomes in the [Performance](#performance) section.

## Knowledge Center

The _[!UICONTROL Knowledge Center]_ gives the Account Qualification Agent (AQA) access to your own sales materials, so that Sales Qualifier can generate research, qualification insights, and outreach that reflect how your organization sells. Building and managing the playbook is an administrator task.

![Knowledge Center](./assets/integrations-knowledge-center.png){width="700" zoomable="yes"}

### Upload sales collateral

1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**.
1. Select **[!UICONTROL Knowledge Center]** under **[!UICONTROL Integrations]**.
1. Set the **[!UICONTROL Company name]** and **[!UICONTROL Company URL]** that Sales Qualifier uses to research your company and draft emails.
1. Upload sales plays, ideal customer profiles (ICPs), positioning guides, and other sales collateral in PDF, PPTX, or DOCX format.

Each uploaded document displays its processing status, such as **[!UICONTROL Ready]**, and when it was last updated.

### Build a playbook

After you upload your documents, select **[!UICONTROL Build Playbook]** to turn them into a playbook.

>[!NOTE]
>
>A playbook takes about 24 hours to process before it is ready to use.

When the playbook is ready, it feeds both outreach and assistance:

* **Outbound email prompts** – Reference the playbook when generating emails by naming the document and context in your prompt. See [Generate and review touchpoints](#step-3-generate-and-review-touchpoints).
* **Conversational Sales Assistant** – To pull from the playbook, point the assistant at the Knowledge Center. See [Conversational Sales Assistant](#conversational-sales-assistant).

## Conversational Sales Assistant

The Conversational Sales Assistant is a chat experience where you ask questions in natural language and get answers grounded in your sales context. The assistant draws on:

* Your internal knowledge base, including any [Knowledge Center](#knowledge-center) playbook
* CRM signals from your connected CRM
* [!DNL Marketo] activity and engagement data
* Web research

Use the assistant to prepare before outreach—for example, to build account positioning ahead of a meeting. To pull from a built playbook, point the assistant at the Knowledge Center in your question. For example: `From the Knowledge Center, help me position our security solution for ABC Corp ahead of tomorrow's call.`

## Performance

The **[!UICONTROL Performance]** section shows how your outbound is doing, so that you can see what is working and where to adjust.

### Email performance

Review the volume and effectiveness of your outbound email:

* Emails sent
* Open rate
* Click rate
* Reply rate

Sales Qualifier identifies out-of-office replies and bounces with their corresponding statuses, so that you can distinguish them from prospect engagements.

### Meeting booking performance

Meeting-booking status cards summarize where your booked meetings stand. Filter the cards to focus on the meetings and statuses you want to review.

## Integrations and CRM

With integrations, Sales Qualifier connects to your CRM so that the Account Qualification Agent (AQA) and outbound workflows share a consistent view of leads, accounts, contacts, activities, and owners in Salesforce or Microsoft Dynamics 365. Sales Qualifier reads CRM sales data and activities to enrich insights, and it can write back logged outreach activities and opt-out status. It does not otherwise modify your CRM records through this connection.

CRM connections, inbound field mapping, and activity synchronization are configured by an administrator under **[!UICONTROL Administration]** > **[!UICONTROL Admin Settings]** > **[!UICONTROL CRM connections]**. Standard users consume the configured CRM data and filters but cannot change these settings.

### CRM MCP and the embedded plugin

Sales Qualifier works with your CRM in more than one way:

* **Query CRM data through the CRM MCP** – The Account Qualification Agent queries live CRM data through the CRM MCP, so that answers and insights reflect the current state of your records.
* **Embedded plugin** – The embedded CRM plugin surfaces [!DNL Marketo Sales Insights] (MSI) core insights alongside the new agentic data, directly in your CRM. From the plugin, add a prospect to Sales Qualifier in one click.
* **Activity sync-back** – When an administrator enables **[!UICONTROL Activity sync]**, outreach activities sync back to the CRM, so that reps see Sales Qualifier activity in the tools they already use.

>[!IMPORTANT]
>
>Accessing **[!UICONTROL Admin Settings]** requires membership in both the `Sales Qualifier` and `Sales Qualifier Admins` user groups.

### CRM access scope

Sales Qualifier reads the CRM entities it needs and can write back only a defined set of data. Typical entities read include users, contacts, owner mappings, leads, accounts, opportunities, and activities. Write-back is limited to logged outreach activities and opt-out status. Your CRM administrator prepares API access in Salesforce or Dynamics. You then connect Sales Qualifier, map inbound fields, and choose whether to sync activities in the app.

>[!NOTE]
>
>The credential steps that follow describe read access to CRM objects. If you enable activity sync or opt-out write-back, work with your CRM administrator to grant the corresponding write access required by your CRM configuration.

### Prepare credentials in your CRM

Work with your CRM administrator before you connect Sales Qualifier. The following summarizes what is usually created in each system.

#### Microsoft Dynamics 365 (Dataverse / Power Platform)

1. In Azure Active Directory, register an application (**[!UICONTROL App registrations]**).

   Note the **Client ID** and **Tenant ID**, and create a **Client Secret**.

1. In the **[!UICONTROL Power Platform admin center]**, open your environment and go to **[!UICONTROL Settings]** > **[!UICONTROL Users + permissions]** > **[!UICONTROL Application users]**.

1. Create an application user linked to that Azure AD app.

1. Assign a security role that grants **read** access to the entities Sales Qualifier needs, such as leads, contacts, accounts, opportunities, and activities.

   The app requires a security role with read access to read data.

**Information to provide when connecting Dynamics:**

* Client ID
* Client Secret
* Tenant ID
* Dynamics instance URL (organization URL)

#### Salesforce

In Salesforce, [create an External Client App](https://help.salesforce.com/s/articleView?id=xcloud.create_a_local_external_client_app.htm&type=5) (or a _Connected App_) with OAuth enabled and scopes that allow API access to identity and data, following your org's security standards. The integrating user must have read access to objects such as leads, accounts, contacts, tasks, events, and opportunities. Administrative tasks often require a user with **[!UICONTROL Manage Connected Apps]** (among other permissions) to view a consumer key and secret after creation.

>[!PREREQUISITES]
>
>To create an External Client App, a product administrator should verify that you have the following enabled (from Profile or Permission Set):
>
>* Customize Application
>* View Setup and Configuration
>* Modify All Data
>* Manage Connected Apps (important)
>
>   If _Manage Connected Apps_ is not enabled, you cannot view the client ID and client secret after you create the External Client App.

When you create the External Client App, enable OAuth and give permissions. Also enable the following client credentials:

* Access the identity URL service (id, profile, email, address, phone)
* Manage user data via APIs (api)
* Access unique user identifiers (openid)

After you create the app, enable client credentials flow again and use contact email as the username.  When client credentials are enabled, configure a user to _Run As_.

Ensure that the configured user has read access to the following objects:

* Leads
* Accounts
* Contacts
* Tasks
* Events
* Opportunity
* OpportunityContactRoles
* OpportunityLineItems

**Information to provide when connecting Salesforce in Sales Qualifier:**

* Client ID (Consumer Key)
* Client Secret (Consumer Secret)
* Callback URL (as configured on the connected app)
* Salesforce instance URL

>[!IMPORTANT]
>
>Do not send client secrets by email. Use your organization's approved secure channel to share credentials with whoever enters them in Sales Qualifier.

### Connect to your CRM

1. Log in to Sales Qualifier and confirm that the correct sandbox or environment is selected.

1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**.

1. Select **[!UICONTROL CRM connections]** under **[!UICONTROL Integrations]**.

   The page displays cards for Salesforce and Microsoft Dynamics. An inactive connection displays **[!UICONTROL Connect]**. A configured connection displays **[!UICONTROL Connected]** and a **[!UICONTROL Manage]** action.

   ![Admin Settings CRM connections with Salesforce and Dynamics connection cards](./assets/integrations-crm-connections.png){width="800" zoomable="yes"}

1. Click **[!UICONTROL Connect]** for the CRM that you use.

1. Enter the Client ID, secrets, tenant or callback values, and **instance URL** from your CRM administrator.

1. After a successful connection, confirm that the card shows **[!UICONTROL Connected]**.

### Instance URL guidelines

The **instance URL** must be the environment base URL your CRM uses for API and integration configuration—not a UI-only hostname.

**Salesforce**

1. Sign in and note your org _My Domain_ subdomain from the browser address bar (the `{{mydomain}}` value).

1. For Sales Qualifier, use the canonical form: `https://{{mydomain}}.my.salesforce.com` .

   Do **not** use a `lightning.force.com` URL as the instance URL.

**Microsoft Dynamics 365**

1. Open your CRM in the browser and copy the base URL from the address bar.

   It is typically in the form `https://{{org}}.crm.dynamics.com`.

### Map CRM fields (inbound mapping)

After the CRM is connected, select **[!UICONTROL Manage]** for the connection and open **[!UICONTROL Inbound mapping]**. Inbound mapping controls which CRM fields Sales Qualifier pulls into the application.

1. Select an object group: **[!UICONTROL Contact]**, **[!UICONTROL Prospect]**, or **[!UICONTROL Account]**.
1. Select **[!UICONTROL Add Section]** and enter a section name and optional description.
1. Add the CRM fields to the section.

   Each field row displays its **[!UICONTROL Display name]**, **[!UICONTROL Field name]**, and **[!UICONTROL Data type]**.

1. Turn on **[!UICONTROL Filterable]** for each field that should be available as a filter on the **[!UICONTROL Prospects]** list.
1. Preview the mapping and save it.

Mapped fields appear in the corresponding areas of Sales Qualifier:

* Prospect and contact fields appear on the **[!UICONTROL Person]** tab for prospects.
* Account fields appear on the account view.
* Opportunity-related fields appear in the opportunity areas of the account experience.

### Configure activity sync (outbound mapping)

1. From **[!UICONTROL CRM connections]**, select **[!UICONTROL Manage]** for the connected CRM.
1. Open **[!UICONTROL Outbound mapping]**.
1. Turn on **[!UICONTROL Activity sync]** to sync Sales Qualifier outreach activities back to the CRM.

When activity sync is off, Sales Qualifier can continue to use inbound CRM data, but it does not write outreach activities back to the CRM.

### Configure global email opt-out

1. In the left navigation, expand **[!UICONTROL Administration]** and select **[!UICONTROL Admin Settings]**.
1. Select **[!UICONTROL Email settings]** under **[!UICONTROL Compliance]**.
1. Turn on **[!UICONTROL Include opt-out link in every email]** to append an unsubscribe footer to outbound emails.
1. In **[!UICONTROL Opt-out message template]**, enter the footer text. Include the `{{opt_out_link}}` token where the clickable unsubscribe link should appear.
1. Save the settings.

When a prospect selects the link, Sales Qualifier permanently suppresses the prospect from further emails. The opt-out status also syncs back to the connected CRM.

### Reference: sample API parameters

Your CRM team can use these examples to confirm read access returns the expected lead fields.

**Dynamics (OData-style excerpt)**

```text
$select=fullname,_ownerid_value,leadid,emailaddress1,jobtitle,statuscode,createdon,modifiedon,statecode
$filter=_ownerid_value eq '<crmUserId>' [AND additional filters]
$expand=Lead_ActivityPointers(...),parentaccountid(...)
$orderby=modifiedon desc
```

**Salesforce (SOQL excerpt)**

```sql
SELECT Id, Salutation, FirstName, LastName, Name, Title, Company, Email,
  LeadSource, Status, OwnerId, LastModifiedDate, LastActivityDate, CreatedDate,
  (SELECT Id, Subject, ActivityDate, Status FROM Tasks ORDER BY ActivityDate DESC LIMIT 1),
  (SELECT Id, Subject, ActivityDateTime FROM Events ORDER BY ActivityDateTime DESC LIMIT 1)
FROM Lead
WHERE OwnerId = '<crmUserId>' AND IsDeleted = false
ORDER BY LastModifiedDate DESC
```

## Profile settings

The profile settings specify information about yourself, including personal details, email, calendar, and chat availability.

### Email settings

In the **[!UICONTROL Email settings]** tab, set up your email connections.

![Email settings tab showing email connection options and email signature configuration](assets/email-settings.png)

* **[!UICONTROL Email connections]** - Click **[!UICONTROL Connect]** and follow the Microsoft login procedure. 

* **[!UICONTROL Email signature]** - Configure the email signature that is used in auto-generated emails. Add your [meeting booking](#meeting-booking) link to the signature so that prospects can schedule time with you.

### Calendar configuration

On the **[!UICONTROL Calendar configuration]** tab, set your time zone and availability.

<!-- 
![Calendar settings tab showing time zone and availability options](assets/calendar-settings.png)
-->

* **[!UICONTROL Calendar connection]** - Click **[!UICONTROL Connect]** and follow the Microsoft login procedure to integrate your calendar. 

* **[!UICONTROL Meeting confirmation email]** - When a client confirms a meeting with you, they receive the confirmation email as a reply. Use these settings to define the email subject and body.

* **[!UICONTROL Preferences]** - Set your default meeting length and the time between back-to-back meetings.

If you disconnect your calendar:

* Active booking links are effectively disabled.
* The booking page shows a friendly, temporarily unavailable state.
* Reconnecting preserves settings.

### Calendar availability

Your calendar availability in Sales Qualifier is based on two inputs:

* Your connected work calendar (Outlook or Gmail)
* Your configured availability + timeslot rules in _Calendar Settings_.

Sales Qualifier reads free/busy status from the connected calendar, not full event contents, and uses that together with the configured rules to decide which booking slots a prospect can see.

You can configure:

* Working hours by day of week
* Multiple blocks per day (example: 9:00–12:00 and 1:00–5:00)
* Your time zone
* Meeting duration
* Buffer before/after meetings
* Minimum notice
* Booking window

<!-- 
### Chat settings

In the **[!UICONTROL Chat settings]** tab, set your Timezone Live chat availability.

![Chat settings tab for configuring timezone and live chat availability](assets/chat-settings.png)

## Representative management

The _[!UICONTROL Representative management]_ panel displays the defined representatives and their calendar status.

## Meeting performance

This panel presents analytics around your completed meetings.
-->

<!--
 SHPHR-24341 remove section
## Set up the Chrome plugin

The AI Assistant Chrome plugin is available on the [Google Store](https://chromewebstore.google.com/detail/ai-assistant/hancbabllcmckehonngbdkhilocpdfji?authuser=0&hl=en).

When the plugin is installed in Chrome, the Adobe logo appears on the middle right when you are on an integrated site:

* Adobe web applications
* Salesforce
* Outlook
* Microsoft Dynamics and web applications
* Google applications 
-->
