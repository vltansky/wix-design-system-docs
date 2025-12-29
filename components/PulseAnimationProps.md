
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### children
- type: node
- description: Node to animate (one child node)
### active
- type: bool
- description: Triggers the animation transition
### onStart
- type: func
- description: A callback fired immediately after the animation starts.
### onEnd
- type: func
- description: A callback fired immediately after the animation ends.
### loop
- type: bool
- description: When set to true, the child component animate repetitively until stopped by other event
### delay
- type: union
- description: Set a delay before the animation execution. When provided a number- sets this as `ms`.
### color
- type: enum
- description: The color of the animation
### borderRadius
- type: string
- description: Sets the border-radius css property of the animation
### fluid
- type: bool
- description: Changes fluidity from fit-content to 100% and allows children to stretch to its parent container width


