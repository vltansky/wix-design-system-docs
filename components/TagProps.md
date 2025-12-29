
### disabled
- type: boolean
- description: Specifies whether the tag should be disabled
### id
- type: string
- description: Assigns an unique identifier for the tag
### onClick
- type: (id: string, event: MouseEvent&lt;HTMLButtonElement, MouseEvent&gt;) =&gt; void
- description: Defines a callback function which is called whenever a tag component is clicked.
It passes the id property as the first parameter and a mouse event as second parameter.
### onRemove
- type: (id: string) =&gt; void
- description: Defines a callback function which is called when removing the tag. It passes the id property as a parameter.
### removable
- type: boolean
- description: Specifies whether the tag is removable or not. If enabled, a small clickable X icon is displayed on the right side of a component.
### size
- type: TagSize
- description: Controls the size of the component
### skin
- type: TagSkin
- description: Sets the skin of the component
### theme
- type: TagSkin
- description: No description
### thumb
- type: ReactElement&lt;any, string | JSXElementConstructor&lt;any&gt;&gt;
- description: Displays a thumbnail at the front of a tag label. Usually contain icons or `&lt;Avatar/&gt;`.
### maxWidth
- type: MaxWidth&lt;string | number&gt;
- description: Sets a maximum tag width
### ellipsisProps
- type: EllipsisCommonProps
- description: Ellipsis props
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### children
- type: ReactNode
- description: Sets the text of the tag


