
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### activeId
- type: string | number
- description: A selected tab id
### showDivider
- type: boolean
- description: If true, places a divider on bottom
### hasDivider
- type: boolean
- description: No description
### items
- type: Item[]
- description: An array of tabs
### minWidth
- type: string | number
- description: A minimum width of the container
### alignment
- type: TabsAlignment
- description: Control text alignment in tab item
### type
- type: TabsType
- description: One of: &#39;&#39;, compact, compactSide, uniformSide, uniformFull
### size
- type: &#34;small&#34; | &#34;medium&#34;
- description: One of: medium, small
### sideContent
- type: ReactNode
- description: Can be either string or renderable node
### width
- type: string | number
- description: A specific width of a tab (only for uniformSide type)
### onClick
- type: (item: Item) =&gt; void
- description: Click event handler
### scrollOnOverflow
- type: boolean
- description: Wraps overflowing content within a scrollable container.
### horizontalScrollProps
- type: HorizontalScrollCommonProps
- description: Allows to pass all common horizontal scroll props.
### horizontalPadding
- type: boolean
- description: If true, adds horizontal padding to the tabs container


