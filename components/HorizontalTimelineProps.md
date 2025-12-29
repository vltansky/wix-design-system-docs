
### skin
- type: enum
- description: Controls the style of the component.
### alignLabel
- type: enum
- description: Aligns the labels of items.
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### items
- type: arrayOf
- description: Timeline items
 * `skin` - Controls line and text color (deprecated).
 * `line ` - Affects the line type, can be one of: &#39;filled&#39; | &#39;dashed&#39;.
 * `label` -  Text displayed below the icon.
 * `icon ` - An icon representing a timeline item.
 * `width ` - The width of the timeline item, can be percentage or pixels.
 * `labelEllipsis ` - Set ellipsis for item&#39;s label  .


