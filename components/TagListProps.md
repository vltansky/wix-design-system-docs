
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests.
### tags
- type: Omit&lt;TagProps, &#34;size&#34; | &#34;onRemove&#34;&gt;[]
- description: Lists all component’s tags and its properties.
### size
- type: TagListSize
- description: Sets the size of a component.
### onTagRemove
- type: (id: string) =&gt; void
- description: Defines a callback function that passes an `id` property as a parameter when removing a tag.
### initiallyExpanded
- type: boolean
- description: Defines whether the list is:
- initially expanded (shows all tags)
- or collapsed (shows tags up to the max visible number)
### maxVisibleTags
- type: number
- description: Sets an amount of tags to show before expanding.
### actionButton
- type: TagListActionButtonProps
- description: Defines the label of an action button and its onClick function.
### toggleMoreButton
- type: (amountOfHiddenTags: number, isExpanded: boolean) =&gt; ToggleMoreButtonProps
- description: Defines a function which provides props for the ToggleMoreButton.
##### toggleMoreButton signature is:
`function(amountOfHiddenTags: number, isExpanded: boolean) =&gt; ToggleMoreButtonProps`

##### ToggleMoreButtonProps:
* `label`: string
* `tooltipContent`: node
* `tooltipProps`: TooltipCommonProps


