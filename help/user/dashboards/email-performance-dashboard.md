---
title: Email Performance Report
description: Use the Email performance report in Journey Optimizer B2B Edition to monitor email send, delivery, engagement, and opt-out metrics across all journeys in one unified view.
feature: Dashboards, Reporting
role: User
autotag-review: '2026-05-21T15:04:51.176Z'
TQID: 'https://experienceleague.adobe.com/hA63o9-2-atw0kRNFeEu6H449WmZ59CjL3uiVS7nEcA'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Email performance report

The **Email performance** report gives marketers a unified view of email activity across all journeys in Adobe Journey Optimizer B2B Edition. It aggregates send, delivery, engagement, and opt-out metrics. By surfacing both raw counts and calculated rates, you can monitor campaign health, compare email performance, and identify deliverability or engagement issues at a glance. For journey-level metrics across email and SMS channels, see the [Account Journeys dashboard](./journeys-dashboard.md).

## Access the report

1. In the left navigation, select **[!UICONTROL Dashboard]**.
1. Select the **[!UICONTROL Email performance]** tab at the top of the reporting dashboard.

![Email performance report](./assets/email-performance-dashboard.png){width="800" zoomable="yes"}

## Filter the data

Click the _Filter_ ( ![Filter icon](../assets/do-not-localize/icon-filter.svg) ) icon at the top left to filter the data display using the two supported filter types. These filters apply to all panels simultaneously:

* **[!UICONTROL Journey]** - Filters the report to show data for one or more selected journeys. Use this filter to isolate performance for the journeys that matter for your campaign or program.

* **Date range** - Restricts all metrics to emails sent within the specified time window. Supports preset ranges and a custom date picker. The date range selector is in the top-right corner of the dashboard.

![Journey and date range filters in the filters dialog](./assets/email-performance-filters.png){width="500"}

When you change filters in the filters dialog, click **[!UICONTROL Apply]**.

## Count and rate metric charts

The top section of the Email performance report contains two side-by-side bar charts that provide a visual summary of overall email program health across the selected date range and journey.

**Count metrics** — Displays the absolute volume of email activity. Each bar represents the total count of a key email event across all emails in the filtered scope: Sent, Delivered, Opened, Clicked, Bounced, and Unsubscribes.

**Rate metrics** — Displays calculated percentage rates, enabling you to assess engagement and deliverability quality independently of volume: Deliver rate, Open rate, Click rate, Bounce rate, Click-to-open rate, and Unsubscribe rate.

Hover over the chart to display numeric data.

![Hover over the bar chart - displayed count](./assets/email-performance-counts-hover.png){width="500"}

| Metric | Type | Description |
|--------|------|-------------|
| Sent | Count | Total number of email messages submitted for delivery. |
| Delivered | Count | Emails successfully accepted by the recipient's mail server. |
| Opened | Count | Number of delivered emails that were opened at least once. |
| Clicked | Count | Number of emails that received at least one link click. |
| Bounced | Count | Emails that could not be delivered (hard or soft bounce). |
| Unsubscribes | Count | Recipients who opted out via an unsubscribe link in the email. |
| Deliver rate | Rate | Delivered ÷ Sent. Indicates the percentage of emails that reached inboxes. |
| Open rate | Rate | Opened ÷ Delivered. Measures recipient engagement with subject lines. |
| Click rate | Rate | Clicked ÷ Delivered. Measures overall click engagement per delivered email. |
| Bounce rate | Rate | Bounced ÷ Sent. Highlights deliverability and list health issues. |
| Click-to-open rate (CTOR) | Rate | Clicked ÷ Opened. Measures content and CTA effectiveness among engaged readers. |
| Unsubscribe rate | Rate | Unsubscribes ÷ Delivered. Signals relevance and audience fit. |

## Email performance table

At the bottom of the page, a detailed table shows per-email metrics for every email asset in the filtered scope. By default, the table displays 10 rows per page.

The **Unsubscribe %** column is a prioritized metric for monitoring opt-out activity directly in the table view.

| Column | Description |
|--------|-------------|
| Email Name | The name of the [email asset](../content/add-email.md) as configured in the journey. |
| Sent | Total sends for this email within the selected date range. |
| Delivered | Number of emails successfully delivered to recipient mail servers. |
| Delivery % | Delivered ÷ Sent, expressed as a percentage. |
| Opens | Total number of open events recorded for this email. |
| Open % | Opens ÷ Delivered, expressed as a percentage. |
| Clicks | Total link click events for this email. |
| Click % | Clicks ÷ Delivered, expressed as a percentage. |
| CTOR % | Click-to-open rate: Clicks ÷ Opens, expressed as a percentage. |
| Bounces | Number of undeliverable emails (hard + soft bounces). |
| Bounce % | Bounces ÷ Sent, expressed as a percentage. |
| Unsubscribe % | Unsubscribes ÷ Delivered. Prioritized metric for monitoring opt-out health. |
| First Activity | Timestamp of the first recorded event (send, open, or click) for this email in the selected period. |
| Last Activity | Timestamp of the most recent recorded event for this email in the selected period. |

## Export report data

The Email performance report supports data export for further analysis in external tools or for sharing results with stakeholders. You can export the table data in CSV format, which is compatible with any data analysis or BI tool.

>[!CAUTION]
>
>Exports reflect the currently active filters. Ensure that your date range and journey filters are set correctly before exporting to avoid incomplete data in the output file.

**_To export report data:_**

1. Set your date range at the top right and apply **[!UICONTROL Journey]** filtering as needed.
1. Click the **...** menu icon in the top-right corner of the Email performance panel and choose **[!UICONTROL View more]**.
1. Click **[!UICONTROL Download CSV]** from the menu.

   ![View detailed data and download CSV](./assets/email-performance-data-export.png){width="700" zoomable="yes"}

   The file downloads automatically to your browser's default download location.

1. Click **[!UICONTROL Close]** to return to the Email performance report.
