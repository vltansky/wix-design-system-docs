
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### zIndex
- type: number
- description: Controls the z-index of the component.
### position
- type: TopBannerPosition
- description: Determines if the top banner stays fixed at the top of its container.
### dismissible
- type: boolean
- description: Determines whether the top banner should render a dismiss button.
### dismissLabel
- type: string
- description: Aria label for the dismiss button.
### action
- type: ReactNode
- description: An action component to display in the top banner. The component can be one of these types:
Can be either:
- `&lt;TopBanner.ActionButton/&gt;`
- `&lt;TopBanner.ActionLink/&gt;`
- custom
### onDismiss
- type: (event: MouseEvent&lt;Element, MouseEvent&gt;) =&gt; void
- description: Callback function called whenever the user clicks the dismiss button.
### children
- type: ReactNode
- description: The main content of the top banner.


