
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### onClick
- type: React.ReactEventHandler&lt;HTMLElement&gt;
- description: Defines a callback when the item is clicked
### options
- type: TableListItemColumn[]
- description: Defines each TableListItem column  individually, using the following props:
- `value` - defines column’s content.
- `width` - sets the width of a column. It supports all grid-template-column values: [https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns)
- `align` - aligns the content in the horizontal axis.
### verticalPadding
- type: TableListItemPadding
- description: Adjusts the top and bottom padding size.
### horizontalPadding
- type: TableListItemPadding
- description: Adjusts the left and right padding size.
### checkbox
- type: boolean
- description: Defines whether the component is selectable by a checkbox.
### checkboxDisabled
- type: boolean
- description: Disables the visible checkbox
### checked
- type: boolean
- description: Defines if component is selected
### focused
- type: boolean
- description: Forces focus on drag handle
### onBlur
- type: (e: React.FocusEvent) =&gt; void
- description: Defines a callback when item loses its focus
### onFocus
- type: (e: React.FocusEvent) =&gt; void
- description: Defines a callback when item gains focus
### onKeyUp
- type: (e: React.KeyboardEvent) =&gt; void
- description: Defines a callback when the item is focused, and a key is pressed and released. Used for NestableList solutions controlled with a keyboard.
### onCheckboxChange
- type: React.ChangeEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback when checkbox is clicked
### draggable
- type: boolean
- description: Makes drag handle visible.
### dragging
- type: boolean
- description: Visually indicates that component is being dragged
### dragDisabled
- type: boolean
- description: Disables the visible drag handle
### showDragHandleOnHover
- type: boolean
- description: Enables showing drag handle only on hover.
### showDivider
- type: boolean
- description: Enables a divider at the bottom of the list item.
### dragHandleProps
- type: Partial&lt;DragHandleProps&gt;
- description: Extra props to pass to the `&lt;DragHandle /&gt;` element
### checkboxTooltipContent
- type: React.ReactNode
- description: Defines a message to be displayed in a tooltip. Tooltip is displayed on a checkbox hover.
### checkboxTooltipProps
- type: TooltipCommonProps
- description: Tooltip props (when hovering over the checkbox)
### border
- type: boolean
- description: Adds a border around the component.
### showSelectionBorder
- type: boolean
- description: When item is with checkbox and is selected, adds a border on the left side of the component.
### dragHandleSize
- type: DragHandleSizes
- description: Changes the size of the DragHandle.
### hideDragHandle
- type: boolean
- description: Hides drag handle visually.
### expandable
- type: boolean
- description: Adds functionality to expand the list item.
### expandDisabled
- type: boolean
- description: Disables the visible expand handle
### reserveExpandHandleSpace
- type: boolean
- description: Hides the expand handle without changing the layout. Used for aligning items when there&#39;s a mix of expandable and non-expandable items at the same level.
### reserveDragHandleSpace
- type: boolean
- description: Hides the drag handle without changing the layout. Used for aligning items when there&#39;s a mix of draggable and non-draggable items at the same level.
### onClickExpand
- type: React.MouseEventHandler
- description: Defines a callback when caret handle is clicked
### expanded
- type: boolean
- description: Defines whether the list component is expanded/collapsed.
### onMouseEnter
- type: React.MouseEventHandler
- description: Defines a callback function which is called on `onMouseEnter` event on the list item
### onMouseLeave
- type: React.MouseEventHandler
- description: Defines a callback function which is called on `onMouseLeave` event on the list item
### selectable
- type: boolean
- description: Defines whether the root element of list component is selectable.
### ariaLabel
- type: string
- description: Provides context for screen readers when has a root element of list component in selectable state
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


