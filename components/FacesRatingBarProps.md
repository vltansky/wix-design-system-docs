
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### readOnly
- type: bool
- description: Specifies whether the rating bar is in read only mode
### descriptionValues
- type: arrayOf
- description: Specifies the rate value descriptions’ texts. The array length must match the maxValue prop number (5 by default).
### value
- type: enum
- description: Specifies the selected rate. `0` indicates undefined rating. `readOnly` mode value cannot be `0`.
### maxValue
- type: enum
- description: Specifies the maximum rate value.
### onChange
- type: func
- description: Defines a handler that is called whenever a rating changes.
##### Signature:
function(rating: number) =&gt; void
* `rating`: 1 | 2 | 3 | 4 | 5


