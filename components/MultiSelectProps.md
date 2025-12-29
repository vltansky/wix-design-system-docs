
### ariaControls
- type: string
- description: Associate a control with the regions that it controls.
### ariaDescribedby
- type: string
- description: Associate a region with its descriptions. Similar to aria-controls but instead associating descriptions to the region and description identifiers are separated with a space.
### ariaLabel
- type: string
- description: Define a string that labels the current element in case where a text label is not visible on the screen.
### border
- type: enum
- description: Control the border style of input
### closeOnSelect
- type: bool
- description: Closes list once list item is selected
### popoverProps
- type: shape
- description: Allows to pass all common popover props.
### predicate
- type: func
- description: Callback predicate for the filtering options function
### tags
- type: array
- description: Optional list of strings that are selected suggestions.
### maxNumRows
- type: number
- description: Max number of visible lines
### delimiters
- type: array
- description: Delimiters that will trigger a Submit action (call to onTagsAdded). By default it is [,] but also enter and tab keys work.
### emptyStateMessage
- type: node
- description: Defines a message to be displayed instead of options when no options exist or no options pass the predicate filter function.
### hasMore
- type: bool
- description: Specifies whether there are more items to be loaded.
### infiniteScroll
- type: bool
- description: Specifies whether lazy loading of the dropdown layout items is enabled.
### loadMore
- type: func
- description: Defines a callback function which is called on a request to render more list items.
### mode
- type: string
- description: Passing &#39;select&#39; will render a readOnly input with menuArrow suffix *
### status
- type: enum
- description: The status of the Multiselect
### statusMessage
- type: string
- description: Text to be shown in the status icon tooltip
### onReorder
- type: func
- description: When this callback function is set, tags can be reordered. The expected callback signature is `onReorder({addedIndex: number, removedIndex: number}) =&gt; void` *
### onManuallyInput
- type: func
- description: A callback which is called when the user enters something in the input and then confirms the input with some action like Enter key or Tab.
### onOptionsShow
- type: func
- description: A callback which is called when options dropdown is shown
### onOptionsHide
- type: func
- description: A callback which is called when options dropdown is hidden
### onSelect
- type: func
- description: A callback which is called when the user selects an option from the list. `onSelect(option: Option): void` - Option is the original option from the provided options prop.
### customSuffix
- type: node
- description: A node to display as input suffix when the dropdown is closed
### customPrefix
- type: node
- description: A node to display as input prefix when the dropdown is closed
### disabled
- type: bool
- description: When set to true this component is disabled
### clearOnBlur
- type: bool
- description: When set to false, the input will not be cleared on blur
### acceptOnBlur
- type: bool
- description: When set to true, the input will be submitted as new tag on blur
### onRemoveTag
- type: func
- description: A callback function to be called when a tag should be removed. The expected callback signature is `onRemoveTag(tagId: number | string) =&gt; void.`
### readOnly
- type: bool
- description: Specifies whether input should be read only
### fixedFooter
- type: node
- description: Adds a fixed footer container at the bottom of options list.
### markedOption
- type: union
- description: Sets the default option focus behavior:
 - `false` - no initially focused list item
 - `true` - focus first selectable option
 - any `number/string` specify the id of an option to be focused
### customInput
- type: any
- description: No description


