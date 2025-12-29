
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### onCloseButtonClick
- type: func
- description: No description
### onHelpButtonClick
- type: func
- description: No description
### skin
- type: enum
- description: Sets the appearance of modal (i.e., changes the skin of primary and secondary action buttons)
### theme
- type: enum
- description: No description
### title
- type: union
- description: Sets text title for the modal; can be used in conjunction with other components
### subtitle
- type: union
- description: Sets text subtitle for the modal; can be used in conjunction with other components
### content
- type: union
- description: Contains all modal’s content in its middle area. `&lt;CustomModalLayout/&gt;` children are passed as `content`, too.
### actionsSize
- type: custom
- description: Sets the size of action buttons
### primaryButtonText
- type: union
- description: Sets text label or other content (e.g., &lt;Loader/&gt;) for the primary button
### primaryButtonOnClick
- type: func
- description: Defines a call-back function after user clicks on the primary button
### primaryButtonProps
- type: custom
- description: Passes on any `&lt;Button/&gt;` properties on the primary button
### primaryButtonTooltipProps
- type: shape
- description: Passes on any `&lt;Tooltip/&gt;` properties on the primary button tooltip
### secondaryButtonText
- type: union
- description: Sets text label for the secondary button
### secondaryButtonOnClick
- type: func
- description: Defines a call-back function after user clicks on the secondary button
### secondaryButtonProps
- type: custom
- description: Passes on any `&lt;Button/&gt;` properties on the secondary button
### sideActions
- type: node
- description: Contains a checkbox or other components at the start of the footer
### footnote
- type: node
- description: Renders supplementary text or other components at the bottom of the modal
### footnoteSkin
- type: enum
- description: Sets the look and feel of the footnote
### removeContentPadding
- type: bool
- description: Removes 30 px left and right padding from the content area
### width
- type: union
- description: Fixes the width of component; if content area is wider than `width`, it scrolls horizontally
### maxWidth
- type: union
- description: Sets the maximum width of component; if content area is longer than maxWidth, it scrolls horizontally
### height
- type: union
- description: Fixes the height of component
### maxHeight
- type: union
- description: Sets the maximum height of component; if content area is longer than maxHeight, it scrolls vertically
### showHeaderDivider
- type: enum
- description: Controls visibility of a header divider. When set to `auto`, it is shown only when scroll position is greater than 0. When set to `true`, it is always visible, and when set to `false`, it is always hidden.
### showFooterDivider
- type: enum
- description: Controls visibility of a footer divider. When set to `auto`, it is shown up until content is scrolled to the very bottom. When set to `true`, it is always visible, and when set to `false`, it is always hidden.
### overflowY
- type: string
- description: Determines what happens when content overflows component vertically
### style
- type: any
- description: Sets object of CSS styles
### helpButtonProps
- type: shape
- description: Help button props.
### closeButtonProps
- type: shape
- description: Close button props.


