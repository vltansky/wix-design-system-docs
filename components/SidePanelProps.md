
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### buttonText
- type: string
- description: No description
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### onCloseButtonClick
- type: () =&gt; void
- description: Defines a callback function which is called every time a close button is clicked.
### onHelpButtonClick
- type: () =&gt; void
- description: Defines a callback function which is called every time a help button is clicked.
### children
- type: ReactNode
- description: Accepts any item as a child element. For standard panel layout pass compound elements of the panel:
* `&lt;SidePanel.Header/&gt;`
* `&lt;SidePanel.Content/&gt;`
* `&lt;SidePanel.Footer/&gt;`
* `&lt;SidePanel.Divider/&gt;`
### width
- type: string | number
- description: Controls the width of the panel
### height
- type: string | number
- description: Controls the height of the panel
### maxHeight
- type: string | number
- description: Controls the maximum height of the panel
### skin
- type: &#34;standard&#34; | &#34;floating&#34;
- description: Specifies the skin of the side panel.
### draggable
- type: boolean
- description: Specifies if panel is draggable (works only with floating skin).
### onBackButtonClick
- type: () =&gt; void
- description: Defines a callback function which is called every time a back button is clicked.
### backButtonDescription
- type: ReactNode
- description: When provided, sets the content of the back button&#39;s tooltip.
### backButtonTooltipProps
- type: TooltipCommonProps
- description: Allows to pass all common tooltip props to back button’s tooltip.
### backButtonProps
- type: SidePanelBackButtonProps
- description: Back button props.
### helpButtonProps
- type: SidePanelButtonProps
- description: Help button props.
### closeButtonProps
- type: SidePanelCloseButtonProps
- description: Close button props.


