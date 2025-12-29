
### dataHook
- type: string
- description: applied as data-hook HTML attribute that can be used to create driver in testing
### title
- type: node
- description: Title of the modal
### subtitle
- type: node
- description: Fixed text displayed above the list
### onOk
- type: func
- description: OK button callback, called with the currently selected item
### onClose
- type: func
- description: X button callback
### onCancel
- type: func
- description: Cancel button callback
### dataSource
- type: func
- description: paging function that should have a signature of
```typescript
(searchQuery: string, offset: number, limit: number) =&gt;
Promise&lt;{
 items: Array&lt;{
   id: number | string,
   title: node,
   subtitle?: string,
   extraText?: string,
   extraNode?: node,
   disabled?: boolean // show item as disabled, dont count it in &#34;select all&#34;, exclude from `onOk`
   selected?: boolean // force item as selected
   image?: node
   subtitleNode?: node,
   belowNode?: node,
   showBelowNodeOnSelect?: boolean,
 }&gt;,
 totalCount: number
}&gt;
```
`offset` - next requested item&#39;s index&lt;br&gt;
`limit` - number of items requested&lt;br&gt;
`totalCount` - total number of items that suffice the current search query
### cancelButtonText
- type: string
- description: Cancel button&#39;s text
### okButtonText
- type: string
- description: OK button&#39;s text
### imageSize
- type: enum
- description: Image icon size
### imageShape
- type: custom
- description: Image icon shape, `rectangular` or `circle`.&lt;br&gt;
NOTE: `circle` is not compatible with `imageSize` of `portrait` or `cinema`
### searchPlaceholder
- type: string
- description: Placeholder text of the search input
### emptyState
- type: node
- description: Component/element that will be rendered when there is nothing to display,
i.e. empty `{items:[], totalCount: 0}` was returned on the first call to `dataSource`
### noResultsFoundStateFactory
- type: func
- description: Function that will get the current `searchQuery` and should return the component/element
that will be rendered when there are no items that suffice the entered search query
### itemsPerPage
- type: number
- description: Number of items loaded each time the user scrolls down
### withSearch
- type: bool
- description: Whether to display the search input or not
### searchDebounceMs
- type: number
- description: Search debounce in milliseconds
### height
- type: string
- description: Height CSS property, sets the height of the modal
### maxHeight
- type: string
- description: Max-height CSS property, sets the maximum height of the modal.
### multiple
- type: bool
- description: display checkbox and allow multi selection
### selectAllText
- type: string
- description: string to be displayed in footer when `multiple` prop is used and no items are selected
### deselectAllText
- type: string
- description: string to be displayed in footer when `multiple` prop is used and some or all items ar selected
### disableConfirmation
- type: bool
- description: to disable confirm button
### onSelect
- type: func
- description: callback that triggers on select and return selected item object
### sideActions
- type: node
- description: Used to display some side component in the footer.
Will override element select all in the footer when multiple=true


