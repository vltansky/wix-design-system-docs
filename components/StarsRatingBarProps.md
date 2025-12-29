
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### size
- type: &#34;tiny&#34; | &#34;small&#34; | &#34;medium&#34; | &#34;large&#34;
- description: Controls the size of the star rating bar. Interactive mode can be `large` or `medium`. The default value for the read only mode is `medium`.
### readOnly
- type: boolean
- description: Specifies whether the rating bar is in read-only mode.
### labelValues
- type: string[]
- description: Specifies the rate input value labels.
### descriptionValues
- type: string[]
- description: Specifies the rate caption value labels. Array must contain all 5 strings to display the rating labels.
### value
- type: 0 | 1 | 2 | 3 | 4 | 5
- description: Specifies the selected rate. 0 indicates an undefined rating.
### onChange
- type: (rating: number) =&gt; void
- description: Defines a handler that is called whenever rating changes.
##### Signature:
function(rating: number) =&gt; void
* * `rating`: 1 | 2 | 3 | 4 | 5
### name
- type: string
- description: Specifies radio group name.
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


