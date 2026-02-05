---
title: Content personalization
description: Personalize B2B emails using account, person, and system tokens in Journey Optimizer B2B Edition. Learn to use the personalization editor and syntax.
feature: Personalization, Content Design Tools, Email Authoring
topic: Personalization
role: User, Developer
level: Intermediate
keywords: expression, editor, start, personalization
exl-id: 60bf2e06-8d6e-4cc4-8aff-5c5ca11f05ab
---
# Content personalization {#add-personalization}

>[!CONTEXTUALHELP]
>id="aj-b2b_personalization"
>title="Personalize content experiences"
>abstract="Use **Adobe Journey Optimizer B2B Edition** to adapt your messages to each specific recipient by leveraging the data and information you have about them. It can be their first name, industry, title, and more."

[!DNL Adobe Journey Optimizer B2B Edition] personalization capabilities allow you to adapt your email messages to each specific recipient by leveraging the data and information you have about them. It can be their first name, industry, title, and more.

Using the _personalization editor_, you can select, arrange, customize and validate all the data to create a customized personalization for your content. Use various tools, such as helper functions, to tailor messages. The editor uses an inline personalization syntax based on _Handlebars_, where expressions are constructed with contents enclosed by double curly braces `{{}}`.

When processing the message, Journey Optimizer B2B Edition replaces the expression with the data contained in the Adobe Experience Platform dataset and local system values. For example, `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` dynamically becomes `Hello John Doe`.

Using this syntax, you can personalize messages across multiple fields, including email subject lines, message bodies, and sender information. 

## Personalization tokens

In [!DNL Journey Optimizer B2B Edition], you can build your dynamic email content using personalization tokens:

* **Account tokens** - These tokens are based on the account attributes, such as _account name_, _industry_, and _number of employees_. Use these tokens to populate attribute data managed by the **_XDM Business Account Details_** schema, which is defined in Adobe Experience Platform.

* **Person tokens** - These tokens are based on the business person attributes, such as _first name_, _job title_, and _company name_. Use these tokens to populate attribute data managed by the **_XDM Business Person Details_** schema, which is defined in Adobe Experience Platform.

* **System tokens** - These tokens are based on the system field values, such as _date_, _time_, and _unsubscribe link_.

* **My tokens** (when defined for the journey) - The [custom tokens defined for the journey](./personalization-my-tokens.md) where the email resides. 

>[!NOTE]
>
>Learn more about the XDM schemas in the [Adobe Experience Platform Data Model (XDM) documentation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home){target="_blank"}.

## Personalization editor

The personalization editor is available in every context where you need to define personalization in email content. In the editor, you can select, arrange, customize, and validate all the data to create a customized personalization for your content.

Add personalization in any field or content component by clicking the _Add personalization_ ( ![Add personalization icon](../../assets/do-not-localize/icon-personalization-field.svg) ) icon. 

![Personalization editor](./assets/personalization-editor.png){width="800" zoomable="yes"}

>[!NOTE]
>
>The following information about the personalization editor reflects the changes that are available for [!DNL Journey Optimizer B2B Edition] environments provisioned on the [simplified architecture](../simplified-architecture.md).

### Tokens and helper functions

To use a personalization token or helper function, locate it in the left navigation pane and click **+** to add it to the expression.

Click the _More menu_ ( **...** ) icon (next to the _Add_ ( **+** ) icon) to view more details for each attribute and to add your most frequently used attributes to the _favorites_. Attributes added to favorites are accessible from the **[!UICONTROL Favorites]** menu in the left navigation of the editor.

![Personalization editor - token More menu](./assets/personalization-editor-token-more-menu.png){width="800" zoomable="yes"}

<!-- >>[!NOTE]
>
>By default, the attributes list shows only populated attributes. To display all attributes, click the _Settings_ icon above the search field and toggle off the **[!UICONTROL Show only populated attributes]** option.
-->
You can also define a default fallback text string that is displayed if a string-type profile attribute is empty. Click the _More menu_ ( **...** ) icon for the attribute and select **[!UICONTROL Insert with fallback text]**. Enter the text that should be displayed when the attribute's value is empty for a profile, and then click **[!UICONTROL Add]**.

It is a best practice to validate the expression before you insert it into the content. Click **[!UICONTROL Validate]** at the bottom of the editor to check your syntax and ensure that there are no errors.

![Personalization editor validated code](./assets/personalization-editor-validated.png){width="500"}

When the expression is complete and free of errors, click **[!UICONTROL Save]**.

### Custom datasets

You can use relational schemas (model-based classes) for email personalization. The custom objects are defined within _relational schemas_, and a product administrator can [configure relational schema fields](../admin/xdm-field-management.md#relational-schemas) in [!DNL Journey Optimizer B2B Edition]. These fields are accessible in the personalization editor. Only custom objects that have a one-to-many (1:M) relationship to Account <!-- (M1.5 Beta) or Person (M1.5 GA) --> are available.

>[!IMPORTANT]
>
>Before you use custom objects for scripted personalization, make sure that you review and understand the [Handlebar templating language](https://handlebarsjs.com/guide/), [personalization syntax](./personalization-syntax.md), and the built-in [helper functions](./personalization-helper-functions.md).

When you define personalization using the custom objects, you can access to all variables in script-accessible objects across the **[!UICONTROL Personalization tokens]** (person/lead, account, system, and My Tokens) and the **[!UICONTROL Model-based classes]** (relational schemas). With Model-based classes selected, you can view the fields by clicking the custom object folder. Click **+** for each field that you want to add it to the expression.

![Personalization editor - Model-based classes - add custom object fields](./assets/personalization-editor-custom-object-fields.png){width="800" zoomable="yes"}

<!-- ## Personalization experimentation {#playground}

**[!DNL Adobe Journey Optimizer]** includes an interactive tool designed to help you learn and experiment with personalization capabilities.

This playground provides a simulated environment to write and test personalization code using sample data without requiring live datasets. You can leverage predefined code samples, edit dummy profile payloads, and preview the output of your personalization code in real-time. 

![personalization playground](assets/playground.png)

➡️ [Access the personalization playground](https://experienceleague.adobe.com/en/apps/journey-optimizer/ajo-personalization){target="_blank"} 

## How-to videos{#video-perso}

Learn how to use contextual event information from a journey to personalize a message.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Learn how to add profile-based personalization to a message and how to use audience membership as a pre-condition to a personalization block.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

Learn how to leverage the personalization editor playground to write and test personalization code using sample data.

>[!VIDEO](https://video.tv.adobe.com/v/3457868?quality=12) -->
