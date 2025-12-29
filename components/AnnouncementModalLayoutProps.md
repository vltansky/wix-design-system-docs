
### title
- type: ReactNode
- description: The modal&#39;s title
### subtitle
- type: ReactNode
- description: The modal&#39;s subtitle
### content
- type: ReactNode
- description: the content you want to render in the modal, children passed directly will be treated as `content` as well
### primaryButtonText
- type: ReactNode
- description: a text for the primary action button
### primaryButtonProps
- type: Omit&lt;ButtonProps, &#34;dataHook&#34;&gt;
- description: Passed to the primary action button as props without any filter / mutation
### primaryButtonOnClick
- type: () =&gt; void
- description: a callback for when the primary action button is clicked
### secondaryButtonText
- type: ReactNode
- description: a text for the secondary action button
### secondaryButtonProps
- type: Omit&lt;ButtonProps, &#34;dataHook&#34;&gt;
- description: Passed to the secondary button as props without any filter / mutation
### secondaryButtonOnClick
- type: () =&gt; void
- description: callback for when the secondary action button is clicked
### actionsSize
- type: ButtonSize
- description: will determine the action buttons size
### sideActions
- type: ReactNode
- description: side actions node, to be rendered as the first element on the same row as the action buttons
### footnote
- type: ReactNode
- description: a footnote node, to be rendered at the very bottom of the modal
### footnoteSkin
- type: FootnoteSkin
- description: Sets the look and feel of the footnote
### illustration
- type: ReactNode
- description: The illustration src or the illustration node itself
### linkText
- type: ReactNode
- description: When not provided, the primary link will not be rendered
### linkOnClick
- type: () =&gt; void
- description: callback for when the link is clicked
### skin
- type: &#34;standard&#34; | &#34;premium&#34;
- description: a global skin for the modal, will be applied as stylable state and will affect footer buttons skin
### theme
- type: &#34;standard&#34; | &#34;premium&#34;
- description: No description
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### style
- type: CSSProperties
- description: No description
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests.
### closeButtonProps
- type: ModalCloseButtonProps
- description: Close button props.
### helpButtonProps
- type: ModalControlButtonProps
- description: Help button props.
### onCloseButtonClick
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: No description
### onHelpButtonClick
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: No description
### illustrationClassName
- type: string
- description: No description
### headerClassName
- type: string
- description: No description
### footnoteClassName
- type: string
- description: No description
### footerClassName
- type: string
- description: No description
### contentClassName
- type: string
- description: No description
### primaryButtonTooltipProps
- type: Omit&lt;TooltipProps, &#34;children&#34;&gt;
- description: No description


