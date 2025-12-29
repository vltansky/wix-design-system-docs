
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### imageUrl
- type: string
- description: Links to image asset source (URL). Leave it blank when image is not uploaded yet.
### fit
- type: enum
- description: Specifies image fit mode inside a box.
Check [object-fit](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) CSS property values for more info.
### status
- type: enum
- description: Specifies the status of a viewer.
### statusMessage
- type: node
- description: Defines the message to display on status icon hover. If not given or empty there will be no tooltip.
### tooltipProps
- type: shape
- description: Allows to pass all common tooltip props.
### showUpdateButton
- type: bool
- description: Specifies whether the update button is visible.
### showDownloadButton
- type: bool
- description: Specifies whether the download button is visible.
### showRemoveButton
- type: bool
- description: Specifies whether the remove button is visible.
### onAddImage
- type: func
- description: Defines a click handler, which is called every time a user clicks on an empty viewer (when no `imageUrl` is provided).
### onUpdateImage
- type: func
- description: Defines a handler function, which is called every time user clicks on the ‘Update image’ button.
### onDownloadImage
- type: func
- description: Defines a handler function, which is called every time user clicks on the download button.
### onRemoveImage
- type: func
- description: Defines a handler function, which is called every time user clicks on the ‘Remove image’ button.
### onImageLoad
- type: func
- description: Defines a handler function which is called right after image loads.
### addImageInfo
- type: string
- description: Specifies a message to display in a tooltip when no image is uploaded yet.
### updateImageInfo
- type: string
- description: Defines a message to display in a tooltip when ‘Update’ action button is hovered.
### downloadImageInfo
- type: string
- description: Defines a message to display in a tooltip when ‘Download’ action button is hovered.
### removeImageInfo
- type: string
- description: Defines a message to display in a tooltip, when ‘remove’ action button is hovered.
### moreImageInfo
- type: string
- description: Defines a message to display in a tooltip when the ‘More’ action button is hovered. Relevant only when all buttons are visible.
### removeRoundedBorders
- type: bool
- description: Removes default border radius.
### width
- type: union
- description: Sets the width of the viewer box.
### height
- type: union
- description: Sets the height of the viewer box.
### disabled
- type: bool
- description: Specifies whether the component is disabled.
### imageProps
- type: shape
- description: Additional props to pass to the Image component (borderRadius, position, showBorder, transparent, etc.).
### updateButtonAriaLabel
- type: string
- description: Defines a string value that labels the update button element
### removeButtonAriaLabel
- type: string
- description: Defines a string value that labels the remove button element


