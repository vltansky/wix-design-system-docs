
### children
- type: any
- description: Accept any wrapper component as a child element. It must eventually include &lt;Table.Content/&gt;.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### onSelectionChanged
- type: func
- description: Defines a callback function which is called when selection happens. &lt;br /&gt;
There are 3 types of selections:
   * `ALL` - bulk selection checkbox has been triggered to select all items
   * `SINGLE_TOGGLE` - a checkbox to select one item from the list has been triggered. The change object will also include an `id` prop with the unique item identifier and a `value` prop with the new boolean selection state of the item.
   * `NONE` - bulk selection has been triggered to unselect all items.
### onSelectionStarted
- type: func
- description: Called when item selection triggered but not changed yet.
### showSelection
- type: bool
- description: Displays selection checkbox as a first column in each row. To hide the selection checkbox from a specific row, set its `row.unselectable` value to true in the data array.
### hideBulkSelectionCheckbox
- type: bool
- description: Hides bulk selection checkbox in the table titlebar
### bulkSelectionCheckboxRef
- type: union
- description: A ref to the bulk selection checkbox in the table titlebar
### selectedIds
- type: union
- description: Defines an array of selected rows
### selectionDisabled
- type: union
- description: Specifies whether table row selection is restricted at a given moment. Can be defined as:
   * `bool` disables selection for all table rows
   * `function` that will be called for each row to check whether to disable selection or not depending on specified condition
### deselectRowsByDefault
- type: bool
- description: Controls bulk selection checkbox behaviour in indeterminate state. By default, first click on indeterminate state selects all items in the table. If set to `true`, first click will deselect all items instead.
### withWrapper
- type: bool
- description: When false then Table would not create a `&lt;div/&gt;` wrapper around it&#39;s children.
 Useful when using `&lt;Table/&gt;` to wrap a `&lt;Page/&gt;` component, in that case we use the `&lt;Table/&gt;` only as a context provider and it does not render anything to the DOM by itself.
### onSortClick
- type: func
- description: Defines a callback function which is called on column title click
### allowMultiDetailsExpansion
- type: bool
- description: Allows to expand multiple row details at once
### data
- type: array
- description: Defines any amount of data to be displayed in the table. Properties for each entry:&lt;br&gt;
  * `id`: should be provided and will be used as a React key internally
  * `unselectable`: specifies whether a row can be selected by a user when `showSelection` is enabled for the whole table
  * `checkboxTooltipContent`: defines tooltip content to show when user hovers selection checkbox
  * any number of records with unique identifiers for column rendering
