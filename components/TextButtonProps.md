
### ButtonHTMLAttributes
- type: All props from ButtonHTMLAttributes that comes from @types/react/index.d.ts
- description: No description
### HTMLAttributes
- type: All props from HTMLAttributes that comes from @types/react/index.d.ts
- description: No description
### AriaAttributes
- type: All props from AriaAttributes that comes from @types/react/index.d.ts
- description: No description
### DOMAttributes
- type: All props from DOMAttributes that comes from @types/react/index.d.ts
- description: No description
### skin
- type: TextButtonSkin
- description: Specifies the skin of a button
### underline
- type: TextButtonUnderline
- description: Specifies whether to display and when to display an underline below button label
### weight
- type: TextButtonWeight
- description: Controls the font weight of button label
### size
- type: TextButtonSize
- description: Controls the size of a button
### suffixIcon
- type: IconElement
- description: Pass an icon or a component to display at the end of a label (e.g., svg, image, etc.)
### prefixIcon
- type: IconElement
- description: Pass an icon or a component to display at the front of a label (e.g., svg, image, etc.)
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### fluid
- type: boolean
- description: Stretches button to fill a 100% of its parent container width
### ellipsis
- type: boolean
- description: Specifies whether component handles text overflow with ellipsis. If enabled, label that exceed available space will be displayed inside of a tooltip when user hover over a button.
### showTooltip
- type: boolean
- description: Specifies whether the full button label is displayed in a tooltip when label overflows available space.

Behaviour is enabled by default. Set property value to false to show ellipsis without a tooltip.
### tooltipProps
- type: TooltipCommonProps
- description: Allows to pass all common tooltip props. Use it to customize a tooltip created from text ellipsis.
### ariaLabel
- type: string
- description: Defines a string value that labels the button element to screen reader users
### ariaLabelledBy
- type: string
- description: Identifies the element that labels the button element
### ariaHaspopup
- type: string
- description: Indicates to screen reader users whether an interactive popup element, such as menu or dialog, can be triggered by a button
### ariaExpanded
- type: boolean
- description: Indicates to screen reader users whether the collapsible content below is in the expanded or in the collapsed state
### ariaControls
- type: string
- description: Identifies the element whose contents or presence are controlled by the button
### ariaActiveDescendant
- type: string
- description: Identifies the element that represents the currently active descendant of the button
### as
- type: &#34;object&#34; | &#34;small&#34; | &#34;form&#34; | &#34;slot&#34; | &#34;style&#34; | &#34;title&#34; | &#34;button&#34; | &#34;search&#34; | &#34;article&#34; | &#34;dialog&#34; | &#34;figure&#34; | &#34;img&#34; | &#34;link&#34; | &#34;main&#34; | &#34;menu&#34; | &#34;option&#34; | &#34;table&#34; | &#34;time&#34; | ... 94 more ... | ComponentType&lt;...&gt;
- description: Renders component as any other component or a given HTML tag.
### wrap
- type: boolean
- description: Enables wrapping when text is longer than its parent container. Cannot be used with as=&#34;button&#34;
### AnchorHTMLAttributes
- type: All props from AnchorHTMLAttributes that comes from @types/react/index.d.ts
- description: No description


