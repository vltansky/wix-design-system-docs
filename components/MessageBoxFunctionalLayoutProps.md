
### dataHook
- type: string
- description: applied as data-hook HTML attribute that can be used to create driver in testing
### hideFooter
- type: boolean
- description: Hides the footer that contains the action buttons
### confirmText
- type: ReactNode
- description: Defines the main action button text
### confirmPrefixIcon
- type: IconElement
- description: Add a prefix icon for the main action button
### confirmSuffixIcon
- type: IconElement
- description: Add a suffix icon for the main action button
### cancelText
- type: ReactNode
- description: Defines the secondary action button text
### cancelPrefixIcon
- type: IconElement
- description: Add a prefix icon for the secondary action button
### cancelSuffixIcon
- type: IconElement
- description: Add a suffix icon for the secondary action button
### theme
- type: MessageBoxFunctionalLayoutTheme
- description: modal theme color
### onOk
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: Called when the main action (confirm) is clicked
### onCancel
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: Called when the secondary action (cancel) is clicked
### onClose
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: Called when the close button is clicked
### width
- type: string
- description: Specify exact width
### margin
- type: string
- description: Specify exact margin. Use to fine tune position inside other elements.
When used inside `&lt;Modal&gt;`, beware that `&lt;Modal&gt;` is a flex container, therefore specific flex item CSS rules apply for this margin.
### title
- type: ReactNode
- description: Defines the modals&#39;s header title
### children
- type: ReactNode
- description: The content to be displayed. can be text or some node
### maxHeight
- type: string | number
- description: Max height. When supplied - will allow internal scroll to the component
### buttonsHeight
- type: ButtonSize
- description: Defines the buttons size
### closeButton
- type: boolean
- description: Show/hide the close button
### disableCancel
- type: boolean
- description: Defines the secondary action button
### disableConfirmation
- type: boolean
- description: Defines the main action button
### noBodyPadding
- type: boolean
- description: Removes the content padding. Used in custom modal that defines it&#39;s own padding
### footerBottomChildren
- type: ReactNode
- description: A render slot to display a foot note
### fullscreen
- type: boolean
- description: Stretches the component to a full screen mode (with some padding)
### withEmptyState
- type: boolean
- description: Changes the internal padding to be used with `&lt;EmptyState/&gt;` component
### sideActions
- type: ReactNode
- description: Used to display some side component in the footer, for example `&lt;Checkbox/&gt;`
### image
- type: ReactNode
- description: Used to display an illustration on the left side


