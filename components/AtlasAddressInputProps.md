
### baseUrl
- type: string
- description: Accept a custom domain for WixAtlasServiceWeb to retrieve predictions from
### token
- type: string
- description: Sets an authorization token to pass to the Atlas Service
### language
- type: string
- description: Sets the `language` to pass to the Atlas Service.
Use the language code e.g. `&#39;en&#39;`.
### locale
- type: string
- description: Sets the `locale` to pass to the Atlas Service.
Locale consists of language code and country code separated by a dash e.g. `&#39;en-us&#39;`.
### debounceMs
- type: number
- description: Fetch predictions debounce in milliseconds (default: 200)
### debounceFn
- type: func
- description: Allows passing a custom debounce function (default: lodash debounce).
Usage:
(callback: Function, debounceMs: number) =&gt; Function
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### clearButton
- type: bool
- description: Displays clear button (X) on a non-empty input
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### initialValue
- type: string
- description: Sets the initial input value
### value
- type: string
- description: Sets a value to display (controlled mode)
### disabled
- type: bool
- description: Specifies whether input is disabled
### onSelect
- type: func
- description: Defines a callback function which is called whenever a user selects a different option in the list.
### onChange
- type: func
- description: Defines a callback function which is called every time input value is changed
### onClear
- type: func
- description: Defines a handler for getting notified upon a clear event. When passed, it displays a clear button in the input.
### onFocus
- type: func
- description: Defines a standard input onFocus callback
### onBlur
- type: func
- description: Defines a standard input onBlur callback
### autoSelect
- type: bool
- description: Specifies whether input is auto selected on focus
### selectOnSubmit
- type: bool
- description: Specifies whether to trigger `onSelect` handler when performing a Submit-Action (Enter or Tab key down).
If set to true, `onSelect` will be called with the following params:

`option`: an option with a label set to the input value.

`getAddress`: function for retrieving additional place details
   uses Atlas&#39;s search function to return the closest result to the input value

This is useful when looking for locations for which Atlas does not give suggestions - for example: Apartment/Apt.
### onError
- type: func
- description: Defines a handler for prediction fetching errors. Returns an error object.
you can read these [guidelines](https://bo.wix.com/wix-docs/rnd/platformization-guidelines/errors#platformization-guidelines_errors_errors)
to learn about the meaning of each error status.
### status
- type: enum
- description: Specify the status of a field. Mostly used for a “loading” indication upon async request calls.
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip
### border
- type: enum
- description: Control the border style of an input
### size
- type: enum
- description: Controls the size of the input
### placeholder
- type: string
- description: Sets a placeholder message to display
### noResultsText
- type: union
- description: Sets the message to show in a dropdown when no results are found
### optionLayout
- type: enum
- description: Sets the layout of `mainLabel` and `secondaryLabel`. The possible options can be either side by side or vertically stacked.
### optionPrefix
- type: node
- description: Pass any component to show as the prefix of the option, e.g., text, icon.
### optionSuffix
- type: node
- description: Pass any component to show as the suffix of the option, e.g., text, icon, button.
### popoverProps
- type: shape
- description: Allows to pass common popover props


