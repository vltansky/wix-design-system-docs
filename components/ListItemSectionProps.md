
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### type
- type: ListItemSectionTypes
- description: A list item section can be
* `title` - Acts as a title for following list items.
* `subheader` - Acts as separator between list items for differentiation.
* `whitespace` - Adds some padding between list items.
* `divider` - Same as whitespace, but with a line.
### title
- type: ReactNode
- description: Text of the list item
### suffix
- type: ReactNode
- description: Suffix node. Renders TextButton for a string otherwise the node itself.
### ellipsis
- type: boolean
- description: If true, long text won&#39;t break into more than one line and will be terminated with an ellipsis
### onClick
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: A callback function called when suffix is clicked


