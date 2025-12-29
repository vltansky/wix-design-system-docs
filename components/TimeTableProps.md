
### dataHook
- type: string
- description: Hook for testing purposes.
### onChange
- type: func
- description: Event triggered on column data change:
`onChange(columns, { addedToColumnIndex, removedFromColumnIndex, addedItemIndex, removedItemIndex })`
### columns
- type: arrayOf
- description: Column data configuration. Item content is provided as a simple node or a
render function with `content` property. When render function is used the
signature is:
`({ Item, draggable, disabled }) =&gt; {}`:
- `Item` - component used to provide default item visual representation.
You should render `&lt;Item draggable={draggable} disabled={disabled}&gt;...&lt;/Item&gt;`
- `draggable` - item is draggable.
- `disabled` - item is disabled.
### onAdd
- type: func
- description: Event triggered on add button click: `onAdd(columnIndex)`.
When not provided the button will be hidden.
### addItemButtonLabel
- type: node
- description: Title of add button.
### insertPosition
- type: enum
- description: Position where dragged items will be inserted. Using `any` value will
allow the items to be re-ordered within the same column.
### height
- type: union
- description: Custom table height.


