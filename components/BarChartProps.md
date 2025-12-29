
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used to create driver in testing
### items
- type: arrayOf
- description: Array of items
 * `value` - This prop is used for sorting bars. Displayed as big text on a bar, when there is no caption prop.
 * `label` -  Displayed as big text on a bar.
 * `labelShort` - Is shown instead of a `label` when there is not enough space.
 * `description` - short label under the bar.
 * `descriptionInfo` - long description.
### total
- type: number
- description: Used to calculate space for bars inside a widget. Should be specified if the actual total is different from the sum of values of all items
### onDescriptionInfoShown
- type: func
- description: Callback called every time when descriptionInfo tooltip is shown


