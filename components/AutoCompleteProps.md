
### ariaControls
- type: string
- description: Associate a control with the regions that it controls.
### ariaDescribedby
- type: string
- description: Associate a region with its descriptions. Similar to aria-controls but instead associating descriptions to the region and description identifiers are separated with a space.
### ariaLabel
- type: string
- description: Define a string that labels the current element in case where a text label is not visible on the screen.
### autoFocus
- type: bool
- description: Focus the element on mount (standard React input autoFocus).
### border
- type: enum
- description: Control the border style of input.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### clearButton
- type: bool
- description: Displays clear button (X) on a non-empty input.
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### closeOnSelect
- type: bool
- description: Closes DropdownLayout when option is selected.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### defaultValue
- type: string
- description: Sets a default value for those who want to use this component un-controlled.
### disabled
- type: bool
- description: Specifies whether input should be disabled or not.
### disableEditing
- type: bool
- description: Restricts input editing.
### dropdownWidth
- type: string
- description: Sets the width of the dropdown in pixels.
### emptyStateMessage
- type: node
- description: Defines a message to be displayed instead of options when no options exist or no options pass the predicate filter function.
### fixedFooter
- type: node
- description: Adds a fixed footer container at the bottom of options list in `&lt;DropdownLayout/&gt;`.
### fixedHeader
- type: node
- description: Adds a fixed header container at the top of options list in `&lt;DropdownLayout/&gt;`.
### focusOnOption
- type: union
- description: Highlights and scrolls view to the specified option when dropdown layout is opened. It does not select the specified option.
### focusOnSelectedOption
- type: bool
- description: Scrolls view to the selected option when dropdown layout is opened.
### forceFocus
- type: bool
- description: USED FOR TESTING. Forces focus state on the input.
### forceHover
- type: bool
- description: USED FOR TESTING. Forces hover state on the input.
### hasMore
- type: bool
- description: Specifies whether there are more items to be loaded.
### hideStatusSuffix
- type: bool
- description: Specifies whether status suffix should be hidden.
### highlight
- type: bool
- description: Highlight word parts that match search criteria in bold.
### id
- type: string
- description: Assigns an unique identifier for the root element.
### infiniteScroll
- type: bool
- description: Specifies whether lazy loading of the dropdown layout items is enabled.
### loadMore
- type: func
- description: Defines a callback function which is called on a request to render more list items.
### markedOption
- type: union
- description: ##### Sets the default hover behavior:
 * `false` - no initially hovered list item
 * `true` - hover first selectable option
 *  any `number/string` - specify the id of an option to be hovered
