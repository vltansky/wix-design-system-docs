
### ariaControls
- type: string
- description: Associate a control with the regions that it controls
### ariaDescribedby
- type: string
- description: Associate a region with its descriptions. Similar to aria-controls but instead associating descriptions to the region and description identifiers are separated with a space.
### ariaLabel
- type: string
- description: Define a string that labels the current element in case where a text label is not visible on the screen
### autocomplete
- type: string
- description: Sets the value of native autocomplete attribute (consult the [HTML spec](https://html.spec.whatwg.org/multipage/form-control-infrastructure.html#attr-fe-autocomplete) for possible values)
### autoFocus
- type: bool
- description: Focus the element on mount (standard React input autoFocus)
### border
- type: enum
- description: Control the border style of input
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### clearButton
- type: bool
- description: Displays clear button (X) on a non-empty input
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### closeOnSelect
- type: bool
- description: Closes DropdownLayout when option is selected
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### debounceMs
- type: number
- description: Specifies the `onChange` debounce in milliseconds
### defaultValue
- type: string
- description: Defines the initial value of an input for those who want to use this component un-controlled
### disabled
- type: bool
- description: Specifies whether the input should be disabled or not
### disableEditing
- type: bool
- description: Restricts input editing
### dropdownWidth
- type: string
- description: Sets the width of the dropdown in pixels
### renderEmptyState
- type: func
- description: Function which returns custom node shown when no options are available
### expandable
- type: bool
- description: Specifies whether to collapse input to search icon only. Once clicked, icon will expand to a full search input.
### expandWidth
- type: union
- description: Specifies the width of an input in an  expanded state
### expandDirection
- type: enum
- description: Specifies the direction of expansion animation when expandable is true
### forceFocus
- type: bool
- description: USED FOR TESTING - forces focus state on the input
### forceHover
- type: bool
- description: USED FOR TESTING - forces hover state on the input
### hasMore
- type: bool
- description: Specifies whether there are more items to be loaded
### hideStatusSuffix
- type: bool
- description: Specifies whether the status suffix should be hidden
### highlight
- type: bool
- description: Highlight word parts that match search criteria in bold
### id
- type: string
- description: Assigns an unique identifier for the root element
### infiniteScroll
- type: bool
- description: Specifies whether lazy loading of the dropdown layout items is enabled
### loadMore
- type: func
- description: Defines a callback function which is called on a request to render more list items
### maxHeightPixels
- type: union
- description: Sets the maximum height of the `dropdownLayout` in pixels
### maxLength
- type: number
- description: Sets the maximum number of characters that can be entered into a field
### minWidthPixels
- type: union
- description: Sets the minimum width of dropdownLayout in pixels
### name
- type: string
- description: Reference element data when a form is submitted
### noLeftBorderRadius
- type: bool
- description: Specifies whether input shouldn’t have rounded corners on its left
### noRightBorderRadius
- type: bool
- description: Specifies whether input shouldn’t have rounded corners on its right
### onBlur
- type: func
- description: Defines a standard input `onBlur` callback
### onChange
- type: func
- description: Defines a standard input `onChange` callback
### onClear
- type: func
- description: Displays clear button (X) on a non-empty input and calls a callback function with no arguments
### onClose
- type: func
- description: Defines a callback function which is called whenever the user presses the escape key
### onCompositionChange
- type: func
- description: Defines a callback function called on `compositionstart`/`compositionend` events
### onEnterPressed
- type: func
- description: Defines a callback handler that is called when the presses -enter-
### onEscapePressed
- type: func
- description: Defines a callback handler that is called when the user presses -escape-
### onFocus
- type: func
- description: Defines a standard input `onFocus` callback
### onInputClicked
- type: func
- description: Defines a standard input `onClick` callback
### onKeyDown
- type: func
- description: Defines a standard input `onKeyDown` callback
### onKeyUp
- type: func
- description: Defines a standard input `onKeyUp` callback
### onManuallyInput
- type: func
- description: Defines a callback function which is called when the user performs a submit action. Submit action triggers are:
&#34;Enter&#34;, &#34;Tab&#34;, [typing any defined delimiters], paste action.
`onManuallyInput(values: Array&lt;string&gt;): void` - the array of strings is the result of splitting the input value by the given delimiters
### onMouseEnter
- type: func
- description: Defines a callback function which is called whenever the user enters dropdown layout with the mouse cursor
### onMouseLeave
- type: func
- description: Defines a callback function which is called whenever the user exits from dropdown layout with a mouse cursor
### onOptionMarked
- type: func
- description: Defines a callback function which is called whenever an option becomes focused (hovered/active). Receives the relevant option object from the original `props.options array`.
### onOptionsHide
- type: func
- description: Defines a callback function which is called when options dropdown is hidden
### onOptionsShow
- type: func
- description: Defines a callback function which is called when the options dropdown is shown
### onPaste
- type: func
- description: Defines a callback handler that is called when user pastes text from a clipboard (using mouse or keyboard shortcut)
### onSelect
- type: func
- description: Defines a callback function which is called whenever user selects a different option in the list
### options
- type: arrayOf
- description: Array of objects:
- `id &lt;string / number&gt;` *required*: the id of the option, should be unique;
- value `&lt;function / string / node&gt;` *required*: can be a string, react element or a builder function;
- disabled `&lt;bool&gt;` *default value- false*: whether this option is disabled or not;
- linkTo `&lt;string&gt;`: when provided the option will be an anchor to the given value;
- title `&lt;bool&gt;`  *default value- false*  **deprecated**: please use `listItemSectionBuilder` for rendering a title;
- overrideStyle `&lt;bool&gt;` *default value- false*  **deprecated**: please use `overrideOptionStyle` for override option styles;
- overrideOptionStyle `&lt;bool&gt;` *default value- false* - when set to `true`, the option will be responsible for its own styles. No styles will be applied from the DropdownLayout itself;
- label `&lt;string&gt;`: the string displayed within an input when the option is selected. This is used when using `&lt;DropdownLayout/&gt;` with an `&lt;Input/&gt;`.
### overflow
- type: string
- description: Handles container overflow
### pattern
- type: string
- description: Sets a pattern that the typed value must match to be valid (regex)
### placeholder
- type: string
- description: Sets a placeholder message to display
### popoverProps
- type: shape
- description: Allows to pass common popover props. Check `&lt;Popover/&gt;` API for a full list.
### predicate
- type: func
- description: Defines a custom function for options filtering
### readOnly
- type: bool
- description: Specifies whether input is read only
### required
- type: bool
- description: Specifies that an input must be filled out before submitting the form
### scrollbar
- type: enum
- description: Controls which type of scrollbar to render inside the dropdown
### selectedId
- type: union
- description: Specifies selected option by its id
### showOptionsIfEmptyInput
- type: bool
- description: Controls whether to show options if input is empty
### size
- type: enum
- description: Controls the size of the input
### status
- type: enum
- description: Specify the status of a field
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### tabIndex
- type: number
- description: Indicates that element can be focused and where it participates in sequential keyboard navigation
### textOverflow
- type: string
- description: Handles text overflow behavior. It can either `clip` (default) or display `ellipsis`.
### tooltipPlacement
- type: string
- description: Controls the placement of a status tooltip
### type
- type: string
- description: Specifies the type of `&lt;input&gt;` element to display. The default type is text.
### value
- type: union
- description: Specifies the current value of the element
### onExpandTransitionStart
- type: func
- description: Callback function that is called when the expandable input starts expanding or collapsing
### onExpandTransitionEnd
- type: func
- description: Callback function that is called when the expandable input finishes expanding or collapsing


