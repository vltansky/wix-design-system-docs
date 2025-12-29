
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component&#39;s root element.
### skin
- type: enum
- description: Sets a default overlay skin.
### hoverSkin
- type: enum
- description: Sets a hover overlay skin.
### media
- type: node
- description: Accept image URL or a custom node as a media background.
### onClick
- type: func
- description: Defines a click handler. When provided, component will be clickable and will have a pointer cursor on hover.
### children
- type: node
- description: Accepts any component as `&lt;MediaOverlay.Content&gt;` content.
Each element has the following properties:
- `visible` - define when to display this content. Possible values are:
  - `default` (default) - content is visible only when not hovered.
  - `hover` - content is visible only when hovered.
  - `always` - content is always visible.
- `placement` - define where to place this content. Possible values are `top-start`,
`top-end`, `middle` (default), `bottom-end` and `bottom-start`.
### hovered
- type: bool
- description: Toggles hover state in a controlled mode.
### removeRoundedBorders
- type: bool
- description: Removes a default borders radius.
### borderRadius
- type: union
- description: Control border radius of the media container.
### ariaHidden
- type: bool
- description: Adding aria-hidden=&#34;true&#34; to an element removes that element and all of its children from the accessibility tree.


