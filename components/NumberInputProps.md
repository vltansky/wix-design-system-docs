
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### id
- type: string
- description: Assigns a unique identifier for the root element
### ariaControls
- type: string
- description: No description
### ariaDescribedby
- type: string
- description: No description
### ariaLabel
- type: string
- description: No description
### autoFocus
- type: boolean
- description: No description
### autoSelect
- type: boolean
- description: No description
### autocomplete
- type: string
- description: No description
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
### hideStatusSuffix
- type: boolean
- description: No description
### forceFocus
- type: boolean
- description: No description
### forceHover
- type: boolean
- description: No description
### maxLength
- type: number
- description: No description
### menuArrow
- type: boolean
- description: No description
### clearButton
- type: boolean
- description: No description
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### focusOnClearClick
- type: boolean
- description: No description
### name
- type: string
- description: Reference element data when a form is submitted
### border
- type: &#34;standard&#34; | &#34;round&#34; | &#34;bottomLine&#34; | &#34;none&#34;
- description: No description
### noLeftBorderRadius
- type: boolean
- description: No description
### noRightBorderRadius
- type: boolean
- description: No description
### onBlur
- type: FocusEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onBlur callback
### onClear
- type: (event: MouseEvent&lt;HTMLButtonElement, MouseEvent&gt; | KeyboardEvent&lt;HTMLButtonElement&gt;) =&gt; void
- description: No description
### onCompositionChange
- type: (isComposing: boolean) =&gt; void
- description: No description
### onEnterPressed
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: No description
### onEscapePressed
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: No description
### onFocus
- type: (e?: FocusEvent&lt;HTMLInputElement, Element&gt;) =&gt; void
- description: Defines a standard input onFocus callback
### onInputClicked
- type: MouseEventHandler&lt;HTMLInputElement&gt;
- description: No description
### onKeyDown
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: No description
### onKeyUp
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: No description
### onPaste
- type: ClipboardEventHandler&lt;HTMLInputElement&gt;
- description: No description
### placeholder
- type: string
- description: Sets a placeholder message to display
### prefix
- type: ReactNode
- description: Pass a component you want to show as the prefix of the input, e.g., text, icon
### readOnly
- type: boolean
- description: No description
### disableEditing
- type: boolean
- description: No description
### rtl
- type: boolean
- description: No description
### size
- type: InputSize
- description: Controls the size of the input
### suffix
- type: ReactNode
- description: Pass a component you want to show as the suffix of the input, e.g., text, icon
### tabIndex
- type: number
- description: No description
### textOverflow
- type: &#34;clip&#34; | &#34;ellipsis&#34;
- description: No description
### tooltipPlacement
- type: Placement | &#34;auto&#34; | &#34;auto-start&#34; | &#34;auto-end&#34;
- description: No description
### type
- type: string
- description: No description
### value
- type: string | number
- description: Specifies the current value of the element
### withSelection
- type: boolean
- description: No description
### required
- type: boolean
- description: No description
### min
- type: number
- description: Sets a minimum value of an input. Similar to HTML5 min attribute.
### max
- type: number
- description: Sets a maximum value of an input. Similar to html5 max attribute.
### step
- type: number | number[]
- description: Specifies the interval between number values
### customInput
- type: Function | ReactNode
- description: No description
### pattern
- type: string
- description: No description
### inputRef
- type: ((input: HTMLInputElement) =&gt; void) | MutableRefObject&lt;HTMLInputElement&gt;
- description: No description
### strict
- type: boolean
- description: No description
### hideStepper
- type: boolean
- description: Specifies whether stepper should be hidden
### onChange
- type: (value: number, stringValue: string) =&gt; void
- description: Defines a standard input onChange callback
### invalidMessage
- type: string
- description: Enables internal validation and defines a message to display when user types invalid value
### onInvalid
- type: (stringValue: string, { validationType, value, }: { validationType?: &#34;outOfBoundsError&#34; | &#34;formatError&#34;; value: string; }) =&gt; void
- description: Defines a callback function which is called on cases when invalid value is typed.
- return { stringValue: string, { validationType: &#39;formatError&#39; | &#39;outOfBoundsError&#39;, value: string }}
- `validationType` - type &#39;formatError&#39; is set when value is in the wrong format
                  - type &#39;outOfBoundsError&#39; is set when min or max props are used and value does not match the bounds
- `value` - is set to current input value


