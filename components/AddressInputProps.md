
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### clearButton
- type: boolean
- description: Displays a clear button (X) on a non-empty input.
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### initialValue
- type: string
- description: Sets the initial input value.
### value
- type: string
- description: Sets a value to display (controlled mode).
### disabled
- type: boolean
- description: Specifies whether input is disabled.
### onSelect
- type: (option: DropdownLayoutValueOption) =&gt; void
- description: Defines a callback function which is called whenever a user selects a different option in the list.
### onManuallyInput
- type: ManualInputFnSignature
- description: Defines a callback function which is called when user performs a submit action.
Submit-Action triggers are: &#34;Enter&#34;, &#34;Tab&#34;.
### onChange
- type: ChangeEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback function which is called every time input value is changed.
### onFocus
- type: (e?: FocusEvent&lt;HTMLInputElement, Element&gt;) =&gt; void
- description: Defines a standard input onFocus callback.
### onBlur
- type: FocusEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onBlur callback.
### autoSelect
- type: boolean
- description: Specifies whether input is auto selected on focus.
### onClear
- type: () =&gt; void
- description: Defines a handler for getting notified upon a clear event. When passed, it displays a clear button in the input.
### options
- type: DropdownLayoutOption[]
- description: Specify an array of options to render. When the option is an {optionProps}, the &lt;AddressInput.Option/&gt; component will be rendered on behalf of the user.
### status
- type: AddressInputStatus
- description: Specify the status of a field. Mostly used for “loading” indication upon async request calls.
### statusMessage
- type: ReactNode
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### border
- type: AddressInputBorder
- description: Control the border style of an input.
### size
- type: AddressInputSize
- description: Controls the size of the input. Default value: `medium`.
### placeholder
- type: string
- description: Sets a placeholder message to display.
### noResultsText
- type: ReactNode
- description: Sets the message to show in a dropdown when no results are found.
### popoverProps
- type: PopoverCommonProps
- description: Allows to pass common popover props.
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


