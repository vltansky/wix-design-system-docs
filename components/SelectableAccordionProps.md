
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### type
- type: enum
- description: A type can be ether radio, checkbox, or toggle, which will effect the way an accordion item is selected
### items
- type: arrayOf
- description: An array of Accordion items:
- `title`: A title of the item
- `subtitle`: An optional second row of the header
- `content`: A content of the item
- `initiallyOpen`: Whether the item is initially open
- `open`: Whether the item is open
- `disabled`: Whether the item is disabled
- `onClick`: A callback which is invoked when item&#39;s selection is changed
### verticalPadding
- type: enum
- description: Extra space on top and bottom of selectable accordion item
### onSelectionChanged
- type: func
- description: A callback which is invoked every time the selection is changed


