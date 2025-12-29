
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used to create driver in testing
### size
- type: enum
- description: Displayed value size (default: large)
### alignItems
- type: enum
- description: Alignment of inner items (default: center)
### isLoading
- type: bool
- description: Show loader instead of values for all statistic items (default: undefined)
### items
- type: arrayOf
- description: Array of statistic items
 * `value` - Value of the statistic. Displayed as big text in the first row.
 * `valueInShort` - Short version of value. Will be applied when there is no space for long value. If not specified, part of the value will be hidden with ellipsis
 * `description` - Description of the statistic. Displayed in the second row.
 * `descriptionInfo` - More info about the description. Displayed as an info icon with this text inside a tooltip
 * `percentage` - Change in percents. Positive number - arrow up, negative - arrow down.
 * `invertedPercentage` - When set to true renders positive percentage in red and negative in green.
 * `onClick` - Callback to be executed on click (also on Enter/Space key press)
 * `isLoading` - Shows a loader instead of value.
 * `children` - Node to render on bottom of section.


