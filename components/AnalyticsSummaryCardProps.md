
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### title
- type: string
- description: Text for the title
### titleTooltip
- type: string
- description: Text for title tooltip
### value
- type: string
- description: Text value
### valueTooltip
- type: string
- description: Text for value tooltip
### trend
- type: number
- description: A number to be displayed as the trend, a positive number will be green with an arrow facing up and a negative number will be red with an arrow facing down
### invertedTrend
- type: boolean
- description: Invert color and arrow direction of Trend.
### isTrendVisible
- type: boolean
- description: Show/Hide trend
### isLoading
- type: boolean
- description: Whether component is loading
### ctaButton
- type: ReactNode
- description: CTA button React Node
### onCTAClick
- type: (event: MouseEvent&lt;HTMLDivElement, MouseEvent&gt;) =&gt; void
- description: Fires when CTA button is clicked
### alwaysShowCTA
- type: boolean
- description: Always show CTA button
### onClick
- type: (event: MouseEvent&lt;HTMLDivElement, MouseEvent&gt;) =&gt; void
- description: Card would be clickable
### onChartHover
- type: (index: number) =&gt; void
- description: Fires when chart is hovered
### chartHighlightedStartingIndex
- type: number
- description: Indicates the starting index of the highlighted area of the chart
### chartWidth
- type: number
- description: Chart width
### chartData
- type: { label: Date; value: number; }[]
- description: Chart data
### getChartTooltipContent
- type: (index: number) =&gt; ReactNode
- description: Chart tooltip content
### chartColorHex
- type: string
- description: Sets the color of the chart
### chartAnimationDuration
- type: number
- description: Chart animation duration
### footer
- type: ReactNode
- description: Footer - node
### border
- type: boolean
- description: Adds a border and corner radius
### horizontalPadding
- type: AnalyticsSummaryCardHorizontalPadding
- description: Controls spacing size from left and right sides
### focusableOnFocus
- type: React.FocusEventHandler&lt;E&gt;
- description: No description
### focusableOnBlur
- type: React.FocusEventHandler&lt;E&gt;
- description: No description
### ref
- type: React.RefObject&lt;E&gt;
- description: No description


