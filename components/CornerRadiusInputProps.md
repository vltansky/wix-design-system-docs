
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### topLeft
- type: CornerProps
- description: Properties for the top left corner input.
### topRight
- type: CornerProps
- description: Properties for the top right corner input.
### bottomLeft
- type: CornerProps
- description: Properties for the bottom left corner input.
### bottomRight
- type: CornerProps
- description: Properties for the bottom right corner input.
### linked
- type: boolean
- description: When set to `true`, linked mode is initially enabled on the component.
### onLinkedToggle
- type: (isLinked: boolean) =&gt; void
- description: Callback function that is called when the linked mode is toggled on or off.
### linkingButtonLabels
- type: { pressed: string; unpressed: string; }
- description: Specifies the labels displayed when hovering over the link button.
The `pressed` key defines the label shown when link mode is active (or pressed),
while the `unpressed` key defines the label for when link mode is inactive (or unpressed).
### size
- type: ValuesOf&lt;{ readonly tiny: &#34;tiny&#34;; readonly small: &#34;small&#34;; readonly medium: &#34;medium&#34;; readonly large: &#34;large&#34;; }&gt;
- description: Specifies the size of the component.
### min
- type: number
- description: Min value for all corners.
### max
- type: number
- description: Max value for all corners.
### linkedValuesChangedMessage
- type: string
- description: When all corners have been modified in linked mode, this message is announced to screen readers.