### maxHeightPixels
- type: union
- description: Sets the maximum height of the dropdownLayout in pixels.
### maxLength
- type: number
- description: Sets the maximum number of characters that can be entered into a field.
### menuArrow
- type: bool
- description: Specifies whether input should have a dropdown menu arrow on the right side.
### minWidthPixels
- type: union
- description: Sets the minimum width of dropdownLayout in pixels.
### name
- type: string
- description: Reference element data when a form is submitted.
### noLeftBorderRadius
- type: bool
- description: Specifies whether input shouldn’t have rounded corners on its left.
### noRightBorderRadius
- type: bool
- description: Specifies whether input shouldn’t have rounded corners on its right.
### onBlur
- type: func
- description: Defines a standard input onBlur callback
### onChange
- type: func
- description: Defines a standard input onChange callback.
### onClear
- type: func
- description: Displays clear button (X) on a non-empty input and calls a callback function with no arguments.
### onClose
- type: func
- description: Defines a callback function which is called whenever the user presses the escape key.
### onCompositionChange
- type: func
- description: Defines a callback function called on compositionstart/compositionend events.
### onEnterPressed
- type: func
- description: Defines a callback handler that is called when user presses `enter`.
### onEscapePressed
- type: func
- description: Defines a callback handler that is called when user presses `escape`.
### onFocus
- type: func
- description: Defines a standard input onFocus callback.
### onInputClicked
- type: func
- description: Defines a standard input onClick callback.
### onKeyDown
- type: func
- description: Defines a standard input onKeyUp callback.
### onManuallyInput
- type: func
- description: Defines a callback function which is called when user performs a submit action. Submit action triggers are: &#34;Enter&#34;, &#34;Tab&#34;, [typing any defined delimiters], paste action. `onManuallyInput(values: Array): void - The array of strings is the result of splitting the input value by the given delimiters.
### onMouseEnter
- type: func
- description: Defines a callback function which is called whenever the user enters dropdown layout with the mouse cursor.
### onMouseLeave
- type: func
- description: Defines a callback function which is called whenever the user exits from dropdown layout with a mouse cursor.
### onOptionMarked
- type: func
- description: Defines a callback function which is called whenever an option becomes focused (hovered/active). Receives the relevant option object from the original props.options array.
### onOptionsHide
- type: func
- description: Defines a callback function which is called when options dropdown is hidden.
### onOptionsShow
- type: func
- description: Defines a callback function which is called when options dropdown is shown.
### onEmptyState
- type: func
- description: Defines a callback function which is called when no options exist.
### onPaste
- type: func
- description: Defines a callback handler that is called when user pastes text from a clipboard (using mouse or keyboard shortcut).
### onSelect
- type: func
- description: Defines a callback function which is called whenever user selects a different option in the list.
### options
- type: arrayOf
- description: Specify an array of options:
- id `&lt;string / number&gt;` *required*: the id of the option, should be unique.
- value `&lt;function / string / node&gt;` *required*: can be a string, react element or a builder function.
- disabled `&lt;bool&gt;` *default value- false*: whether this option is disabled or not
- linkTo `&lt;string&gt;`: when provided the option will be an anchor to the given value
- title `&lt;bool&gt;`  *default value- false*  **deprecated**: please use `listItemSectionBuilder` for rendering a title.
- overrideStyle `&lt;bool&gt;` *default value- false*  **deprecated**: please use `overrideOptionStyle` for override option styles.
- overrideOptionStyle `&lt;bool&gt;` *default value- false* - when set to `true`, the option will be responsible to its own styles. No styles will be applied from the DropdownLayout itself.
- label `&lt;string&gt;`: the string displayed within an input when the option is selected. This is used when using `&lt;DropdownLayout/&gt;` with an `&lt;Input/&gt;`.
### overflow
- type: string
- description: Handles container overflow.
### pattern
- type: string
- description: Sets a pattern that typed value must match to be valid (regex).
### placeholder
- type: string
- description: Sets a placeholder message to display.
### popoverProps
- type: shape
- description: Allows to pass all common popover props.
### predicate
- type: func
- description: Defines a callback predicate for the filtering options function.
### prefix
- type: node
- description: Pass a component you want to show as the prefix of the input, e.g., text string, icon.
### readOnly
- type: bool
- description: Specifies whether input is read only.
### required
- type: bool
- description: Specifies whether input is mandatory.
### selectedId
- type: union
- description: Specifies selected option by its id.
### showOptionsIfEmptyInput
- type: bool
- description: Controls whether to show options if input is empty.
### size
- type: enum
- description: Controls the size of the input. Default value: `medium`
### status
- type: enum
- description: Specify the status of a field.
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### suffix
- type: node
- description: Pass a component you want to show as the suffix of the input, e.g., text string, icon.
### tabIndex
- type: number
- description: Indicates that element can be focused and where it participates in sequential keyboard navigation.
### textOverflow
- type: string
- description: Handles text overflow behavior. It can either clip (default) or display ellipsis.
### tooltipPlacement
- type: string
- description: Controls placement of a status tooltip.
### type
- type: string
- description: Specifies the type of `&lt;input/&gt;` element to display. Default is text string.
### autoSelect
- type: any
- description: No description
### dropdownOffsetLeft
- type: any
- description: No description
### inContainer
- type: any
- description: No description
### selectedHighlight
- type: any
- description: No description
### inputElement
- type: any
- description: No description
### autocomplete
- type: any
- description: No description


