
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### dataSource
- type: func
- description: Returns data source for the list described in a following structure:

```typescript
(searchQuery: string, offset: number, limit: number) =&gt;
Promise&lt;{
 items: Array&lt;{
   id: number | string, // sets the unique item ID (required)
   title: node, defines // an item’s title (required)
   subtitle?: string, // defines an item’s subtitle
   extraText?: string, // contains any text at the end of an item
   extraNode?: node, // contains any component at the end of an item
   disabled?: boolean, // controls if an item is disabled for selection or not
   selected?: boolean, // sets an item as selected
   indeterminate?: boolean, // sets an item as indeterminate
   image?: node, // contains &lt;Image/&gt; or other component to illustrate an item
   subtitleNode?: node, // contains any component below an item’s subtitle
   belowNode?: node, // contains any component below the item, to be shown after an item is selected
   showBelowNodeOnSelect?: boolean, // allows to show belowNode content when an item is selected
 }&gt;,
 offset: number, // specifies the item index in the data source to start fetching from&lt;br&gt;
 limit: number, // sets a max amount of items to load from the data source&lt;br&gt;
 totalCount: number, // sets a max amount of items to load from the data source on user’s search query
}&gt;
```
### size
- type: enum
- description: Controls the size of component paddings and list items
### imageSize
- type: enum
- description: Controls the size of item images. Note: `portrait` and `cinema` sizes are only compatible with `rectangular` image shape.
### imageShape
- type: enum
- description: Controls the shape of item images
### showDivider
- type: bool
- description: Use to display a divider between items
### searchPlaceholder
- type: string
- description: Defines placeholder value shown in the search input
### emptyState
- type: node
- description: Contains a component which is shown when there are no items to display in the selector list.

i.e. empty `{items:[], totalCount: 0}` was returned on the first call to `dataSource`. Render `&lt;EmptyState/&gt;` component in `section` skin for this purpose.
### renderNoResults
- type: func
- description: Defines a function that gets the current `searchQuery` and returns the component that is shown when no items are found. Render `&lt;EmptyState /&gt;` component in `section` skin for this purpose.
### itemsPerPage
- type: number
- description: Sets the number of items to be loaded each time users scroll down to the end of the list
### withSearch
- type: bool
- description: Controls whether to display the search input
### searchDebounceMs
- type: number
- description: Sets search debounce in milliseconds
### height
- type: string
- description: Sets the height of the component in % or px
### maxHeight
- type: string
- description: Sets the maximum height of the component in % or px
### multiple
- type: bool
- description: Renders checkboxes instead of radio buttons and allows users to select multiple items
### autoFocus
- type: bool
- description: Focus the element on mount (standard React input autoFocus).
### onSelect
- type: func
- description: Defines callback that triggers on select and return selected item object
### selectAllText
- type: string
- description: Sets the label for the checkbox which allows to select all items
### deselectAllText
- type: string
- description: Sets the label for the checkbox which allows to deselect all selected items
### initialAmountToLoad
- type: number
- description: Sets the number of items to load on initial render or after search. If not defined, it will be equal to `itemsPerPage` value.
### subtitle
- type: node
- description: Contains text or other component in a fixed position at the top of the list
### renderToggleAllCheckbox
- type: func
- description: Displays a checkbox which allows to select and deselect all items at once


