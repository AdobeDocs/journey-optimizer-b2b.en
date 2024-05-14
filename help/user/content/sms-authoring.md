---
title: SMS authoring
description: Learn about...
feature: SMS Authoring, Content
---

# SMS authoring

Use Adobe Journey Optimizer B2B edition to send text messages (SMS) to your customers on their mobile devices. You can create, personalize, and preview messages in text format from the SMS editor.

You can set up text message deliveries in an Account Journey when you add a new _[!UICONTROL Take an action]_ node and do the following:

1. For the _[!UICONTROL Action on]_ target, choose **[!UICONTROL People]**.

1. For the _[!UICONTROL Action on people]_, choose **[!UICONTROL Send SMS]**.

   ![Take an action - send sms](assets/journey-node-send-sms.png){width="800" zoomable="yes"}

1. At the bottom of the _[!UICONTROL Take an action]_ panel, click **[!UICONTROL Create SMS]**.

1. In the _[!UICONTROL Create new email]_ dialog, enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

   ![Create new SMS dialog](assets/create-new-sms.png){width="500"}



Adobe Journey Optimizer sends text messages through SMS service providers (or SMS gateway providers). Before creating your SMS message, configure your service provider from the Administration section.

SMS Gateway Service Provider Configuration
Adobe Journey Optimizer B2B Edition currently integrates with third-party providers who offer text messaging services independently. Supported providers for text messaging are: Sinch, Twilio and Infobip. 

Prior to SMS channel configuration in Adobe Journey Optimizer B2B edition, you must create an account with one of these providers to get your API Token and Service ID, which you need to configure the connection between Adobe Journey Optimizer B2B edition and the applicable provider.

Your use of text messaging services is subject to additional terms and conditions from the applicable provider. As third-party solutions, Sinch, Twilio and Infobip are available to Adobe Journey Optimizer B2B edition users via an integration. Adobe does not control, and is not responsible for third-party products. For any issues or requests for assistance related to the text messaging services (SMS), contact your provider.

List and manage API Configurations
Note that this section is accessible only to the users with SMS Admin privilege.

Navigate to Administration > Channels > API Configuration to view a listing of all available API Configurations in the instance


From this listing page you can -
Search for an API credential
Filter API credentials by 'SMS Service Provider'
Sort API credentials by a column
Create new API Credential
Create new API credentials
Sinch
To configure your SMS provider with Adobe Journey Optimizer B2B Edition, follow these steps:

In the left rail, browse to Administration > Channels and select the API Credentials menu. Click the Create new API credentials button.

Configure your SMS API credentials, as detailed below:

Name: Choose a name for your API Credential

Service ID and API Token: Access the APIs page from your SMS service provider, you can find your credentials under the SMS tab

Click Submit once you done adding the configuration details of your API credentials



Twilio
To configure Twilio with Journey Optimizer, follow these steps:

In the left rail, browse to Administration > Channels and select the API Credentials menu. Click the Create new API credentials button.

Configure your SMS API credentials, as detailed below:

Name: Choose a name for your API Credential

Account SID and Auth Token: Access the Account Info pane of your Twilio Console Dashboard page to find your credentials

Message SID: Enter the unique identifier assigned to every message created by Twilio's API

Click Submit  once you done adding the configuration details of your API credentials



Infobip
To configure Infobip with Journey Optimizer, follow these steps:

In the left rail, browse to Administration > Channels and select the API Credentials menu. Click the Create new API credentials button.

Configure your SMS API credentials, as detailed below.

Name: Choose a name for your API Credential

API base URL and API key: Access your web interface homepage or the API key management page to find your credentials

Click Submit  once you done adding the configuration details of your API credentials



In each of the above cases, once you click 'Submit', the credentials are immediately validated & saved, redirecting you to the API Credentials listing page. In case the credentials are invalid, you will receive an error message on the same screen. And you can choose to cancel the configuration or update and save.

SMS Authoring
Create text message
After adding SMS node to Account journeys
Provide basic information on your message (label, description)
Label - 
Character limit = 100

Description - max 300 characters

Alpha, numeric, special characters allowed

Reserved characters not allowed: \ / : * ? " < > |

 

Description -
Character limit = 100

Description - max 300 characters

Alpha, numeric, special characters allowed

Reserved characters not allowed: \ / : * ? " < > |

Users can create SMS messages of up to 1600 characters and every 160 characters will be considered as a single SMS message


Personalize text message
At anytime while authoring the text message, click on the 'personalize' icon to the right side of the text message box


This opens up a modal, listing Adobe Marketo Engage Lead & System tokens


You can either use the Search bar or navigate through the Folder Tree to access any of the lead/ system tokens
Both standard and custom tokens will be listed here

You can either directly add a token by clicking on the '+' sign next to it, or add the token with a fallback (default that will appear in case that field is not available for a lead) by clicking on the ellipsis


You can click on Save to save changes & return to the SMS authoring screen
Add URLs to text message
After defining your content, you can add URLs to your message by clicking on the link icon, which opens a modal
You can add 2 types of URLs
External URLs
This is ANY external URL that can be directly typed into/ pasted into the input text box
Adobe Marketo Engage Design Studio Landing Pages
Selecting this option, you will see a 'Landing Page picker' from which you can select any of the listed approved Landing Pages from Marketo Engage
You can choose to 'shorten' either of these URLs by selecting the checkbox
Note that the URL shortening function, uses the Marketo subdomain for shortening
The shortened URL appears as a read-only field within the modal
You can optionally track clicks on the URL
You can also choose to include 'mkt_tok' for tracking activity against a user
Click on Add to save changes & add the chosen URL to the SMS message
Define SMS properties
Post defining the message, you can
Select one of the pre-defined API configurations - to determine which SMS gateway service provider needs to be used to deliver the message
Add sender number/ alphanumeric name
The recipient number will always be mapped to the Lead.MainPhone field in Marketo


Simulate text message content
You can also simulate content for specific leads by clicking on 'Simulate Content' & adding a test profile. And the preview updated to the personalization fields for the selected profile.

Steps to Simulate SMS

Add/ manage test profiles

Click on the 'Simulate Content' button on the SMS authoring page


From the Simulate Content page, click on 'Add People' button
This opens a modal from where you can 'search' for and add (up to 10 leads at a time) any of the leads from the Marketo Engage lead database


You have to search by typing the whole email address & clicking enter - the corresponding lead profile shows up for selection
All the leads thus added appear on the left rail of the 'Simulate Content' page
You can manage this list by adding more people/ deleting individual leads from the listing (only)
Simulate content for a selected lead

Select any of the leads listed on the left rail of the Simulate Content page and the SMS preview on the page updates for the corresponding lead
You can also select a lead from the 'drop-down' box above the preview space and the SMS preview on the page updates for the corresponding lead


You can click on 'Close' to exit Simulate Content & return back to the SMS authoring screen
SMS Consent Management
In accordance with the industry standards and regulations, all SMS marketing messages must contain a way for the recipients to easily unsubscribe. To do this, SMS recipients can reply with opt-in and opt-out keywords. All standard opt-in and opt-out keywords will be supported & honored. In addition, any custom keywords configured at the 'SMS service provider' will also be supported and honored.



LikeBe the first to like this
No labelsEdit Labels
User icon: tilling
Write a comment...