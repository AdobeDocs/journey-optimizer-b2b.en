---
title: Author from a Governed Template
description: Learn how to use email authoring with a governed template that contains locked content components.
feature: Email Authoring, Content
exl-id: 1af996a6-a010-4899-96e9-bad76f93865c
---
# Author from a governed template

Content designers can enable [governance (_content locking_)](./template-content-governance.md) when creating email templates. Governance features allow them to designate the parts of the design that cannot be changed when used in an account journey. When you [select a saved template](./email-authoring.md#select-a-template) to author an email, the visual designer loads the template so that you can use it as a basis for your email. 

If the template has governance enabled, an alert is displayed in the properties panel on the right. You can turn on the **[!UICONTROL Highlight editable areas]** at the top of the canvas to see which components and content elements are editable for use in your journey.

![View editable areas in a governed template](./assets/email-designer-governed-highlight.png){width="800" zoomable="yes"}

You can also determine the elements that are locked or editable using the _Navigation tree_. Click the _Navigation tree_ icon ( ![Link icon](../assets/do-not-localize/icon-navigation-tree.svg) ) to the left of the canvas to display the tree. 

![View editable areas in a governed template](./assets/email-designer-governed-tree.png){width="600" zoomable="yes"}

The icons indicate the applied content locking settings.

| Icon | Name | Description |
|------|------|-------------|
| ![Read only icon](../assets/do-not-localize/icon-tree-lock.svg) | Read only| The component is locked and cannot be edited. When applied at the root (_[!UICONTROL Body]_) level, all child components are locked and cannot be edited. |
| ![Content edit icon](../assets/do-not-localize/icon-tree-content-lock.svg) | Content lock | Content locking is applied at the component level. |
| ![Editable icon](../assets/do-not-localize/icon-edit.svg) | Editable | The component is fully editable. However, you may not be able to delete the element. |
| ![Content edit icon](../assets/do-not-localize/icon-tree-edit-text.svg) | Editable - content only | The component and styling is static, but you can change the content (such as text or image). |
