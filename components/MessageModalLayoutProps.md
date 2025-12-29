
### title
- type: ReactNode
- description: Sets text title for the modal; can be used in conjunction with other components.
### subtitle
- type: ReactNode
- description: Sets text subtitle for the modal; can be used in conjunction with other components.
### content
- type: ReactNode
- description: Contains modal’s message in its middle area. &lt;MessageModalLayout/&gt; children are passed as content, too.
### primaryButtonText
- type: ReactNode
- description: Sets text label for the primary button.
### primaryButtonProps
- type: Omit&lt;ButtonProps, &#34;dataHook&#34;&gt;
- description: Passes on any \&lt;Button/\&gt; properties on the primary button.
### primaryButtonOnClick
- type: () =&gt; void
- description: Defines a call-back function after user clicks on the primary button.
### secondaryButtonText
- type: ReactNode
- description: Sets text label for the secondary button.
### secondaryButtonProps
- type: Omit&lt;ButtonProps, &#34;dataHook&#34;&gt;
- description: Passes on any \&lt;Button/\&gt; properties on the secondary button.
### secondaryButtonOnClick
- type: () =&gt; void
- description: Defines a call-back function after user clicks on the secondary button.
### actionsSize
- type: ButtonSize
- description: Determines the action buttons size.
### sideActions
- type: ReactNode
- description: Contains a checkbox or other components at the start of the footer.
### footnote
- type: ReactNode
- description: Renders supplementary text or other components at the bottom of the modal.
### footnoteSkin
- type: FootnoteSkin
- description: Sets the look and feel of the footnote.
### illustration
- type: ReactNode
- description: Contains a 120x120 px illustration at the left side of the modal.
### theme
- type: ModalSkin
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
### skin
- type: ModalSkin
- description: a global skin for the modal, will be applied as stylable state and will affect footer buttons skin.
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


