
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### width
- type: union
- description: Width HTML attribute of the content. If a number is passed then it defaults to px. e.g width={400} =&gt; width=&#34;400px&#34;
### target
- type: node
- description: The target of the popover
### content
- type: node
- description: A `&lt;FloatingHelper.Content&gt;` component
### onClose
- type: func
- description: callback to call when the popover content is requested to be closed (Uncontrolled mode only). NOTE: this callback is called when the close timeout (if exists) starts In Controlled mode - called when the close button is clicked. In Uncontrolled mode - called when the popover is closed
### skin
- type: enum
- description: Skin : `dark` or `light`
### appearance
- type: enum
- description: No description
### initiallyOpened
- type: bool
- description: Controls whether the popover&#39;s content is initially opened (In Uncontrolled mode only)
### opened
- type: bool
- description: Controls whether the popover&#39;s content is shown or not (aka Controlled mode).
When undefined, then the component is Uncontrolled. See open/close behaviour section in docs.
### placement
- type: enum
- description: The location to display the content.
### appendTo
- type: enum
- description: Enables calculations in relation to a dom element.
### onOpen
- type: func
- description: Callback to call when the popover content is requested to be opened (Uncontrolled mode only)
### moveBy
- type: shape
- description: Moves the floating helper relative to the parent by x or y
### zIndex
- type: number
- description: Floating helper z-index
### hideDelay
- type: number
- description: Set a delay on closing


