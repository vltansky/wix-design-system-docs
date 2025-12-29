
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### children
- type: any
- description: Defines tooltip’s trigger element
### content
- type: React.ReactNode
- description: Defines the content to be shown inside a tooltip
### disabled
- type: boolean
- description: Allows showing a tooltip when hovering on a disabled trigger element with mouse
### textAlign
- type: TooltipTextAlign
- description: Controls the alignment of tooltip’s content
### enterDelay
- type: number
- description: Sets time to wait before showing the tooltip (in milliseconds)
### exitDelay
- type: number
- description: Sets time to wait before hiding the tooltip (in milliseconds)
### moveBy
- type: { x?: number; y?: number; }
- description: Moves a tooltip in relation to its trigger element on x or y axis
### moveArrowTo
- type: number
- description: Moves a tooltip’s arrow by a defined amount
### appendTo
- type: AppendTo
- description: Calculates tooltip’s position in relation to a DOM element.
Can be either: &#39;window&#39;, &#39;scrollParent&#39;, &#39;viewport&#39;, &#39;parent&#39;, element or
function based predicate. I.e., (elm) =&gt; elm.getAttribute(&#39;data-hook&#39;) === &#39;value
### flip
- type: boolean
- description: Flips a tooltip’s placement when it starts to overlap its trigger element
### fixed
- type: boolean
- description: Enables keeping a tooltip at its original placement even when it is being positioned outside the boundary
### maxWidth
- type: React.CSSProperties
- description: Defines max width of a tooltip in px. If content is wider than maxWidth allows, it wraps into multiple lines.
### onShow
- type: () =&gt; void
- description: Defines a callback function on tooltip’s show event
### onHide
- type: () =&gt; void
- description: Defines a callback function on tooltip’s hide event
### placement
- type: Placement | &#34;auto&#34; | &#34;auto-start&#34; | &#34;auto-end&#34;
- description: Sets tooltip&#39;s placement in relation to its trigger element
### size
- type: TooltipSize
- description: Controls the size of a tooltip
### zIndex
- type: React.CSSProperties
- description: Controls the tooltip’s z-index
### fluid
- type: boolean
- description: Stretches the root element to the width of its container
### aria-labelledby
- type: string
- description: Connects tooltip’s trigger element to tooltip’s label content for assistive technologies.
Use this when the action doesn&#39;t have any visual text content, i.e. Icon Button.
Currently only one, either aria-labelledby or aria-describedby is supported.
If both are provided aria-labelledby takes priority.
### aria-describedby
- type: string
- description: Connects tooltip’s trigger element to tooltip’s descriptive content for assistive technologies.
Use this when you want to provide information in addition to actions visual information, i.e. TextButton.
Currently only one, either aria-labelledby or aria-describedby is supported.
If both are provided aria-labelledby takes priority.
### inline
- type: boolean
- description: Enables inline-block behaviour for the tooltip trigger element.
Use this when working with inline based elements i.e. Text, TextButton, Button etc.
### interactive
- type: boolean
- description: Enables hovering the tooltip itself.
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


