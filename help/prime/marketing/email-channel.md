---
title: Email Channel
description: Add email action nodes to account journeys - create new emails or use existing Marketo Engage emails for targeted communications in Journey Optimizer B2B Edition.
feature: Email Authoring, Account Journeys
role: User
autotag-review: '2026-06-18T20:30:25.418Z'
TQID: 'https://experienceleague.adobe.com/K3OZnLvtSdwSq6AT4JlRQ62t32d6smIJ4K9EEnK-QUc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
    internal-label: Tiers
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
    internal-label: Prime
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Email channel

[!DNL Adobe Journey Optimizer B2B Prime] brings a modern, enterprise-grade email authoring and delivery experience to B2B marketers. This release introduces redesigned email design tools and a complete set of email deliverability controls.

>[!NOTE]
>
>If you are sending an email for the first time, make sure that the [email channel and deliverability](../admin/configuration-email-deliverability.md) is configured. 

## Email channel overview {#overview}

* **Email channel configurations** - Manage the sender identity, reply behavior, marketing vs. transactional message types, and tracking.
* **Email deliverability controls** - Set up your email deliverability channel, including subdomain delegation (Fully Delegated and CNAME methods), DMARC, SPF/DKIM auto-configuration, and shared IP pool support.
* **Send Email action** - From a journey, add a _Send email_ action node, including personalization using profile attributes (Handlebars syntax).
* **Visual drag-and-drop email design tools** -  Design your email content with structures, content components, themes, dark-mode support, and reusable visual fragments.
* **Marketo Design Studio assets** — Choose images and assets from a one-time copy of your Marketo Engage asset library directly inside the email canvas.
* **Reusable templates and fragments** — Save common headers, footers, CTAs, and full email layouts and reuse them across journeys.
* **Role-Based Access Control (RBAC)** — Apply granular permissions for creating, editing, approving, and sending email.

## Key concepts {#key-concepts}

Before creating emails for person journeys and authoring email content, review these concepts:

| Concept | In [!DNL Journey Optimizer B2B Prime] Prime |
| ------- | ---------------------- |
| **_Email design space_** | The visual canvas and design tools used to compose email content. It includes drag-and-drop layout components, templates, fragments, themes, and a personalization editor. |
| **_Template_** | A reusable email layout that is available for creating a new email. It can be either a built-in sample template provided by Adobe or a custom-built template created by your team. |
| **_Visual fragment_** | A reusable block of content (such as a header, footer, CTA, legal disclaimer) that can be inserted into multiple emails. Updating a fragment propagates the change to every email that uses it. |
| **_Theme_** | A reusable styling preset (colors, typography, spacing, button styles) applied across an email. |
| **_Personalization token_** | A Handlebars expression — for example, `{{profile.firstName}}` — resolved at send time using each recipient's profile data. |
| **_Send Email action_** | The journey action node that uses a channel configuration and email content to deliver an email. |

## Add an email from a journey

To send email from a journey, add a _Take an action_ node and configure it to send email.

1. In the journey canvas, click the **+** icon and select **[!UICONTROL Take an action]**.

1. In the node properties on the right, set the action to **[!UICONTROL Send email]**.

    ![Take an action - Send email](./assets/person-action-node-send-email.png){width="450"}

1. Choose the Email source:

   * **Create/edit email** - Choose this option to define the email content including the subject line, sender information, and email body in the email design space.

   * **[!UICONTROL Use an AI-personalized email]** - Choose this option to refine an AI_generated email in the email design space. These emails are optimized so that AI-assisted inbox clients ground their summaries and answers in your offers and calls to action.

1. Click **[!UICONTROL Create email]**.

1. In the _[!UICONTROL Create email]_ dialog, enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional). 

1. Click **[!UICONTROL Create]**.

## Define the email properties and actions

1. With the _[!UICONTROL Send email]_ node selected in the journey canvas, click **[!UICONTROL Edit email]** in the node properties on the right.

<!-- Staging environment broken -->

for the email and a **[!UICONTROL Subject line]**.

   This opens the **[!UICONTROL Actions]** tab where you can select or create the email configuration to use.

1. (Optional) Select a rule set in the Business rules to apply capping rules to your email action.

You can use the [Send time optimization option](./email-send-time-optimization.md) to predict the best time to send the message to maximize engagement based on historical open and click rates. Learn how

Select the Edit content button and create your content as desired using the Email Designer.

Go back to the journey canvas. If necessary, complete your journey flow by dragging and dropping additional actions or events.

For more information on how to create, configure and publish a journey, refer to this page.


### Define email settings {#email-settings}

Configure settings in the **[!UICONTROL Details]** tab of the node summary panel.

| Setting | Description |
| ------- | ----------- |
| **[!UICONTROL From name]** | Sender name displayed in the email header. Supports personalization tokens. |
| **[!UICONTROL From email]** | Sender email address. Defaults from channel configuration. Supports personalization. |
| **[!UICONTROL Reply-to address]** | Address that receives replies from recipients. Supports personalization. |
| **[!UICONTROL Subject line]** | Email subject line. Editable from the value entered at creation. |
| **[!UICONTROL Branding domain]** | Domain used for brand-specific sending. |
| **[!UICONTROL Dedicated IP]** | Specific IP address for tracking deliverability. |
| **[!UICONTROL Operational email]** | When enabled, bypasses opt-out and unsubscribe suppression. Use only for legitimate operational messages. |
| **[!UICONTROL Include view as web page]** | Generates a web page link for the email content. |
| **[!UICONTROL Disable open tracking]** | Prevents tracking of email open activity. |
| **[!UICONTROL Preheader]** | Short summary text displayed after the subject line in inbox previews. |
| **[!UICONTROL CC addresses]** | Add up to 25 Lead or Company email fields to receive a copy. |

### Check alerts {#alerts}

[!DNL Journey Optimizer B2B Prime] surfaces issues in the top-right corner of the email editor. Resolve all errors before activating the journey — warnings are recommendations only.

**Errors** (prevent journey activation):

* From name is empty
* Subject line is missing
* Email content is empty

**Warnings** (recommendations):

* Opt-out link is not present in the email body
* Text version of HTML is empty
* Empty links detected
* Email exceeds 100 K
