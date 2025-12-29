
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### value
- type: union
- description: Defines current color. It can be provided in `string` or `object` format [https://github.com/Qix-/color](https://github.com/Qix-/color)
### showHistory
- type: bool
- description: Specifies whether current and previously used colors should be displayed
### showConverter
- type: bool
- description: Specifies whether `HEX`/`RGB`/`HSB` converter tabs be displayed
### showInput
- type: bool
- description: Specifies whether color input in HEX mode should be displayed. This is relevant only if `showConverter` is `false`
### showActionButtons
- type: bool
- description: Specifies whether action buttons (confirm/cancel) should be displayed
### onChange
- type: func
- description: Defines an event handler for color change.
### onCancel
- type: func
- description: Defines an event handler for cancel button click.
### onConfirm
- type: func
- description: Defines an event handler for confirm button click.
### onAdd
- type: func
- description: Defines an event handler for color add button click. If not passed, the plus icon will not be visible.
### children
- type: union
- description: Defines child items to be rendered above action buttons. Accepts any kind of content.
### addTooltipContent
- type: node
- description: Defines content to show in add button tooltip. Does not appear if `onAdd` is not passed.
### allowEmpty
- type: bool
- description: Allows to submit when color is not selected. Returns a color object with alpha equal to 0.
### emptyPlaceholder
- type: string
- description: Defines a placeholder text to show in an input when `allowEmpty` is true
### showEyeDropper
- type: bool
- description: Specifies whether eye dropper tool should be displayed
### eyeDropperLabel
- type: string
- description: Defines the label for the eye dropper button
### removePadding
- type: bool
- description: Specifies whether component padding should be removed


