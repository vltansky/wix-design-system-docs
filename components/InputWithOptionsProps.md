
### inputElement
- type: element
- description: Use a customized input component instead of the default @wix/design-system `&lt;Input/&gt;` component
### closeOnSelect
- type: boolean
- description: Closes DropdownLayout on option selection
### customDropdown
- type: node
- description: Node which is displayed in dropdown
### onManuallyInput
- type: func
- description: A callback which is called when the user performs a Submit-Action.
Submit-Action triggers are: &#34;Enter&#34;, &#34;Tab&#34;, [typing any defined delimiters], Paste action.
`onManuallyInput(values: Array&lt;string&gt;): void - The array of strings is the result of splitting the input value by the given delimiters
### onOptionsShow
- type: func
- description: A callback which is called when options dropdown is shown
### onOptionsHide
- type: func
- description: A callback which is called when options dropdown is hidden
### valueParser
- type: func
- description: Function that receives an option, and should return the value to be displayed.
### dropdownWidth
- type: string
- description: Sets the width of the dropdown
### dropdownOffsetLeft
- type: string
- description: Sets the offset of the dropdown from the left
### showOptionsIfEmptyInput
- type: bool
- description: Controls whether to show options if input is empty
### highlight
- type: bool
- description: Mark in bold word parts based on search pattern
### native
- type: bool
- description: Indicates whether to render using the native select element
### showDrawerOnMobile
- type: bool
- description: Controls whether to show drawer on mobile devices
### popoverProps
- type: shape
- description: common popover props
### onSelect
- type: (option: DropdownLayoutValueOption, sameOptionWasPicked: boolean) =&gt; void
- description: Callback function called whenever the user selects a different option in the list
### options
- type: DropdownLayoutOption[]
- description: Array of objects:
- id `&lt;string / number&gt;` *required*: the id of the option, should be unique.
- value `&lt;function / string / node&gt;` *required*: can be a string, react element or a builder function.
- disabled `&lt;bool&gt;` *default value- false*: whether this option is disabled or not
- linkTo `&lt;string&gt;`: when provided the option will be an anchor to the given value
- title `&lt;bool&gt;`  *default value- false*  **deprecated**: please use `listItemSectionBuilder` for rendering a title.
- overrideStyle `&lt;bool&gt;` *default value- false*  **deprecated**: please use `overrideOptionStyle` for override option styles.
- overrideOptionStyle `&lt;bool&gt;` *default value- false* - when set to `true`, the option will be responsible to its own styles. No styles will be applied from the DropdownLayout itself.
- label `&lt;string&gt;`: the string displayed within an input when the option is selected. This is used when using `&lt;DropdownLayout/&gt;` with an `&lt;Input/&gt;`.
### autocomplete
- type: string
- description: Sets the value of native autocomplete attribute (check the [HTML spec](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-autocomplete) for possible values
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component&#39;s root element.
### dropDirectionUp
- type: boolean
- description: No description
### focusOnSelectedOption
- type: boolean
- description: Scroll view to the selected option on opening the dropdown
### onClose
- type: () =&gt; void
- description: Callback function called whenever the user press the `Escape` keyboard.
### onOptionMarked
- type: (option: DropdownLayoutValueOption, optionElementId?: string) =&gt; void
- description: Callback function called whenever an option becomes focused (hovered/active). Receives the relevant option object from the original props.options array.
### onOptionsNavigate
- type: (option: DropdownLayoutValueOption) =&gt; void
- description: Callback function called whenever the user navigates to an option (via keyboard or mouse). Receives the relevant option object from the original props.options array, or null when navigation is cleared.
### visible
- type: boolean
- description: Should show or hide the component
### selectedId
- type: string | number
- description: The id of the selected option in the list
### tabIndex
- type: number
- description: Indicates that element can be focused and where it participates in sequential keyboard navigation
### onClickOutside
- type: (e: TouchEvent | MouseEvent) =&gt; void
- description: No description
### fixedHeader
- type: ReactNode
- description: A fixed header to the list
### fixedFooter
- type: ReactNode
- description: A fixed footer to the list
### maxHeightPixels
- type: string | number
- description: Set the max height of the dropdownLayout in pixels
### minWidthPixels
- type: string | number
- description: Set the min width of the dropdownLayout in pixels
### withArrow
- type: boolean
- description: No description
### onMouseEnter
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function called whenever the user entered with the mouse to the dropdown layout.
### onMouseLeave
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function called whenever the user exited with the mouse from the dropdown layout.
### onMouseDown
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function called whenever the user clicks the dropdown layout.
### itemHeight
- type: DropdownLayoutItemHeight
- description: No description
### size
- type: InputSize
- description: Controls the size of the input. Default value: `medium`
### selectedHighlight
- type: boolean
- description: Whether the selected option will be highlighted when dropdown reopened.
### inContainer
- type: boolean
- description: Whether the `&lt;DropdownLayout/&gt;` is in a container component. If `true`, some styles such as shadows, positioning and padding will be added the the component contentContainer.
### infiniteScroll
- type: boolean
- description: Set this prop for lazy loading of the dropdown layout items.
### loadMore
- type: (page: number) =&gt; void
- description: A callback called when more items are requested to be rendered.
### hasMore
- type: boolean
- description: Whether there are more items to be loaded.
### markedOption
- type: string | number | boolean
- description: Sets the default hover behavior when:
1. `false` means no default
2. `true` means to hover the first selectable option
3. Any number/string represents the id of option to hover
### overflow
- type: Overflow
- description: Set overflow of container
### focusOnOption
- type: string | number
- description: Marks (not selects) and scrolls view to the option on opening the dropdown by option id
### scrollToOption
- type: string | number
- description: Scrolls to the specified option when dropdown is opened without marking it
### listType
- type: ListType
- description: Defines type of behavior applied in list
### autoFocus
- type: boolean
- description: Focus the element on mount (standard React input autoFocus)
### scrollbar
- type: &#34;overlay&#34; | &#34;fixed&#34;
- description: Controls which type of scrollbar to render
### listboxId
- type: string
- description: Defines the id for the listbox
### overlayScrollbarProps
- type: { OverlayScrollbarHostElement: React.FunctionComponent&lt;any&gt;; OverlayScrollbarContentElement: React.ForwardRefExoticComponent&lt;any&gt;; }
- description: No description
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
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
### autoSelect
- type: boolean
- description: Automatically selects the entire input text
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
### suffix
- type: ReactNode
- description: Pass a component you want to show as the suffix of the input, e.g., text, icon
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
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


