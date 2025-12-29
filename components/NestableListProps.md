
### actions
- type: custom
- description: Actions that will be rendered for on the root depth level
### withBottomBorder
- type: bool
- description: Adds a bottom border (divider) to the last item.
### readOnly
- type: bool
- description: Prevents the list from being reordered by removing the dragging grip icons.
### addItemLabel
- type: string
- description: Adds a button to create a new item (to the Root or a child to the existing item).
### dragHandleSize
- type: enum
- description: Size of the drag handle
### showDragHandleOnHover
- type: bool
- description: Shows the drag handle only on hover.
### onAddItem
- type: func
- description: Triggers function when the &#34;Add new ...&#34; button is clicked.
### onChange
- type: func
- description: Triggers function when the item’s order or nesting position is changed.
### maxDepth
- type: number
- description: Defines a maximum depth (number of levels) for the list.
### preventChangeDepth
- type: bool
- description: Allows dragging and dropping an item only on its own depth (inside the same level).
### preventChangeParent
- type: bool
- description: Allows dragging and dropping an item only on its own parent.
### enforcePinnedOrder
- type: bool
- description: Allows dragging and dropping an item only on its pin section.
### items
- type: arrayOf
- description: Defines each Nestable List item individually, using the following props:
* __id__ - specifies an item’s ID.
* __addItemLabel__ - creates the “Add new ...” button with a given label at the bottom of the item.
* __isCollapsed__ - bool prop, defines whether to render the item’s children.
* __children__ - defines an item’s children.
* __draggable__ - bool prop, turns on / off dragging ability for an item.
* __hideDragHandle__ - bool prop, turns on / off drag handle for an item.
* All &lt;a href=&#34;https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-lists-table--tablelistitem&#34; target=&#34;_blank&#34;&gt;`&lt;TableListItem/&gt;`&lt;/a&gt; props can be used to format item’s style and content.
### dataHook
- type: string
- description: Can be applied in the tests as a data-hook HTML attribute.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### zIndex
- type: number
- description: Defines the zIndex of the draggable layer
### dividers
- type: bool
- description: Sets the divider visibility
### indentSize
- type: enum
- description: Sets the indent size
### hierarchyIndicator
- type: bool
- description: Displays hierarchyIndicator from the parent to children
### onDragStart
- type: func
- description: Triggers function when the drag of item starts.
### onDragEnd
- type: func
- description: Triggers function when the drag of item ends.


