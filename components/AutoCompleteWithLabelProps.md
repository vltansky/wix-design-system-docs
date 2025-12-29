
### dataHook
- type: string
- description: Sets a default value for those who want to use this component un-controlled.
### label
- type: string
- description: Defines a value label to show inside of a field.
### options
- type: arrayOf
- description: Specify an array of options to display in the dropdown list.
### suffix
- type: arrayOf
- description: Pass a component you want to show as the suffix of the input, e.g., text string, icon.
### status
- type: enum
- description: Specify the status of a field.
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### onFocus
- type: func
- description: Defines a standard input onFocus callback.
### onBlur
- type: func
- description: Defines a standard input onBlur callback
### onChange
- type: func
- description: Defines a standard input onChange callback.
### name
- type: string
- description: Reference element data when a form is submitted.
### type
- type: string
- description: Specifies the type of `&lt;input/&gt;` element to display. Default is text string.
### ariaLabel
- type: string
- description: Define a string that labels the current element in case where a text label is not visible on the screen.
### autoFocus
- type: bool
- description: Focus the element on mount (standard React input autoFocus).
### autocomplete
- type: string
- description: Sets the value of native autocomplete attribute (check the [HTML spec](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-autocomplete) for possible values
### disabled
- type: bool
- description: Specifies whether input should be disabled or not.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### maxLength
- type: number
- description: Sets the maximum number of characters that can be entered into a field.
### placeholder
- type: string
- description: Sets a placeholder message to display.
### onSelect
- type: func
- description: Defines a callback function which is called whenever user selects a different option in the list.
### native
- type: bool
- description: Indicates whether to render using the native select element
### value
- type: union
- description: Value of rendered child input
### maxHeightPixels
- type: union
- description: Sets the maximum height of the dropdownLayout in pixels.


