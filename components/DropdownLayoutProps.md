
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dropDirectionUp
- type: boolean
- description: No description
### focusOnSelectedOption
- type: boolean
- description: Scroll view to the selected option on opening the dropdown
### onClose
- type: () =&gt; void
- description: Callback function called whenever the user press the `Escape` keyboard.
### onSelect
- type: (option: DropdownLayoutValueOption, sameOptionWasPicked: boolean) =&gt; void
- description: Callback function called whenever the user selects a different option in the list
### onOptionMarked
- type: (option: DropdownLayoutValueOption, optionElementId?: string) =&gt; void
- description: Callback function called whenever an option becomes focused (hovered/active). Receives the relevant option object from the original props.options array.
### onOptionsNavigate
- type: (option: DropdownLayoutValueOption) =&gt; void
- description: Callback function called whenever the user navigates to an option (via keyboard or mouse). Receives the relevant option object from the original props.options array, or null when navigation is cleared.
### visible
- type: boolean
- description: Should show or hide the component
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
### selectedId
- type: string | number
- description: The id of the selected option in the list
### tabIndex
- type: number
- description: Specifies the tab order of the component.
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
### closeOnSelect
- type: boolean
- description: Closes DropdownLayout on option selection
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
- type: ListItemSelectSizes
- description: Controls the size of internally rendered ListItemSelect or ListItemAction components
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
- description: Specifies whether first list item should be focused
### scrollbar
- type: &#34;overlay&#34; | &#34;fixed&#34;
- description: Controls which type of scrollbar to render
### listboxId
- type: string
- description: Defines the id for the listbox
### overlayScrollbarProps
- type: { OverlayScrollbarHostElement: React.FunctionComponent&lt;any&gt;; OverlayScrollbarContentElement: React.ForwardRefExoticComponent&lt;any&gt;; }
- description: No description
### ref
- type: React.ForwardedRef&lt;DropdownLayout&gt;
- description: No description


