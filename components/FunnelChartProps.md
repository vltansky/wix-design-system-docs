
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### data
- type: arrayOf
- description: Array of Funnel Chart items
* `value` - Item&#39;s value.
* `label` - Short label under the value.
* `displayValue` - Item&#39;s value send by the user.
### fullHeight
- type: bool
- description: When provided, allows bars to take full height
### hideDifferenceBadge
- type: bool
- description: A flag that controls the appearance of the calculated percentage badge
### differenceBadgeSkin
- type: enum
- description: When provided, changes badge skin
### differenceStepSkin
- type: func
- description: Returns the step skin by current index, badge&#39;s percentage and raw values
##### Signature:
`({currentIndex: number, difference: string, differenceValue: number}) =&gt; &#39;standard&#39; | &#39;success&#39;`
### differenceBadgeProps
- type: func
- description: Returns the badge props by current index, badge&#39;s percentage and raw values
##### Signature:
`({currentIndex: number, difference: string, differenceValue: number}) =&gt; FunnelBadgeCommonProps`
### differenceBadgeTooltipContent
- type: func
- description: Returns the tooltip props by current index, badge&#39;s percentage and raw values
##### Signature:
`({currentIndex: number, difference: string, differenceValue: number}) =&gt; React.ReactNode`
### differenceBadgeTooltipProps
- type: func
- description: Returns the tooltip props by current index, badge&#39;s percentage and raw values
##### Signature:
`({currentIndex: number, difference: string, differenceValue: number}) =&gt; TooltipCommonProps`
### onDifferenceBadgeTooltipShow
- type: func
- description: Callback on tooltip content show event by current index, badge&#39;s percentage and raw values
##### Signature:
`({currentIndex: number, difference: string, differenceValue: number}) =&gt; void`


