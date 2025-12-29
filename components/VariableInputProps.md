
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### disabled
- type: bool
- description: Specifies whether input should be disabled or not
### readOnly
- type: bool
- description: Specifies whether input is read only
### initialValue
- type: string
- description: Defines an initial value to display
### multiline
- type: bool
- description: Specifies whether component allow multiple lines or not. If false, text won’t wrap and horizontal scroll will appear inside of a component.
### onChange
- type: func
- description: Defines a callback function that is called each time value is changed:
`onChange(value: String): void`
### onSubmit
- type: func
- description: Defines a callback function that is called on value submit, in other words after `insertVariable()` and `setValue()` and `insertText()`
`onSubmit(value: String): void`
### onBlur
- type: func
- description: Defines a callback function that is called on focus out:
`onBlur(value: String): void`
### onFocus
- type: func
- description: Defines a callback function that is called on focus in:
`onFocus(value: String): void`
### status
- type: enum
- description: Specify the status of a field
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### placeholder
- type: string
- description: Sets a placeholder message to display
### rows
- type: number
- description: Set the height of a component to fit the given number of rows
### size
- type: enum
- description: Controls the size of the input and variable tags
### variableParser
- type: func
- description: Defines the variable keys that component will parse and convert to &lt;Tag/&gt; components on blur and while using `insertVariable`.
For each key `variableParser` will be called and should return a proper text for that key or false in case the key is invalid.
`variableParser(key: String): String|boolean`
### variableTagPropsParser
- type: func
- description: A function callback that is being called on each keyboard enter and expects a return of object with properties meant for Tag component.
It is designed to dynamically determine the styling or properties applied to variable tags within the input field.`
### variableTemplate
- type: shape
- description: Defines a template for variable recognition. Typed text strings with matching prefix and suffix symbols will be converted to &lt;Tag/&gt; components.


