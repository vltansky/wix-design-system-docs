
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component&#39;s root element.
### id
- type: string
- description: Assigns a unique identifier for the root element
### role
- type: string
- description: Specifies the role of the input element for accessibility
### ariaControls
- type: string
- description: Associate a control with the regions that it controls
### ariaDescribedby
- type: string
- description: Associate a region with its descriptions. Similar to aria-controls but instead associating descriptions to the region and description identifiers are separated with a space.
### ariaLabel
- type: string
- description: Define a string that labels the current element in case where a text label is not visible on the screen
### autoFocus
- type: boolean
- description: Focus the element on mount (standard React input autoFocus)
### autoSelect
- type: boolean
- description: Automatically selects the entire input text
### autocomplete
- type: string
- description: Sets the value of native autocomplete attribute (check the [HTML spec](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-autocomplete) for possible values
### defaultValue
- type: InputValue
- description: Defines the initial value of an input
### disabled
- type: boolean
- description: Specifies whether input should be disabled or not
### status
- type: InputStatus
- description: Specify the status of a field
### statusMessage
- type: ReactNode
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### statusMessageTooltipProps
- type: TooltipCommonProps
- description: Status message tooltip props
### hideStatusSuffix
- type: boolean
- description: Specifies whether status suffix should be hidden
### forceFocus
- type: boolean
- description: USED FOR TESTING - forces focus state on the input
### forceHover
- type: boolean
- description: USED FOR TESTING - forces hover state on the input
### maxLength
- type: number
- description: Sets the maximum number of characters that can be inserted to a field
### menuArrow
- type: boolean
- description: Specifies whether input should have a dropdown menu arrow on the right side
### clearButton
- type: boolean
- description: Displays clear button (X) on a non-empty input
### focusOnClearClick
- type: boolean
- description: Specifies whether to focus the field when clear button is clicked
### name
- type: string
- description: Reference element data when a form is submitted
### border
- type: &#34;standard&#34; | &#34;round&#34; | &#34;bottomLine&#34; | &#34;none&#34;
- description: Control the border style of input
### noLeftBorderRadius
- type: boolean
- description: Specifies whether input shouldn&#39;t have rounded corners on its left
### noRightBorderRadius
- type: boolean
- description: Specifies whether input shouldn&#39;t have rounded corners on its right
### onBlur
- type: FocusEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onBlur callback
### onChange
- type: ChangeEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onChange callback
### onClear
- type: (event: MouseEvent&lt;HTMLButtonElement, MouseEvent&gt; | KeyboardEvent&lt;HTMLButtonElement&gt;) =&gt; void
- description: Displays clear button (X) on a non-empty input and calls a callback function
### onCompositionChange
- type: (isComposing: boolean) =&gt; void
- description: Defines a callback function called on compositionstart/compositionend events
### onEnterPressed
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback handler that is called when the user presses -enter-
### onEscapePressed
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback handler that is called when the user presses -escape-
### onFocus
- type: FocusEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onFocus callback
### onInputClicked
- type: MouseEventHandler&lt;HTMLInputElement | HTMLDivElement&gt;
- description: Defines a standard input onClick callback
### onKeyDown
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onKeyDown callback
### onKeyUp
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onKeyUp callback
### onPaste
- type: ClipboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback handler that is called when user pastes text from a clipboard (using a mouse or keyboard shortcut)
### onCopy
- type: ClipboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback handler that is called when user copies text to a clipboard (using a mouse or keyboard shortcut)
### placeholder
- type: string
- description: Sets a placeholder message to display
### prefix
- type: ReactNode
- description: Pass a component you want to show as the prefix of the input, e.g., text, icon
### readOnly
- type: boolean
- description: Specifies whether input is read only
### disableEditing
- type: boolean
- description: Restricts input editing
### rtl
- type: boolean
- description: No description
### size
- type: InputSize
- description: Controls the size of the input. Default value: `medium`
### suffix
- type: ReactNode
- description: Pass a component you want to show as the suffix of the input, e.g., text, icon
### tabIndex
- type: number
- description: Indicates that element can be focused and where it participates in sequential keyboard navigation
### textOverflow
- type: &#34;clip&#34; | &#34;ellipsis&#34;
- description: Handles text overflow behavior. It can either `clip` (default) or display `ellipsis`.
### tooltipPlacement
- type: Placement | &#34;auto&#34; | &#34;auto-start&#34; | &#34;auto-end&#34;
- description: Controls placement of a status tooltip
### type
- type: string
- description: Specifies the type of `&lt;input/&gt;` element to display. Default is text.
### value
- type: string | number
- description: Specifies the current value of the element
### withSelection
- type: boolean
- description: No description
### required
- type: boolean
- description: Specifies whether input is mandatory
### min
- type: number
- description: Sets a minimum value of an input. Similar to HTML5 min attribute.
### max
- type: number
- description: Sets a maximum value of an input. Similar to html5 max attribute.
### step
- type: number
- description: Specifies the interval between number values
### customInput
- type: Function | ReactNode
- description: Render a custom input instead of the default html input tag
### pattern
- type: string
- description: Sets a pattern that typed value must match to be valid (regex)
### inputRef
- type: (input: HTMLInputElement) =&gt; void
- description: No description
### inputmode
- type: string
- description: No description
### ariaRoledescription
- type: string
- description: No description
### clearButtonTooltipContent
- type: ReactNode
- description: When provided hover will display a tooltip with content
### clearButtonTooltipProps
- type: TooltipCommonProps
- description: Clear button tooltip props
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### inputElementRef
- type: any
- description: Specifies reference of the input element
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


