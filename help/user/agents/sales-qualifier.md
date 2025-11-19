---
title: Sales Qualifier 
description: Automate B2B prospect qualification and outreach with Sales Qualifier. It provides AI-powered research, email drafting, CRM integration, and engagement plans for BDRs.
feature:  AI Assistant, Sales Insights, Account Journeys
role: User
---

# Sales Qualifier

>[!NOTE]
>This feature is currently in Limited Availability and is not available to all users.
>

Sales Qualifier is an AI-driven add-on application to Adobe Journey Optimizer B2B Edition that contains the Account Qualification Agent and is designed to streamline workflows for Business Development Representatives (BDRs). Sales Qualifier automates prospect qualification, outreach, and buyer engagement workflows across channels. It reduces manual BDR load and accelerates pipeline velocity for Enterprise B2B companies.
Use the browser and email plugins to access business intelligence directly within CRMs or Outlook.

Sales Qualifier is included with Journey Optimizer B2B Edition, but it is a separate app within the Exprerience Platform Experience Cloud.

![Sales Qualifier dashboard automating BDR prospect qualification and outreach for enterprise B2B](assets/home-screen.png)

## Account Qualification Agent

The Account Qualification Agent (AQA) is the heart of the Sales Qualifier. The AQA uses AI to read your accounts and determine which ones are ready for the next step. It assists with research, email drafting, and CRM updates.

![AI-powered Account Qualification Agent dashboard for sales prospect and account research](assets/acc-qualification-agent.png)

* **Prospect research**

   Conduct prospect research using automatic retrieval and display of key prospect information (such as job title, recent engagements, buying group membership) to provide a complete picture in seconds.

* **Account research**

   Conduct account research using automatic retrieval and display of detailed information about a prospect's organization. This information includes company vitals, recent news, strategic priorities, and top engaged members.

* **Draft emails**

    Generate email drafts by synthesizing research from prospect and account insights to produce relevant, personalized single email content based on the BDR's objective.

* **Engagement plan emails**

    Create engagement plan email drafts that are personalized for each step of a BDR-defined outreach cadence, ensuring the entire sequence is personalized.

### Basic Usage

Adobe AI agents use _natural language queries_, which means that they use the same language in the text prompt as you would when speaking with a person. The more detailed you are, the better the results.

Using natural language, you can ask the agent to:

* `Show me my assigned leads with no engagement yet`
* `Show me all my leads that are not part of any autonomous engagement`
* `Give me a detailed summary on Acme company, including their buying group, recent intent signals, and our past engagement.`

You can immediately understand which accounts and leads are the most active and show the highest intent, so you can focus your energy where it has the most impact.

Iterate over your journey by refining your prompts to get the results you need. For example:

* Draft a follow-up email drawing from context like earnings calls or reports. Up to 120 words. Subject line: Captivating, incorporating a key theme. Intro: Hook with a direct quote from context sources. Body: Connect to pain points and value propositions. CTA: Propose a short call to explore further.

* The goal of this email is to start a conversation and build credibility. Draft an email under 120 words that has a consultative and empathetic tone. Make sure to avoid an overly familiar or sales approach and do not use the phrases "hope you are well," "just checking in," or "please."

## Prospects

This window lists all the leads that you have access to. It's a quick check on things, such as lead status and last activity.

![Leads table displaying lead status and last activity for prospect management](assets/prospects.png)

Click the _Filter_  ![Filter icon](../../assets/do-not-localize/icon_filter-outline.svg) icon to filter the displayed list by lead status.

## Engagement plans

This window provides details about any defined Engagement plans.

![Engagement plan dashboard showing plan details, selected leads, and schedule settings](assets/engagement-plans.png)

To make a new Engagement plan, click **[!UICONTROL Create engagement plan]**.

1. In the _Details_ stage, provide a name and optional description. Click **[!UICONTROL Save and Continue]**.
1. In the _Select prospects_ stage, select the leads that should belong in this plan.
1. In the _Define cadence_ stage, set the parameters for the plan.
1. In the _Preview_ stage, ensure that everything is working as expected.

## Email outbox

The Email outbox panel lists all the automated emails that you have sent.

## Meeting bookings

This panel displays all meetings set up through automation.

## Chat inbox

This panel displays all your chat threads.

![Panel showing chat threads with contact and thread summaries for sales automation](assets/chat-inbox.png)

You can interact with clients, and see summaries for the contact and the thread so that you can quickly know where you are in the thread.

## Integrations

With integrations, the Sales Qualifier can leverage CRMs and other data sources to enrich customer profiles and tap into sales activities:

