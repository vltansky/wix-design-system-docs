
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### actions
- type: node
- description: component to be displayed in header strip to preform actions relevant to the displayed content
### title
- type: string
- description: title text to be displayed in the header strip
### children
- type: node
- description: modal content displayed mid-screen
### onClose
- type: func
- description: callback for when the modal is closed
### shouldCloseOnOverlayClick
- type: bool
- description: boolean to determine whether closing the overlay on click
### closeButtonTooltipText
- type: node
- description: Tooltip close button text
### prevButtonProps
- type: shape
- description: Previous button props
##### onClick signature:
function(childIndexDisplayed: number) =&gt; void
* `childIndexDisplayed`: the index of the child component displayed.
### nextButtonProps
- type: shape
- description: Next button props
##### onClick signature:
function(childIndexDisplayed: number) =&gt; void
* `childIndexDisplayed`: the index of the child component displayed.
### startDisplayingAtChildIndex
- type: number
- description: Pass an index to start rendering from a specific child component.
### skin
- type: enum
- description: Controls the skin of the component
### closeButtonAriaLabel
- type: string
- description: ARIA label for close button


