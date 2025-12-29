
### name
- type: string
- description: Defines a name of the avatar user. Text initials will be generated from the name.
The name value will be used as default value for HTML title and `aria-label` attributes.
And also as default value for the image&#39;s alt attribute if `imgProps` is provided.
### text
- type: string
- description: Defines a text to render as a content instead of a given `name`.
### placeholder
- type: node
- description: Accept any content to render as a content placeholder. This placeholder will be displayed if no text, name or imgProps are provided.&lt;br&gt;
By default use a generic avatar user icon.
### imgProps
- type: object
- description: Accept all common `&lt;img&gt;` tag properties.
### ariaLabel
- type: string
- description: Defines a string that labels the current element in case where text label is not visible on the screen.
### title
- type: string
- description: Defines a standard HTML title attribute value. Applies it to the root element.
### onClick
- type: func
- description: Defines a click event handler. When defined, component will be clickable and will have a pointer cursor on hover.
### size
- type: enum
- description: Controls the size of an avatar.
### color
- type: enum
- description: Controls the background color of the avatar. If not provided,
color is determined by the provided text or name so that each name will receive a different color.
### shape
- type: enum
- description: Controls the shape of the image.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### presence
- type: enum
- description: Sets the presence status of an avatar.
### indication
- type: node
- description: Accept any content to render as an indication item.
### customIndication
- type: node
- description: Accept any content to render as a custom indication item. This indication element will not be wrapped by an IconButton.
It could be rendered in other shapes (such as square).
### onIndicationClick
- type: func
- description: Defines a callback function which is called every time indication element is clicked.
### showIndicationOnHover
- type: bool
- description: Shows indication element on hover.
### loading
- type: bool
- description: Shows a loader on top of an avatar.


