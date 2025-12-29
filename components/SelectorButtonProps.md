
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### DOMAttributes
- type: All props from DOMAttributes that comes from @types/react/index.d.ts
- description: No description
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
### ButtonHTMLAttributes
- type: All props from ButtonHTMLAttributes that comes from @types/react/index.d.ts
- description: No description
### fullWidth
- type: boolean
- description: Sets button width to fill a 100% of a parent container width.
### suffixIcon
- type: IconElement
- description: Pass an icon or a component to display at the end of a label (e.g., svg, image, etc.)
### onClick
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: Defines a callback function which is called every time a button is clicked.
### size
- type: ValuesOf&lt;{ readonly SMALL: &#34;small&#34;; readonly MEDIUM: &#34;medium&#34;; readonly LARGE: &#34;large&#34;; }&gt;
- description: Controls the size of a button.
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


