
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### value
- type: string
- description: Initial value to display with component render
### placeholder
- type: string
- description: Placeholder to display
### onApprove
- type: (value: string) =&gt; void
- description: A callback function triggered by clicking the approve button.
##### Signature:
function(value: string) =&gt; void
* `value`: the text contained in the input.
### onCancel
- type: () =&gt; void
- description: A callback function triggered by clicking the cancel button.
##### Signature:
function() =&gt; void
### cancelButtonTooltipContent
- type: ReactNode
- description: Cancel button tooltip content
### cancelButtonTooltipProps
- type: TooltipCommonProps
- description: Cancel button tooltip common props
### approveButtonTooltipContent
- type: ReactNode
- description: Approve button tooltip content
### approveButtonTooltipProps
- type: TooltipCommonProps
- description: Approve button tooltip common props
### approveButtonDisabledOnEmpty
- type: boolean
- description: Make the approve button disabled when input value is empty
### size
- type: ValuesOf&lt;{ readonly small: &#34;small&#34;; readonly medium: &#34;medium&#34;; }&gt;
- description: Specifies the size of the input
### status
- type: InputStatus
- description: Input status - use to display an status indication for the user
### statusMessage
- type: ReactNode
- description: The status (error/loading) message to display when hovering the status icon, if not given or empty there will be no tooltip
### margins
- type: ListItemEditableMargins
- description: The type of margin
### suffix
- type: ReactNode
- description: Pass a component you want to show as the suffix of the input, e.g., text, icon
### autoFocus
- type: boolean
- description: Focus the input on mount (standard React input autoFocus)
### onEnterPressed
- type: KeyboardEventHandler&lt;HTMLInputElement&gt;
- description: Defines a callback handler that is called when the user presses enter on the input element
### onChange
- type: ChangeEventHandler&lt;HTMLInputElement&gt;
- description: Defines a standard input onChange callback


