
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### checkbox
- type: boolean
- description: If true, a checkbox will be shown.
### prefix
- type: ReactNode
- description: Any prefix.
### title
- type: ReactNode
- description: Title of the list item.
### subtitle
- type: ReactNode
- description: Text of the list item subtitle.
### suffix
- type: ReactNode
- description: Any suffix.
### selected
- type: boolean
- description: If true, the item is selected.
### highlighted
- type: boolean
- description: If true, the item is highlighted, if false - highlighted styles are not automatically applied on item hover.
### disabled
- type: boolean
- description: If true, the item is disabled.
### disabledDescription
- type: string
- description: Tooltip description if item is disabled.
### tooltipProps
- type: TooltipProps
- description: Allows to pass all common tooltip props.
### onClick
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function triggered when list item is clicked.
### size
- type: ListItemSelectSizes
- description: Changing text size.
### ellipsis
- type: boolean
- description: If true, long text won&#39;t break into more than one line and will be terminated with an ellipsis.
### titleMaxLines
- type: number
- description: Maximum number of title lines before truncating with an ellipsis.
### subtitleMaxLines
- type: number
- description: Maximum number of subtitle lines before truncating with an ellipsis.


