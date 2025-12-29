
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### image
- type: node
- description: Accepts image URL or a custom element to be displayed on the side of content.
### imageBackgroundColor
- type: string
- description: Specifies image area background color. Can be a keyword from color palette or any supported CSS color value (HEX, RGB, etc.).
### size
- type: enum
- description: Controls the size of the marketing layout.&lt;br/&gt;
### direction
- type: enum
- description: Controls content direction.
### alignItems
- type: enum
- description: Controls the vertical alignment of the content.
### inverted
- type: bool
- description: Flips content layout. If true, image will be displayed on the left side of the content.
### actions
- type: node
- description: Sets marketing layout actions. Accepts single or multiple interactive components. Most commonly contain `&lt;Button/&gt;` or `&lt;TextButton/&gt;`.
### title
- type: node
- description: Sets the marketing layout title. Accepts text string or a custom element.
### description
- type: node
- description: Sets the marketing layout description. Accepts text string or a custom element.
### badge
- type: node
- description: Adds a container for a `&lt;Badge/&gt;` component at the top left corner. Affect component height.
### hiddenBadge
- type: bool
- description: Specifies whether the badge is hidden. Can be used to add additional vertical spacing, if no badge is given.
### imagePadding
- type: bool
- description: Enables padding inside image container. Use with `direction=&#34;horizontal&#34;` layout only.