### columns
- type: arrayOf
- description: Configures table columns. Required properties for each column:&lt;br /&gt;
   * `title`: specifies a text string or an element to display in the table titlebar
   * `render`: defines a function which will be called to display this row value for this column&lt;br&gt;

 Optional properties for each column:
   * `onCellClick`: defines a  callback function which is called each time a cell in this column is clicked. Signature: `onCellClick(column, rowData, rowNum, event)`
   * `sortable`: specifies whether field is sortable. If true clicking the header will call `onSortClick`.
   * `sortDescending`: specifies what sort icon to display in the column header. `true` shows an up arrow, `false` shows a down arrow, `undefined&#39; shows no icon.
   * `infoTooltipProps`: controls info [tooltip](/?path=/story/components-overlays--tooltip) appearance in titlebar. Note: `dataHook`, `moveBy` and `children` will not be passed to tooltip.
   * `style`: applies a custom CSS class to the component’s root element
   * `align`: controls the alignment of the column content
   * `width`: sets the width of a column. No value means column will try to contain its children, if possible.
   * `important`: increases text size of this column data across all rows, sets font color to D10
   * `stickyActionCell`: specifies whether `&lt;TableActionCell/&gt;` controls are fixed to the right side of the table
   * `resizeProps`: configures column resize behavior. When provided with an `id`, enables resizing for this column. Use `disabled: true` to show a disabled handle, or `disabled: true, hideDisabledResizeHandle: true` to hide the handle completely.
### dynamicRowClass
- type: func
- description: Defines a function that gets row data and returns a class(es) to apply to that specific row
### isRowHighlight
- type: func
- description: Defines a function that gets row data and returns boolean value specifying whether row is highlighted or not
### isRowActive
- type: func
- description: Defines a function that gets row data and returns boolean value specifying whether row is active or not
### hasMore
- type: bool
- description: Indicates whether there is additional data to load from external sources though `loadMore` function. When set to true `loadMore` property will be called until false value is received.
### initialLoad
- type: bool
- description: Invokes `loadMore` on the initial table render
### id
- type: string
- description: Assigns an unique identifier for the table
### infiniteScroll
- type: bool
- description: Renders data gradually as user scrolls down the list
### totalSelectableCount
- type: number
- description: Specifies the total number of selectable items in the table (including items not loaded yet).
When ‘Select all’ is triggered in infinite scroll tables, newly loaded items will be selected automatically. In this case, `SelectionContext` holds not-selected items rather than the selected ones.
SelectionContext.infiniteBulkSelected is true and SelectionContext.selectedCount is the value of totalSelectableCount minus the count of unselected items.
### itemsPerPage
- type: number
- description: Determines the number of rows to rendered on each load of an infinite scroll table
### loader
- type: node
- description: Pass a loader to show when loading more items in infinite scroll table. Most commonly pass &lt;Loader/&gt; or &lt;Text/&gt; components.
### loadMore
- type: func
- description: Defines a callback function which is called each time user request to load more items
### onRowClick
- type: func
- description: Defines a callback function which is called each time user clicks on the row. This prop is required to enable row hover effect.
### onMouseEnterRow
- type: func
- description: Defines a callback function which is called each time mouse enters the row
### onMouseLeaveRow
- type: func
- description: Defines a callback function which is called each time mouse leaves the row
### useWindow
- type: bool
- description: Add scroll listeners to the window, or else, the component&#39;s parentNode.
### scrollElement
- type: object
- description: Adds scroll listeners to specified DOM object
### rowVerticalPadding
- type: enum
- description: Controls the amount of white space above and below row content:
- `large`: 24px
- `medium`: 18px
- `small`: with the feature toggle: 15px, without the feature toggle: 12px
- `tiny`: 12px
- `xTiny`: 6px
- `xxTiny`: 3px
### rowDetails
- type: func
- description: Defines a function that returns a component to render in the expanded row content area
### removeRowDetailsPadding
- type: bool
- description: Removes paddings from an expanded row content area
### rowDataHook
- type: union
- description: Applies a data-hook HTML attribute or a function that calculates the data-hook for each row on the table
### rowClass
- type: string
- description: A class to apply to all table body rows
### showHeaderWhenEmpty
- type: bool
- description: Specifies whether to show table title bar when there’s no data in the table
### showLastRowDivider
- type: bool
- description: Specifies whether last row in the table should have a bottom divider
### isApplyColumnWidthStyle
- type: bool
- description: A flag specifying weather to apply column width style to table cells
### virtualized
- type: bool
- description: ++EXPERIMENTAL++ Virtualize the table scrolling for long list items
### virtualizedTableHeight
- type: number
- description: ++EXPERIMENTAL++ Controls virtualized table height
### virtualizedLineHeight
- type: number
- description: ++EXPERIMENTAL++ Set virtualized table row height
### virtualizedListRef
- type: any
- description: ++EXPERIMENTAL++ Set ref on virtualized list containing table rows
### width
- type: string
- description: Defines the width of the table in percentages or pixels.
### skin
- type: enum
- description: Controls the appearance of a table title bar
### horizontalScroll
- type: bool
- description: Specifies whether table content can exceed the width of the table. If enabled, table can be scrolled horizontally.
### stickyColumns
- type: number
- description: Specifies the number of columns to stick to the left side in tables that support horizontal scroll
### isRowDisabled
- type: func
- description: Defines a function to call for each row to check whether row should appear as disabled or not
### dragAndDrop
- type: object
- description: No description
### onDragEnd
- type: func
- description: No description
### resizable
- type: bool
- description: Enables column resizing functionality
### resizeProps
- type: shape
- description: Table resize configuration - optional settings for resize behavior


