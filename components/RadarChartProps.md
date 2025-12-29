
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in tests
### data
- type: arrayOf
- description: Defines data points that construct spider web-like charts. Available properties for array items:&lt;br /&gt;
    &amp;emsp;- `value` - a number that represents value in chart&lt;br /&gt;
    &amp;emsp;- `label` - a label that represents value description around the chart&lt;br /&gt;
    &amp;emsp;- `color` - data point color.&lt;br /&gt;
    &amp;emsp;- `tooltipContent` - data point tooltip content
### scale
- type: arrayOf
- description: Defines a number of scale circles in the chart. Available properties for each scale:&lt;br /&gt;
      &amp;emsp;- `value` - a number representing scale&lt;br /&gt;
      &amp;emsp;- `suffix` - a string that represents value meaning (i.e. % or $)
### disabled
- type: bool
- description: Specifies whether graph is disabled
### width
- type: number
- description: Controls the width of a graph. Minimum width is 150 pixels.
### labelDistance
- type: number
- description: Controls label distance from a chart
### hoverIndex
- type: number
- description: Defines the index of a data point in hover state
### labelWidth
- type: number
- description: Defines maximum width of data labels
### onDataPointHover
- type: func
- description: Defines a callback function which is called every time user hovers over a data point. Includes all data point data as first argument and index as second.


