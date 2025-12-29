
### icon
- type: ReactNode
- description: Icon of the list item
### label
- type: string
- description: Label of the list item
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### selected
- type: boolean
- description: If true, the item is selected
### highlighted
- type: boolean
- description: If true, the item is highlighted
### disabled
- type: boolean
- description: If true, the item is disabled
### showTooltip
- type: boolean
- description: If true, the tooltip will be shown on hover
### tooltipProps
- type: Omit&lt;TooltipProps, &#34;disabled&#34; | &#34;children&#34; | &#34;content&#34;&gt;
- description: Allows to pass all common tooltip props.
### onClick
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function triggered when list item is clicked


