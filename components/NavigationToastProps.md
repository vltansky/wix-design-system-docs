
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
### children
- type: ReactNode
- description: Content to display in the toast.
### prefixIcon
- type: false | IconElement
- description: Custom icon displayed at the start of the toast content.
### onAction
- type: MouseEventHandler&lt;HTMLDivElement&gt;
- description: Callback triggered when the toast action is performed.
### duration
- type: number
- description: Time in milliseconds before the toast dismisses automatically. When set to `0` or `null`, the toast remains indefinitely.


