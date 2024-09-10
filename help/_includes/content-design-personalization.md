---
title: Content authoring - personalization
description: Reused section about using personalization for content authoring
---
# Content authoring - personalization

Journey Optimizer B2B Edition uses an inline simple personalization syntax that allows you to create expressions with contents enclosed by double curly braces `{}`. You can add multiple expressions in the same content or field without restrictions.

Examples:

* {% raw %}Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}{% endraw %}
* {% raw %}Hello {{profile.person.name.fullName}}{% endraw %}

When processing the message (email and SMA), Journey Optimizer B2B Edition replaces the expression with the data contained in the Experience Platform database. So, {% raw %}Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}{% endraw %} becomes _Hello John Doe_.

The following example outlines steps to personalize content using lead/account attributes and system tokens.

1. Select the text component and click the _Add personalization_ icon in the toolbar.

   ![Click the Personalize icon](../assets/content-design-shared/visual-designer-personalize-icon.png){width="500"}

   This action opens the _[!UICONTROL Edit Personalization]_ dialog.

1. Click **+** or **...** to add a token to the blank space.

   ![Construct personalized text using tokens](../assets/content-design-shared/visual-designer-personalize-dialog.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Save]**.
