
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests.
### children
- type: React.ReactNode
- description: Accepts any kind of components as child elements. A child component should be a form element like an Input, InputArea, Dropdown or RichTextArea.
### legend
- type: React.ReactNode
- description: Sets a field set legend, which is a descriptive title for a group of components. Its default value is a text string, but it can be overridden with any other component.
### legendPlacement
- type: LegendPlacement
- description: Controls the position of the legend, in terms of field set child components.
### legendAlignment
- type: LegendAlignment
- description: Controls the vertical alignment of the legend.
### legendSize
- type: LegendSize
- description: Controls the size of the legend.
### required
- type: boolean
- description: Marks the field set as mandatory with an asterisk (*) at the end of the legend.
### infoContent
- type: React.ReactNode
- description: Displays a passed info message in a tooltip next to field set legend. Default value is a text string, but it can also be overridden with any other component.
### infoTooltipProps
- type: TooltipCommonProps
- description: Allows control over the tooltip style and behaviour by passed tooltip properties.
### suffix
- type: React.ReactNode
- description: Adds a custom element at the end of the legend row (it overrides the charCount in case it&#39;s provided).
### charCount
- type: number
- description: Sets the maximum length for the field value inside field set child input. Character count is displayed in the top right corner of a component.
### status
- type: FieldSetStatusType
- description: Sets the type (color, icon) of a status message for the whole field set.
### statusMessage
- type: React.ReactNode
- description: Sets the field set status message. It is displayed bellow all field set child components.
### statusId
- type: string
- description: Adds an id to a field set status message. Use with `aria-describedby` attribute on specific input to connect it with `FieldSet` status message for accessibility.
### alignment
- type: Alignment
- description: Controls the alignment of all field set child components.
### direction
- type: Direction
- description: Controls if field set child components are rendered horizontally or vertically.
### gap
- type: Gap
- description: Controls the gap between all field set child components.
### columns
- type: string
- description: Controls the width of each field set child component. Works only with `horizontal` direction.
### ellipsis
- type: boolean
- description: Truncates legend that is longer than its parent container and displays ellipsis at the end of the last line. Enabled by default legend placement is set to `top`.
### maxLines
- type: number
- description: Truncates legend text at a specific number of lines when using `ellipsis`.


