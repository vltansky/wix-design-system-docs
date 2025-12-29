
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### title
- type: ReactNode
- description: title node to be displayed in the header strip
### stickyTitle
- type: boolean
- description: If true, the title will be sticky to the top of the modal
### content
- type: ReactNode
- description: content node to be displayed
### footer
- type: ReactNode
- description: footer node to be displayed
### stickyFooter
- type: boolean
- description: If true, the footer will be sticky to the bottom of the modal
### onOverlayClick
- type: () =&gt; void
- description: callback for when there&#39;s a click on the overlay (in case the modal in not fullscreen)
### onCloseButtonClick
- type: MouseEventHandler&lt;HTMLButtonElement&gt;
- description: callback for when the the close button is clicked.  **Note**: if this prop is not provided, then the close button will not be shown.
### fullscreen
- type: boolean
- description: If true, the modal will take all of the screen


