
### children
- type: ReactNode | ((data: { setCharactersLeft: CharactersLeftFn; }) =&gt; ReactNode)
- description: Accept any kind of component as a child element. A child should be a form element like an Input, InputArea, Dropdown or RichTextArea.
### charCount
- type: number
- description: Sets the maximum length for the field value. Character count is displayed in the top right corner of a component.
### stretchContent
- type: boolean
- description: Defines whether or not the content (children container) grows when there&#39;s space available. Otherwise, it only uses the necessary space.
### label
- type: ReactNode
- description: Sets a field label. It’s default value is a text string, but it can be overridden with any other component.
### labelAlignment
- type: LabelAlignment
- description: Controls the label alignment
### labelPlacement
- type: LabelPlacement
- description: Controls the label placement
### labelSize
- type: LabelSize
- description: Controls the size of label
### required
- type: boolean
- description: Marks a field as mandatory with an asterisk (*) at the end of a label.
### infoContent
- type: ReactNode
- description: Displays a passed info message in a tooltip. Default value is a text string, but it can also be overridden with any other component.
### infoTooltipProps
- type: TooltipCommonProps
- description: Allows control over the tooltip style and behaviour by passed tooltip properties.
### suffix
- type: ReactNode
- description: Adds a custom element at the end of the label row (it overrides the charCount in case it&#39;s provided).
### status
- type: StatusType
- description: Sets the type of status message, to give it appropriate colors and icons
### statusMessage
- type: ReactNode
- description: Sets the status message. It is displayed bellow the child component
### id
- type: string
- description: Input id used for connecting label to the input element using native ```for``` attribute

```js
&lt;FormField id=&#34;myFormField&#34; label=&#34;Hello&#34;&gt;
 &lt;Input id=&#34;myFormField&#34;/&gt;
&lt;/FormField&gt;
```
### labelId
- type: string
- description: Sets the id of the label
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in tests.
### labelWidth
- type: string
- description: Applies custom width to the label. Works only when `labelPlacement` value is `right` or `left`
### inputWidth
- type: string
- description: Applies custom width to the child component. Works only when `labelPlacement` value is `right` or `left`
### classNames
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### showInfoIconOnHover
- type: boolean
- description: Controls the visibility of the information icon based on hover.
If set to true, the icon appears only when the component is hovered over. By default, the icon is always visible (false).
When the component is wrapped with SidePanel.Field, the hover area extends to cover the full bounds of the component.
### ellipsis
- type: boolean
- description: No description
### maxLines
- type: number
- description: No description


