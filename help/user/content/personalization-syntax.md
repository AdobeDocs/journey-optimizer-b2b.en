---
title: Personalization syntax
description: Learn Handlebars-based personalization syntax in Journey Optimizer B2B Edition, including expressions, helpers, literal types, and formatting rules.
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: expression, editor, syntax, personalization
---
# Personalization syntax {#personalization-syntax}

Expressions in the [!DNL Journey Optimizer B2B Edition] [personalization editor](./personalization.md#personalization-editor) are based on the _Handlebars_ templating syntax. It uses a template and an input object to generate HTML or other text formats. Handlebars templates look like regular text with embedded Handlebars expressions.

For more details about the Handlebars and how it works, refer to the [HandlebarsJS documentation](https://handlebarsjs.com/){target="_blank"}.

## General rules

Simple expression example: 

```
{{account.accountName}}
```

Where:

* `account` is a namespace.
* `accountName` is a token composed by attributes. 

   >[!NOTE]
   >
   >The attributes structure is defined in an [Adobe Experience Platform XDM Schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home){target="_blank"}.

* Identifiers can be any Unicode character except for the following: 

    ```
    Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
    ```

* The syntax is case sensitive.

* The words **true**, **false**, **null** and **undefined** are only allowed in the first part of a path expression.

* In Handlebars, the values returned by the {\{expression}\} are _HTML-escaped_. If the expression contains `&`, the returned HTML-escaped output is generated as `&amp;`. If you do not want Handlebars to escape a value, use the +triple-stash_. 

<!-- For example:

    If the value of the field `profile.person.name` is _Mark & Mary_, the `{\{profile.person.name}\}` value generates as `Mark &amp; Mary` and `{\{\{profile.person.name}}}` renders as `Mark & Mary`. -->

* For literal functions arguments, the templating language parser does not support single unescaped backslash (`\`) symbol. This character must be escaped with an additional backslash (`\`) symbol. For example :

   ```
   {%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}
   ``` 

## Helpers {#helpers-all}

A Handlebars helper function is a simple identifier that can be appended with parameters. Each parameter is a Handlebars expression. These helpers can be accessed from any context in an email template.

```sql

{{#each account.accountOrganization.annualRevenue.amount}}
    <li>{{this.name}}</li>
{{/each }}

```

<!-- These block helpers are identified with a `#` preceding the helper name and require a matching closing `/`, of the same name. 

Blocks are expressions that have a block opening ( {\{# }\} ) and closing ( {\{/} } ). -->

For more detailed information about these functions, see [Helper functions](./personalization-helper-functions.md).

## Literal types {#literal-types}

[!DNL Adobe Journey Optimizer B2B Edition] supports the following literal types:

| Literal | Definition |
| ------- | ---------- |
| String | A data type comprised of characters surrounded by double quotes. <br>Examples: `"prospect"`, `"jobs"`, `"articles"` |
| Boolean | A data type that is either true or false.|
| Integer | A data type representing a whole number. It can be positive, negative, or zero. <br>Examples: `-201`, `0`, `412` |
| Array | A data type that is comprised as a group of other literal values. It uses square brackets to group and commas to delimit between different values. <br> **Note:** You cannot directly access the properties of items within an array. <br> Examples: `[1, 4, 7]`, `["US", "FR"]` |  

>[!CAUTION]
>
>The use of **xEvent** variable is not available in personalization expressions. Any reference to xEvent results in validation failures.
