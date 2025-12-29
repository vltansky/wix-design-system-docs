
### dataHook
- type: string
- description: applied as data-hook HTML attribute that can be used to create driver in testing
### open
- type: boolean
- description: when false - items should not be rendered in the DOM.
### children
- type: ReactNode
- description: the content of the drawer
### resizable
- type: boolean
- description: shows handle and enables expand/collapse functionality
### snapPoints
- type: (string | number)[]
- description: the snap points of the drawer
### dismissible
- type: boolean
- description: whether the drawer should be dismissible by clicking outside of it
### backdrop
- type: boolean
- description: only controls the color of the backdrop. Meaning if the backdrop=false, the overlay is still present preventing clicks on the content behind the backdrop, just invisible.
### renderBackdrop
- type: boolean
- description: controls whether the backdrop overlay is rendered at all. When false, the overlay element is not rendered in the DOM.
### margin
- type: boolean
- description: the margin around the Drawer content box (spacing between box and screen)
### onClose
- type: (open: boolean) =&gt; void
- description: fires when (1) overlay is clicked (outside click) and (2) when is in collapsed position and being dragged towards the anchor side and (3) Esc key press.
### ariaLabelledBy
- type: string
- description: a11y: Sets the aria-labelledby attribute on the drawer content
### role
- type: AriaRole
- description: wai-aria role
### zIndex
- type: ZIndex
- description: z-index of the drawer
### scrollable
- type: boolean
- description: Whether the drawer content should be wrapped in a scrollable container, by default it is true. If false, the drawer content will be rendered as is, without any scrollable container.
### repositionInputs
- type: boolean
- description: When true Vaul will reposition inputs rather than scroll then into view if the keyboard is in the way. Setting it to false will fall back to the default browser behavior.


