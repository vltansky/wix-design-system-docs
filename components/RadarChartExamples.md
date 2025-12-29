
## Feature Examples


### Fill
- description: Control the chart color by specifying color for each data point. It accepts the following color variables: `A1` (default), `A2`, `A3`, `A4`, `A5`, `A6`.<br /><br />
        If data points have different colors, chart will be filled with a linear gradient that is defined from the first color to the last color in the dots list.
- example: 
```jsx 

```

### Width
- description: Control the dimensions of a chart with `width` prop. Changing the width will affect component height as well - it grows in 1:1 ratio.<br /><br />
        Minimum width of a chart is 150px.
- example: 
```jsx 

```

### Data points
- description: Define from 3 to 10 data points to display in a chart. Available properties for each point:<br/>
      &emsp;- `value` - use to define a number that represents value in a chart<br/>
      &emsp;- `label` - use to specify a label that represents value around the chart<br/>
      &emsp;- `color` - use to specify data point color<br/>
      &emsp;- `tooltipContent` - use to define a message visible in a tooltip on a data point hover over.
- example: 
```jsx 

```

### Label distance
- description: Control value label distance from a chart with `labelDistance` prop. It support two values:<br/>
      &emsp;- `medium` - use it to increase the distance for better visual balance in larger charts<br/>
      &emsp;- `small` (default) - use in all common cases
- example: 
```jsx 

```

### Scale
- description: Define any number of scale circles in the chart with a `scale` array.
- example: 
```jsx 

```

### Disabled
- description: Disable all chart interactions with `disabled` prop. Use this as an empty state / content placeholder when there’s no data yet.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Empty state
- description: Use radar char in a disabled state as an empty state when there’s not enough data to create a chart yet. It will help to let users know upfront a possible benefit of analytics you’re offering.
- example: 
```jsx 

```


