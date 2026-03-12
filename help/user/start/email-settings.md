---
title: Email Settings
description: Placeholder
feature: Setup, Channels
role: Admin
---
# Email settings

Add sections for the following:

| | **Email parameters and filtering** for the attached Marketo Engage instance | |
| | <li>Configure _From_ email | <!-- [Learn more](TBD) --> |
| | <li>Configure _From_ label | <!-- [Learn more](TBD) --> |
| | <li>Configure _Unsubscribe HTML_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Unsubscribe Text_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _View as Web Page HTML_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _View as Web Page Text_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Custom Object Retrieval Limits_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Custom Header Options_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Text Editor Settings_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Email Editor Settings_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Email CC Settings_ | <!-- [Learn more](TBD) --> |
| | <li>Configure _Bot Activty_ | done |


## Filter email bot activity {#filter-email-bots}

Email bot activity, also referred to as non-human interactions (NHI), can inflate your email _opens_ and _clicks_ data, distorting your engagement metrics and triggering event-based journey progression. Use email bot filtering to maintain the integrity of click engagement metrics and insights. There are two methods for identifying suspected bot activity:

* _**[!UICONTROL Match with IAB Bot list]**_ - Activities that match with anything on the [Interactive Advertising Bureau bot list](https://www.iab.com/guidelines/iab-abc-international-spiders-bots-list/){target="_blank"} (User Agent/IP address) are marked as bots.
* _**[!UICONTROL Match with Proximity Pattern]**_ - Two or more activities that happen at the same time (in under a second) are identified as bots. Attributes considered during comparison are:
  * Lead ID (should be the same)
  * Email asset (should be the same)
  * Link click or email open

For email link click and email open activity, attributes are populated with the following values:

* Activities that are identified as bots -  _Bot Activity_ = `true` and _Bot Activity Pattern_ = identified pattern/method
* Activities that are identified as not bots - _Bot Activity_ = `false` and _Bot Activity Pattern_ = `n/a`

### Set the filters

1. Go to the **[!UICONTROL Admin]** area in the attached Marketo Engage instance and select **[!UICONTROL Email]**.

1. Select the **[!UICONTROL Bot Activity]** tab.

   ![](./assets/me-admin-email-bot-activity.png){width="700" zoomable="yes"}

   The Bot Activity Identification panel displays two sliders that you can use to identify bot activity.
   
1. Toggle the slider to enable one or both.

   For each method that you enable, choose _[!UICONTROL Log Bot Activity]_ or _[!UICONTROL Filter Bot Activity]_.

   >[!IMPORTANT]
   >
   >If you choose [!UICONTROL Filter Bot Activity], you may see a drop in email opens and clicks because false activities are eliminated.

   ![](./assets/me-admin-email-bot-activity-set-filters.png){width="500"}

   For  _[!UICONTROL Match with Proximity Pattern]_, you can also set the amount of seconds for **[!UICONTROL Duration Between Activities]** (default is `0`, maximum is `3`).

   >[!NOTE]
   >
   >With _Duration Between Activities_ set to `0` seconds, Marketo Engage identifies email activities that are happening at the exact same second. If multiple email activities happen within the designated amount of seconds, it is identified as bot activity.

   To disable either filtering method, toggle the slider to the left. If you do, the data does not reset.

### IP Blocklist

Adobe has identified a list of IP addresses that are responsible for generating millions of fake engagements, as such engagement received from any of the following IPs is automatically filtered out and not added to your Marketo Engage instance. This filtering may result in a reduction in email opens, clicks, and other related activities. This list may be updated periodically.

+++ Blocked IP addresses

* 40.94.34.52
* 40.94.34.86
* 52.34.76.65
* 54.70.53.60
* 54.71.187.124
* 60.28.2.248
* 64.235.150.252
* 64.235.153.10
* 64.235.153.2
* 64.235.154.105
* 64.235.154.109
* 64.235.154.140
* 64.74.215.1
* 64.74.215.100
* 64.74.215.138
* 64.74.215.139
* 64.74.215.142
* 64.74.215.146
* 64.74.215.150
* 64.74.215.154
* 64.74.215.158
* 64.74.215.162
* 64.74.215.164
* 64.74.215.166
* 64.74.215.170
* 64.74.215.174
* 64.74.215.176
* 64.74.215.178
* 64.74.215.51
* 64.74.215.56
* 64.74.215.58
* 64.74.215.59
* 64.74.215.86
* 64.74.215.98
* 65.154.226.101
* 66.249.91.149
* 70.42.131.106
* 74.125.217.116
* 74.217.90.250
* 104.129.41.4
* 104.47.55.126
* 104.47.58.126
* 104.47.70.126
* 104.47.73.126
* 104.47.73.254
* 104.47.74.126
* 128.220.160.1
* 155.70.39.101
* 162.129.251.14
* 162.129.251.42
* 208.52.157.204

>[!NOTE]
>
>Every IP address is meticulously analyzed and scrutinized before it is included in this list, ensuring only the most critical and harmful IPs are blocked.

+++
