
### children
- type: ReactNode
- description: Renders modal content
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used to create driver in testing
### isOpen
- type: boolean
- description: Controls if modal is open or closed
### borderRadius
- type: number
- description: Border radius of modal
### contentLabel
- type: string
- description: a11y: The value of contentLabel is set as an aria-label on the modal element. This helps assistive technology, like screen readers, to add a label to an element that would otherwise be anonymous
### zIndex
- type: number
- description: Controls z-index of the modal overlay
### shouldCloseOnOverlayClick
- type: boolean
- description: Enables to close modal when mouse clicked on overlay area
### shouldDisplayCloseButton
- type: boolean
- description: Displays a close button on the top right corner of the overlay
### onRequestClose
- type: (event?: MouseEvent&lt;Element, MouseEvent&gt; | KeyboardEvent&lt;Element&gt;) =&gt; void
- description: Callback that will be executed when the modal is requested to be closed, prior to actually closing
### onAfterOpen
- type: () =&gt; void
- description: Callback that will be executed after the modal has been opened
### onAfterClose
- type: () =&gt; void
- description: Callback that will be executed after the modal has been closed
### horizontalPosition
- type: ModalHorizontalPosition
- description: Horizontal position of the modal
### verticalPosition
- type: ModalVerticalPosition
- description: Vertical position of the modal
### closeTimeoutMS
- type: number
- description: Number indicating the milliseconds to wait before closing the modal
### scrollable
- type: boolean
- description: Specifies if modal portal supports scroll
### scrollableContent
- type: boolean
- description: Specifies if modal content should become scrollable when modal size will fit the window
### maxHeight
- type: string
- description: Sets the maximum height for a scrollable content
### height
- type: string
- description: Sets the height for modal&#39;s content container
### overlayPosition
- type: ModalOverlayPosition
- description: css position of the modal overlay
### parentSelector
- type: () =&gt; HTMLElement
- description: A function that returns a DOM element on which the modal should be appended to
### appElement
- type: string
- description: Selector specifying where to apply the aria-hidden attribute
### onOk
- type: () =&gt; void
- description: No description
### screen
- type: ModalScreen
- description: Specifies minimum spacing between full viewport and modal content
### showNavigationPreviousButton
- type: boolean
- description: Enable navigation previous buttons to the side of the content and listen on clicks by using onNavigationClickPrevious
### showNavigationNextButton
- type: boolean
- description: Enable navigation next button to the side of the content and listen on clicks by using onNavigationClickNext
### onNavigationClickPrevious
- type: () =&gt; void
- description: Callback that will be executed when the navigation control previous is clicked
### onNavigationClickNext
- type: () =&gt; void
- description: Callback that will be executed when the navigation control next is clicked
### navigationPreviousLabel
- type: string
- description: Label used for navigation control previous button tooltip
### navigationNextLabel
- type: string
- description: Label used for navigation control next button tooltip
### transition
- type: ModalTransition
- description: Transition animation type. Note that moveHorizontal/moveVertical transitions work best with FullScreenModalLayout.