* Integrate with your email inbox to keep track of relevant incoming emails and help generate replies.
* Read and update CRM data, such as Salesforce or Microsoft&reg; Dynamics, ZoomInfo, or BuiltWith.

![Sales Qualifier integration with Microsoft Outlook showing email and contact summaries](assets/outlook.png)

### Set up a new integration

To start a new integration, click **[!UICONTROL Create integration]** at the top right.

![Integration setup form showing URL, HTTP method, headers, and authentication options](assets/integration-details.png)

Define the URL of the integration and establish the payload to send:

1. Provide a unique name and a description (optional) for the integration.
1. Set the URL field to the integration authentication endpoint of your integration site.
1. In Path Parameters, set the HTTP method.
1. In Header Parameters, set any HTTP headers that need to be send. Generally, it is a JSON object that is sent and requires a content-type header.
1. In Query Parameters, establish any required parameters.
1. Under Authentication, set up login information for the integration site.

    * None
    * OAuth 2.0
    * API key
    * Basic Auth

1. Set throttling and cache values in the **[!UICONTROL Payload configuration]** section.
   * Click the pencil icon.
   * In the _Paste Payload_ dialog, paste or enter your JSON payload object.
   
      * **[!UICONTROL Request payload]**  - A JSON object containing data to send to the integration site.
      * **[!UICONTROL Response payload]** - The data structure you expect to be returned.

1. Click **[!UICONTROL Test Connection]** to ensure that your settings are correct.

When the connection settings are valid, click **[!UICONTROL Save as draft]**.

When you are back on the main _[!UICONTROL Integrations]_ table, select the integration and click **[!UICONTROL Activate]** to make the integration live. If you are not ready to activate it, click **[!UICONTROL Save as draft]**.

#### Manage access

You can manage access to users and the kind of data that is shared with different user groups.

Click **[!UICONTROL Manage access]** to open the _[!UICONTROL Manage Access]_ dialog.

This dialog lists all the Labels that are established for your organization. Select the labels that you want to apply to this integration.

If you need a new label, click **[!UICONTROL Create label]** and enter the label information:

* Name
* Friendly name
* Description

## Representative settings

The representative settings specify information about yourself, including personal details, email and calendar settings, and chat availability.

### Details

The **[!UICONTROL Details]** tab is where you enter information about yourself:

![Details tab showing personal information, email, and chat availability settings for representatives](assets/details.png)

### Email settings

In the **[!UICONTROL Email settings]** tab, set up your email connections.

![Email settings tab showing email connection options and email signature configuration](assets/email-settings.png)

* **[!UICONTROL Email connections]** - Click **[!UICONTROL Connect]** and follow the Microsoft login procedure. 

* **[!UICONTROL Email signature]** - Configure the email signature that is used in auto-generated emails.

### Calendar settings

In the **[!UICONTROL Calendar settings]** tab, set your time zone and availability.

![Calendar settings tab showing time zone and availability options](assets/calendar-settings.png)

* **[!UICONTROL Calendar connection]** - Click **[!UICONTROL Connect]** and follow the Microsoft login procedure to integrate you calendar. 

* **[!UICONTROL Meeting confirmation email]** - When a client confirms a meeting with you, they receive the confirmation email as a reply. Use these settings to define the email subject and body.

* **[!UICONTROL Preferences]** - Set your default meeting length, and the time you would like between back-to-back meetings.

### Chat settings

In the **[!UICONTROL Chat settings]** tab, set your Timezone Live chat availability.

![Chat settings tab for configuring timezone and live chat availability](assets/chat-settings.png)

## Representative management

The _[!UICONTROL Representative management]_ panel displays the defined representatives and their calendar status.

## Meeting performance

This panel presents analytics around your completed meetings.

## Set up the Chrome plugin

The AI Assistant Chrome plugin is available on the [Google Store](https://chromewebstore.google.com/detail/ai-assistant/hancbabllcmckehonngbdkhilocpdfji?authuser=0&hl=en).

When the plugin is installed in Chrome, the Adobe logo appears on the middle right when you are on an integrated site:

* Adobe web applications
* Salesforce
* Outlook
* Microsoft Dynamics and web applications
* Google applications

## Edit the left navigation bar

At the bottom left of the application, click **[!UICONTROL Edit]** to control which of the icons are visible in the navigation. You can also drag and drop them to reorder as you want.

## Demonstration video

The following video provides a short demonstration of the Sales Qualifier and Account Qualification Agent.

>[!VIDEO](https://video.tv.adobe.com/v/3476550)
