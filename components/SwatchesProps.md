
### colors
- type: array
- description: Defines an array of colors to be shown as swatches.
### selected
- type: string
- description: Specifies which color from the list is in a selected state.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### onClick
- type: func
- description: Defines a callback function for  user click on a swatch. Returns color HEX string representation.
### size
- type: enum
- description: Size of swatches
### showClear
- type: bool
- description: Specifies whether to display a &#39;No color&#39; option as a first item on a list or not.
### showClearMessage
- type: node
- description: Defines a message to display on &#39;No color&#39; option hover. `showClear` must be set to true.
### onAdd
- type: func
- description: Defines a callback function for &#39;Add&#39; button click. Returns color HEX string representation once user selects a color to be added.
### onChange
- type: func
- description: Defines a callback function for color change. Returns color HEX string representation.
### onCancel
- type: func
- description: Defines a callback function for color picker popover &#39;Cancel&#39; action (user closes it without picking color).
### showAddButton
- type: bool
- description: Specifies whether New color&#39; button is displayed or not. Add button opens up a color picker.
### addButtonMessage
- type: string
- description: Specifies a message to display on &#39;Add&#39; button hover. If not provided, the tooltip won&#39;t be displayed.
### addButtonIconSize
- type: enum
- description: Controls the size of a plus icon inside of the add button.
### columns
- type: number
- description: Specifies a number of columns in a single row. Default value is 6.
### gap
- type: number
- description: Specifies a gap between swatches in pixels. Default value is 12px.
### popoverProps
- type: shape
- description: Props that get passed to New color popover.
### renderColorPicker
- type: func
- description: Custom render function for the color picker.
Provides full control over the color picker UI and behavior.


