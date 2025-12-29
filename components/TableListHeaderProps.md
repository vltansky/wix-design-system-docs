
### dataHook
- type: string
- description: No description
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### options
- type: arrayOf
- description: `width` supports px/%/fr
`sortable`: Sets whether this field is sortable. If `true` clicking the header will call `onSortChange`
`sortDescending`: Sets what sort icon to display in the column header. `true` will show an up arrow, `false` will show a down arrow, `undefined&#39; will show no icon
`infoTooltipProps`: Props object for column header&#39;s [tooltip](/?path=/story/components-api-components--tooltip). Note: `dataHook`, `moveBy` and `children` will not be passed to tooltip.
### checkboxState
- type: enum
- description: State of Checkbox rendered at first column. &#39;hidden&#39; to not render it
### onCheckboxChange
- type: func
- description: Called when checkbox is clicked
### onSortChange
- type: func
- description: A callback function called on each column title click. Signature `onSortChange(colNum, nativeEvent)`


