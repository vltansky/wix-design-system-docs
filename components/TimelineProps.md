
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### items
- type: TimelineItem[]
- description: Defines each individual event item in the component:
- `label` stores a text string naming the event or renders other components as its children
- `labelAction` stores an action button (or other components) related to the event
- `customPrefix` defines a custom milestone symbol for an item on the vertical axis
- `suffix` stores a date of the event (or other components)
### gap
- type: string
- description: Sets the distance that separates each item from the one below
### skin
- type: TimelineSkin
- description: Sets the skin of the component


