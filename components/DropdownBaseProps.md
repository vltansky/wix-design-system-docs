
### open
- type: boolean
- description: Control whether the &lt;Popover/&gt; should be opened
### onShow
- type: () =&gt; void
- description: Defines a callback function which is called when dropdown is opened
### onHide
- type: () =&gt; void
- description: Defines a callback function which is called when dropdown is closed
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### popoverContentClassName
- type: string
- description: Specifies a CSS class name to be appended to the popover&#39;s content.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### placement
- type: &#34;auto&#34; | &#34;auto-start&#34; | &#34;auto-end&#34; | Placement
- description: Control popover placement
### appendTo
- type: AppendTo
- description: Specifies where popover should be inserted as a last child - whether `parent` or `window` containers
### showArrow
- type: boolean
- description: Specifies whether popover arrow should be shown
### onClickOutside
- type: () =&gt; void
- description: Defines a callback function which is called when user clicks outside of a dropdown
### onMouseEnter
- type: () =&gt; void
- description: Defines a callback function which is called on `onMouseEnter` event on the entire component
### onMouseLeave
- type: () =&gt; void
- description: Defines a callback function which is called on `onMouseLeave` event on the entire component
### onMouseDown
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: No description
### onSelect
- type: (option: DropdownLayoutValueOption) =&gt; void
- description: Defines a callback function which is called whenever user selects a different option in the list
### dynamicWidth
- type: boolean
- description: Set popover&#39;s content width to a minimum width of a trigger element,
but it can expand up to the defined value of `maxWidth`
### maxWidth
- type: MaxWidth&lt;string | number&gt;
- description: Controls the maximum width of dropdown layout
### minWidth
- type: MinWidth&lt;string | number&gt;
- description: Controls the minimum width of dropdown layout
### width
- type: Width&lt;string | number&gt;
- description: Controls the width of dropdown layout
### maxHeight
- type: string | number
- description: Controls the maximum height of dropdown layout
### children
- type: DropdownBaseChildrenFn
- description: Specifies a target component to be rendered. If a regular node is passed, it&#39;ll be rendered as-is.
If a function is passed, it&#39;s expected to return a React element.
The function accepts an object containing the following properties:

 * `open` - will open the Popover
 * `close` - will close the Popover
 * `toggle` - will toggle the Popover
 * `isOpen` - indicates whether the items list is currently open
 * `delegateKeyDown` - the underlying DropdownLayout&#39;s keydown handler. It can be called
                       inside another keyDown event in order to delegate it.
 * `selectedOption` - the currently selected option

Check inserted component documentation for more information on available properties.
### options
- type: DropdownLayoutOption[]
- description: Specifies an array of options for a dropdown list. Objects must have an id and can include string value or node.
If value is &#39;-&#39;, a divider will be rendered instead (dividers do not require and id).
### selectedId
- type: string | number
- description: Define the selected option in the list
### overflow
- type: Overflow
- description: Handles container overflow behaviour
### tabIndex
- type: number
- description: Indicates that element can be focused and where it participates in sequential keyboard navigation
### initialSelectedId
- type: string | number
- description: Sets the initially selected option in the list. Used when selection
behaviour is being controlled.
### zIndex
- type: number
- description: Specifies the stack order (`z-index`) of a dropdown layout
### moveBy
- type: MoveByOffset
- description: Moves dropdown content relative to the parent on X or Y axis by a defined amount of pixels
### flip
- type: boolean
- description: Specifies whether to flip the &lt;Popover/&gt; placement
when it starts to overlap the target element (&lt;Popover.Element/&gt;)
### fixed
- type: boolean
- description: Specifies whether to enable the fixed behaviour. If enabled, &lt;Popover/&gt; keep its
original placement even when it&#39;s being positioned outside the boundary.
### fluid
- type: boolean
- description: Stretches trigger element to fill its parent container width
### animate
- type: boolean
- description: Adds enter and exit animation
### focusOnSelectedOption
- type: boolean
- description: Focus to the selected option when dropdown is opened
### infiniteScroll
- type: boolean
- description: Specifies whether lazy loading of the dropdown items is enabled
### loadMore
- type: (page: number) =&gt; void
- description: Defines a callback function which is called on a request to render more list items
### hasMore
- type: boolean
- description: Specifies whether there are more items to load
### focusOnOption
- type: string | number
- description: Focus to the specified option when dropdown is opened
### scrollToOption
- type: string | number
- description: Scrolls to the specified option when dropdown is opened without marking it
### fixedHeader
- type: ReactNode
- description: A fixed header to the list
### fixedFooter
- type: ReactNode
- description: A fixed footer to the list
### listType
- type: ListType
- description: Defines type of behavior applied in list
### autoFocus
- type: boolean
- description: Specifies whether first list item should be focused
### markedOption
- type: string | number | boolean
- description: Sets the initial marking of an option in the list when opened:
- `false` - no initially hovered list item
- `true` - hover first selectable option
- any `number/string` specify the id of an option to be hovered


