
### inline
- type: boolean
- description: Defines if the box behaves as an inline element
### direction
- type: BoxDirection
- description: Defines how the children are ordered (horizontally or vertically). Supports <code>horizontal</code> (default) and <code>vertical</code>.
### children
- type: ReactNode
- description: Allows to render any component as a child item
### className
- type: string
- description: Specifies a CSS class name to be appended to the component's root element.
### align
- type: BoxHorizontalAlignment
- description: Defines how the children are aligned according to the X axis. Supports <code>left</code>, <code>center</code>, <code>right</code>, and <code>space-between</code>.
### verticalAlign
- type: BoxVerticalAlignment
- description: Defines how the children are aligned according to the Y axis. Supports <code>top</code>, <code>middle</code>, <code>bottom</code>, and <code>space-between</code>.
### dataHook
- type: string
- description: Accepts HTML attributes that can be used in the tests
### gap
- type: BoxCssSizingProperty
- description: Sets the gaps/gutters between flex items. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), or a spacing token (SP1, SP2, etc.).
### border
- type: string
- description: Enables a border and sets its width and style. This prop does not include WSR color variable keys.
### style
- type: CSSProperties
- description: Sets object of CSS styles
### color
- type: string
- description: Sets a text color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### backgroundColor
- type: string
- description: Sets a background color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### borderColor
- type: string
- description: Sets a border color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### borderTopColor
- type: string
- description: Sets a border top color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### borderRightColor
- type: string
- description: Sets a border right color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### borderBottomColor
- type: string
- description: Sets a border bottom color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### borderLeftColor
- type: string
- description: Sets a border left color by a key from the color palette or natively supported value (Hex, RGB, etc.)
### margin
- type: BoxCssSizingProperty
- description: Sets margin on all sides. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a string of space-separated values ("3px 3px").
### marginTop
- type: BoxCssSizingProperty
- description: Sets margin on the top. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### marginRight
- type: BoxCssSizingProperty
- description: Sets margin on the right. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### marginBottom
- type: BoxCssSizingProperty
- description: Sets margin on the bottom. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### marginLeft
- type: BoxCssSizingProperty
- description: Sets margin on the left. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### padding
- type: BoxCssSizingProperty
- description: Sets padding on all sides. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a string of space-separated values ("3px 3px").
### paddingTop
- type: BoxCssSizingProperty
- description: Sets padding on the top. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### paddingRight
- type: BoxCssSizingProperty
- description: Sets padding on the right. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### paddingBottom
- type: BoxCssSizingProperty
- description: Sets padding on the bottom. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### paddingLeft
- type: BoxCssSizingProperty
- description: Sets padding on the left. Accepts a numeric value (multiplied by spacing unit), predefined spacing value (tiny, small, etc.), a spacing token (SP1, SP2, etc.), or a value in pixels.
### minWidth
- type: BoxCssSizingProperty
- description: Sets the minimum width of the box in pixels
### maxWidth
- type: BoxCssSizingProperty
- description: Sets the maximum width of the box in pixels
### width
- type: BoxCssSizingProperty
- description: Sets the width of the box in pixels
### minHeight
- type: BoxCssSizingProperty
- description: Sets the minimum height of the box in pixels
### maxHeight
- type: BoxCssSizingProperty
- description: Sets the maximum height of the box in pixels
### height
- type: BoxCssSizingProperty
- description: Sets the height of the box in pixels
### HTMLAttributes
- type: All props from HTMLAttributes that comes from @types/react/index.d.ts
- description: No description
### AriaAttributes
- type: All props from AriaAttributes that comes from @types/react/index.d.ts
- description: No description
### DOMAttributes
- type: All props from DOMAttributes that comes from @types/react/index.d.ts
- description: No description
### role
- type: AriaRole
- description: Sets the WAI-ARIA role for the box element. When set to <code>button</code> or <code>link</code>, the box automatically receives <code>tabIndex=0</code> for keyboard accessibility.
### ariaLabel
- type: string
- description: Sets the WAI-ARIA label for the box element, providing an accessible name for assistive technologies.
