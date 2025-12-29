
### items
- type: arrayOf
- description: Describes each breadcrumbs item:
- `id` (required) - gives an item numeric identifier
- `value` (required) - sets the item label to be shown on breadcrumbs
- `link` - stores a link which user is directed to after clicking on an item
- `customElement` - contains and renders a custom component or `&lt;a&gt;` link instead of an item value
- `disabled` - disables an item
### onClick
- type: func
- description: Defines a function which is called when a user clicks on an item
### activeId
- type: union
- description: Defines which breadcrumbs item is currently active
### size
- type: enum
- description: Controls the component size
### itemMaxWidth
- type: union
- description: Sets the maximum width of each item value in px. Longer items get truncated with ellipsis.
### skin
- type: enum
- description: Controls the component appearance
### theme
- type: enum
- description: No description
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests


