---
title: Generative AI Models
description: Create and manage generative AI image models that marketers can select for generating images for email and landing page content.
topic: Generative AI, Brand Identity, Content
role: User
level: Beginner, Intermediate
---
# Generative AI models for brand alignment

Expand your AI image creation capabilities with built-in models, custom Firefly models, and third-party image generation providers to meet your specific needs and improve brand alignment:

- **[!UICONTROL Adobe model]**, powered by Firefly Image Model 4, is provided out of the box and ready to use for immediate image generation without additional setup.
- **[!UICONTROL Partner model]**, powered by Gemini 2.5 Flash, offers specialized capabilities for specific use cases.
- **[!UICONTROL Custom models]** are brand-specific models trained on your own assets and added by your organization.

Learn about custom models in the [Adobe Firefly documentation](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/custom-models-overview.html){target="_blank"}.

Marketers can select any of the enabled generative models when generating images for their email or landing page content.

## Manage generative models

From a central location, you can view all available models, filter and search to find specific models, and configure model settings for your brands.

1. On the left navigation, go to **[!UICONTROL Content Management]** > **[!UICONTROL Brands]**.

1. In the page, select the **[!UICONTROL Generative models]** tab.

![Access the generative models list](./assets/brands-gen-models-list.png){width="800" zoomable="yes"}

### Filter and search the list

Click the _Filter_ ![Filter icon](../../assets/do-not-localize/icon-react-filter.svg) icon to access the filter menu. Filter models by **[!UICONTROL Type]** or **[!UICONTROL Status]**.

![Filter the generative models list](./assets/brands-gen-models-filter.png){width="700" zoomable="yes"}

You can also use the search bar to find a specific generative model by name.

### Model actions

For a custom model in the list, click the _More menu_ ![More menu icon](../../assets/do-not-localize/icon-more-menu.svg) icon. You can choose **[!UICONTROL Enable]** or **[!UICONTROL Disable]** to change the availability status of the model, or choose **[!UICONTROL Delete]** to remove the model from the list.

![More menu in the generative models list](./assets/brands-gen-models-more-menu.png){width="450"}

For a built-in model, click the _Enable_ ( ![Enable icon](../../assets/do-not-localize/icon-enable.svg) ) or _Disable_ ( ![Disable icon](../../assets/do-not-localize/icon-disable.svg) ) icon to change the model availability for image generation.

>[!NOTE]
>
>Only custom models can be deleted.

## Add a generative model

Create custom Firefly models or connect third-party image generation providers to expand your generative AI capabilities.

>[!NOTE]
>
>Creating custom Firefly models requires a Firefly ETLA agreement. 

1. From the _[!UICONTROL Generative models]_ tab, click **[!UICONTROL Add model]**.

1. Enter a **[!UICONTROL Name]** for your model.

<!-- 1. Select a **[!UICONTROL Model provider]**. future development -->

1. Enter the **[!UICONTROL Model ID]**.

    To find your model ID, access the Firefly website and navigate to your trained models. The unique identifier is available in the model's management section after it is published. For more information, refer to the [Firefly custom models documentation](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/custom-models-overview.html){target="_blank"}. 

1. Optionally, enter a **[!UICONTROL Description]** to help identify the model and its intended usage.

    ![Add Model - generative models](./assets/brands-gen-models-add-model.png){width="550" zoomable="yes"}

1. Click **[!UICONTROL Test connection]** to verify the model configuration.

1. When the connection test is successful, click **[!UICONTROL Save]** to save your model configuration.

   Saving the model adds it to the generative models list, where you can enable it for use by marketers. You can also disable or delete it at any time.

   ![Selecting a generative model for image generation](./assets/gen-ai-model-selection.png){width="600" zoomable="yes"}
