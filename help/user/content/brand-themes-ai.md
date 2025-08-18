# None

Adobe Journey Optimizer includes the "None" option to provide greater flexibility when configuring conditions and actions within journeys. This topic explains how "None" works, its primary use cases, and important considerations for journey design.

## Overview of the "None" option

The "None" option allows you to specify that no selection or value applies in certain fields, settings, or configuration options. This enables you to set up journeys that do not require every parameter to be defined or to exclude a specific configuration when it is not needed.

Using "None" helps simplify journey logic. It lets you bypass unnecessary choices, reduce complexity, and clearly indicate that a given setting or condition should remain unselected. In Adobe Journey Optimizer, you may find "None" in dropdown menus, conditions, or other configuration panels.

## Common use cases

* Excluding conditions or parameters  
  When designing journeys, you sometimes need to indicate that a particular attribute or condition should remain unset. Choosing "None" in a dropdown means that the journey will proceed without using the associated filter, action, or setting.

* Creating default or catch-all paths  
  Selecting "None" allows a journey to cover scenarios where no specific value applies. This helps manage cases that fall outside of predefined segments or conditions, ensuring that the journey handles all relevant customer records.

* Resetting selected values  
  If you previously chose a value in a field, you can select "None" to reset that field. This removes the selected value and returns the setting to its default state.

## How to use "None" in Adobe Journey Optimizer

When you configure a journey, you may encounter dropdown lists, toggles, or selection panels that include "None" as an option. Follow these steps to use "None":

1. Open the relevant configuration pane in your journey.
1. Locate the field or dropdown that supports using "None."
1. Select "None" from the available choices.
1. Save your configuration or proceed to the next step in the journey setup.

Selecting "None" ensures that the system treats the field as unselected or unset. The journey will not consider the excluded condition or value when executing or evaluating customers.

## Considerations and best practices

* Clearly document where and why you select "None" to help other users understand the journey's logic.
* Use "None" when excluding a parameter produces the desired journey behavior. Selecting "None" does not add any filter or action related to that parameter.
* Confirm that using "None" aligns with your data strategy. Selecting "None" in required fields can result in incomplete journey logic or unexpected outcomes.
* Review dependencies. Some journeys may rely on specific values; choosing "None" could make parts of the journey inactive or bypass intended steps.

## Troubleshooting

If you select "None" and the journey does not behave as expected:

* Review journey logic to identify dependencies on the excluded field.
* Check for validation errors or warnings that indicate missing required settings.
* Examine reporting and analytics in Adobe Journey Optimizer to confirm that customer segments or actions align with your expectations.

## Summary

The "None" option in Adobe Journey Optimizer offers a flexible approach to journey configuration. Use "None" to exclude unnecessary values, reset fields, and manage default paths. Always ensure that selecting "None" matches your intended journey outcomes and maintains clear logic for other users.