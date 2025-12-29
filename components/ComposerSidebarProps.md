
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### labelPlacement
- type: enum
- description: Controls the items’ label placement
### labelTooltipProps
- type: object
- description: Controls the items’ label tooltip when labelPlacement is set to tooltip
### width
- type: union
- description: Sets the width of the container
### size
- type: enum
- description: Sets the size of the items
### selectedId
- type: union
- description: Defines which item is currently selected
### ellipsis
- type: bool
- description: Controls the ellipsis of the item label
### items
- type: arrayOf
- description: Defines an array of items (buttons and labels) to show on the sidebar:
- `label`: text string next to a button
- `icon`: icon shown in the toggle button
- `disabled`: disables the item
- `onClick`: defines what happens when the item is clicked on
- `sectionTitle`: defines a section under which each item is placed
### onClick
- type: func
- description: Defines a default on click handler for items


