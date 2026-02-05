---
title: Single-Page Applications
description: Create web experiences for single-page applications (SPAs) - configure view tracking, handle dynamic content, and manage client-side navigation in Journey Optimizer B2B Edition.
feature: Channels, Personalization
role: User
badgeBeta: label="Beta" type="informative" tooltip="This feature is currently in a limited beta release"
exl-id: 7691006d-3d22-4db4-94d3-cfd420128b86
---
# Single-page applications

Single-page applications (SPAs) present unique challenges for web personalization because they dynamically update page content without full page reloads. Journey Optimizer B2B Edition provides specialized tools to handle SPA personalization effectively.

## Understanding SPAs

Unlike traditional multi-page websites where each navigation triggers a full page load, SPAs use JavaScript to update content dynamically while maintaining a single HTML page. This approach creates several considerations for web experiences:

* **No page reloads** - Content changes occur without triggering traditional page load events.
* **Virtual views** - Different _views_ or _screens_ within the SPA that need to be tracked as separate pages.
* **Client-side routing** - JavaScript routers (such as React Router, Vue Router, and Angular Router) handle navigation rather than server requests.
* **Dynamic DOM** - Page elements may be created, modified, or removed after initial page load.

## Configure SPA support

To personalize SPAs effectively, you need to configure view tracking so that Journey Optimizer B2B Edition can identify when users navigate between virtual views.

### Set up view declarations

Work with your development team to implement view declarations using the Adobe Web SDK. Using these view declarations involve calling the `sendEvent` command with view information whenever the SPA navigates to a new view.

**Example implementation:**

```javascript
// When a new view is rendered in your SPA
alloy("sendEvent", {
  "xdm": {
    "web": {
      "webPageDetails": {
        "viewName": "product-detail",
        "URL": window.location.href
      }
    }
  },
  "data": {
    "__adobe": {
      "target": {
        "viewName": "product-detail"
      }
    }
  }
});
```

### View naming conventions

Use consistent, descriptive view names that match your application's logical structure:

| View | Example name |
| ---- | ------------ |
| Home page | `home` |
| Product listing | `product-list` |
| Product details | `product-detail` |
| Shopping cart | `cart` |
| Checkout | `checkout` |
| Account dashboard | `account-dashboard` |

>[!NOTE]
>
>View names are case-sensitive. Use a consistent naming convention (lowercase with hyphens is recommended) in your implementation.

## Create web experiences for SPAs

When creating web experiences for SPAs, consider the following best practices:

### Target specific views

* In the [web channel configuration](../admin/configure-channels-web.md), set up URL matching rules that align with your SPA routing structure.

* When creating modifications, specify the view where the modification should apply.

* Use CSS selectors that target elements specific to each view.

### Handle dynamic content

SPAs often load content dynamically after the initial page render. Use these techniques to ensure that modifications apply correctly:

#### Wait for elements

Configure modifications to wait for the target elements to exist before applying:

1. In the non-visual editor, add a modification with a CSS selector.

1. Enable **[!UICONTROL Wait for element]** and specify the maximum wait time.

1. The modification applies once the target element appears in the DOM.

#### Use mutation observers

For highly dynamic content, the Web SDK includes built-in mutation observers that detect when new elements are added to the page. These observers ensure that modifications are applied even when elements load asynchronously.

### SPA frameworks

Journey Optimizer B2B Edition web experiences work with popular SPA frameworks:

| Framework | Considerations |
| --------- | -------------- |
| **React** | Modifications apply after React renders components to the DOM. Use class names or data attributes for targeting. |
| **Angular** | Target elements after Angular's change detection runs. Avoid targeting elements with `*ngIf` before they render. |
| **Vue.js** | Wait for Vue's `nextTick` to ensure that elements are in the DOM. Use references or custom attributes for stable targeting. |
| **Next.js / Nuxt.js** | For SSR/SSG pages, ensure that the Web SDK hydration is completed before expecting modifications. |

## Best practices for SPA personalization

### Use stable selectors

SPAs often generate dynamic class names or IDs (especially with CSS-in-JS solutions). As an alternative, you can use:

* **Data attributes** - Add custom data attributes (`data-testid`, `data-section`, etc.) to elements you want to target.
* **Semantic HTML** - Target based on HTML structure and semantic elements.
* **ID attributes** - Use stable ID attributes where possible.

**Example:**

```html
<!-- Instead of targeting dynamic class names -->
<button class="css-1a2b3c4d">Sign Up</button>

<!-- Add a stable data attribute -->
<button class="css-1a2b3c4d" data-action="signup">Sign Up</button>
```

**CSS selector:** `[data-action="signup"]`

### Test views

When testing SPA web experiences:

1. Navigate through all views where modifications apply.

1. Test the full user flow, including:
   * Direct navigation to a view (deep linking)
   * Navigation from other views within the SPA
   * Browser backward and forward navigation

1. Verify that modifications reapply when returning to a previously visited view.

### Handle view transitions

Some SPAs use animations or transitions between views. Consider:

* **Timing** - Ensure modifications apply after transition animations complete.
* **Element visibility** - Elements may exist but be hidden during transitions.
* **Flickering** - Apply modifications early enough to avoid visible content changes.

## Troubleshooting

As you review the SPA design changes, use the following recommendations to resolve some common issues:

* **Modifications not appearing** - If modifications are not appearing on your SPA:

   1. **Check view tracking** - Verify that `sendEvent` calls include the correct view name.

   1. **Verify element existence** - Ensure that target elements are in the DOM when modifications apply.

   1. **Review selectors** - Confirm CSS selectors match the actual DOM structure.

   1. **Check console** - Look for JavaScript errors that might prevent modifications.

* **Modifications appearing briefly then disappearing** - This issue typically occurs when the SPA re-renders and replaces modified elements:

   1. Use more specific CSS selectors that remain stable across renders.

   1. Enable mutation observers to reapply modifications when elements are recreated.

   1. Work with your development team to add stable attributes to target elements.

* **Duplicate modifications** - If modifications appear multiple times:

   1. Check that view tracking events fire only once per view transition.

   1. Verify that modifications are scoped to specific views rather than applying globally.

## Related topics

* [Web experiences overview](./web-experiences.md)
* [Web experience design](./web-experience-design.md)
* [Web channel configurations](../admin/configure-channels-web.md)
