
### key
- type: string
- description: Toast key
### id
- type: string
- description: Toast id
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### dismissible
- type: boolean
- description: Whether the toast should render the dismiss button.
### dismissLabel
- type: string
- description: Aria label for the dismiss button.
### onDismiss
- type: (event?: React.MouseEvent) =&gt; void
- description: Callback function called whenever the user clicks the dismiss button.
### status
- type: ToastStatus
- description: Toast status.
### action
- type: React.ReactNode
- description: Action element to render.
### duration
- type: number
- description: Number in milliseconds to auto dismiss the toast. If the duration is set to &#39;null&#39;, toast won&#39;t be automatically dismissed.


