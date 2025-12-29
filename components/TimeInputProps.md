
### border
- type: enum
- description: Control the border style of input
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### disabled
- type: bool
- description: Specifies whether component is disabled
### locale
- type: enum
- description: Sets locale and formats time according to it
### onChange
- type: func
- description: Defines a callback function which is called on every time value changes
### onInvalid
- type: func
- description: Defines a callback function which is called on cases when invalid time is typed or confirmed with an action.
- return {{ validationType: &#39;formatError&#39; | &#39;outOfBoundsError&#39;, value: string }}
- `validationType` - type &#39;formatError&#39;is set when value is in the wrong time format
                   - type &#39;outOfBoundsError&#39; is set when `excludePastTimes` or `filterTime` is used and value does not match the filters
- `value` - is set to current input value
### placeholder
- type: string
- description: Sets a placeholder message to display
### prefix
- type: node
- description: Pass a component you want to show as the prefix of the input, e.g., text, icon
### readOnly
- type: bool
- description: Specifies whether input is read only
### autoSelect
- type: bool
- description: Specifies whether input is auto selected on focus
### size
- type: enum
- description: Controls the size of the input
### status
- type: enum
- description: Specify the status of a field
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### invalidMessage
- type: string
- description: Enables internal validation and defines a message to display when user types invalid time value
### step
- type: number
- description: Specifies the interval between time values shown in dropdown
### suffix
- type: node
- description: Pass a component you want to show as the suffix of the input, e.g., text, icon
### timeStyle
- type: string
- description: Specifies what time formatting style to use when calling `format()`
### value
- type: object
- description: Specifies the current value of the input
### width
- type: enum
- description: Controls the width of the component. `auto` will resize the input to match width of its contents, while `100%` will take up the full parent container width.
### onFocus
- type: func
- description: Defines a standard input `onFocus` callback
### onBlur
- type: func
- description: Defines a standard input `onBlur` callback
### excludePastTimes
- type: bool
- description: Specify whether past time slots should be shown or not
### filterTime
- type: func
- description: Specify selectable time slots:
 * `param` {Date} `value` - a time to check
 * `return` {boolean} - true if `value` should be shown in time slots dropdown, false otherwise
### hideStatusSuffix
- type: bool
- description: Specifies whether status suffix is hidden.
### popoverProps
- type: shape
- description: Allows to pass all common popover props.


