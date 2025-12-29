
### placeholder
- type: string
- description: Defines placeholder text to display on an empty input
### disabled
- type: bool
- description: Specifies whether the input should be disabled
### status
- type: enum
- description: Specifies the status of a field
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty, there will be no tooltip.
### size
- type: enum
- description: Controls input size
### value
- type: string
- description: Defines input value
### onConfirm
- type: func
- description: Returns confirmed value
### onCancel
- type: func
- description: Returns last confirmed value from `value` prop
### onChange
- type: func
- description: Returns changed value of input or color picker
### colorPickerChildren
- type: union
- description: Defines child items to render inside of a component. Accepts any kind of content. It receives the `changeColor` function to control &lt;ColorInput/&gt; value.
### onAddColor
- type: func
- description: Defines a callback handler with color HEX string. Handler is called whenever the `Add Color` button is pressed.
### addTooltipContent
- type: node
- description: Defines content to show in add button tooltip. Does not appear if `onAdd` is not passed.
### popoverProps
- type: object
- description: Allows to pass popover props. See &lt;Popover/&gt; API for a full list.


