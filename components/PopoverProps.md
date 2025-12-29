
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### placement
- type: Placement
- description: The location to display the content
### shown
- type: boolean
- description: Is the content shown or not
### onClick
- type: MouseEventHandler&lt;HTMLDivElement&gt;
- description: onClick on the component
### onClickOutside
- type: (event: Event) =&gt; void
- description: Provides callback to invoke when clicked outside of the popover
### onTabOut
- type: (event: KeyboardEvent) =&gt; void
- description: Provides callback to invoke when popover loses focus
### onEscPress
- type: KeyboardEventHandler&lt;HTMLDivElement&gt;
- description: Provides callback to invoke when popover loses focus
### excludeClass
- type: string
- description: Clicking on elements with this excluded class will will not trigger onClickOutside callback
### onMouseEnter
- type: MouseEventHandler&lt;HTMLDivElement&gt;
- description: onMouseEnter on the component
### onMouseLeave
- type: MouseEventHandler&lt;HTMLDivElement&gt;
- description: onMouseLeave on the component
### onKeyDown
- type: KeyboardEventHandler&lt;HTMLDivElement&gt;
- description: onKeyDown on the target component
### showArrow
- type: boolean
- description: Show show arrow from the content
### flip
- type: boolean
- description: Whether to enable the flip behaviour. This behaviour is used to flip the `&lt;Popover/&gt;`&#39;s placement
when it starts to overlap the target element (`&lt;Popover.Element/&gt;`).
### fixed
- type: boolean
- description: Whether to enable the fixed behaviour. This behaviour is used to keep the `&lt;Popover/&gt;` at it&#39;s
original placement even when it&#39;s being positioned outside the boundary.
### moveBy
- type: Partial&lt;{ x: number; y: number; }&gt;
- description: Moves popover relative to the parent
### hideDelay
- type: number
- description: Hide Delay in ms
### showDelay
- type: number
- description: Show Delay in ms
### moveArrowTo
- type: number
- description: Moves arrow by amount
### appendTo
- type: AppendTo
- description: Enables calculations in relation to a dom element
### timeout
- type: number | { enter: number; exit: number; }
- description: Animation timer
### style
- type: object
- description: Inline style
### id
- type: string
- description: Id
### fluid
- type: boolean
- description: No description
### customArrow
- type: (placement: Placement, arrowProps: object) =&gt; ReactNode
- description: Custom arrow element
### role
- type: string
- description: target element role value
### zIndex
- type: ZIndex
- description: popover z-index
### dynamicWidth
- type: boolean
- description: popovers content is set to minimum width of trigger element,
but it can expand up to the value of maxWidth.
### minWidth
- type: string | number
- description: popover content minWidth value
- `number` value which converts to css with `px`
- `string` value that contains `px`
### maxWidth
- type: string | number
- description: popover content maxWidth value
- `number` value which converts to css with `px`
- `string` value that contains `px`
### width
- type: string | number
- description: popover content width value
- `number` value which converts to css with `px`
- `string` value that contains `px`
### disableClickOutsideWhenClosed
- type: boolean
- description: Breaking change:
When true - onClickOutside will be called only when popover content is shown
### dataHook
- type: string
- description: Hook for testing purposes.
### tabIndex
- type: number
- description: tabindex for popover content element
### aria-label
- type: string
- description: No description
### aria-labelledby
- type: string
- description: No description
### aria-describedby
- type: string
- description: No description
### animate
- type: boolean
- description: Whether to animate the popover content when it is shown or hidden.
### skin
- type: PopoverSkin
- description: Components skin value. Can be dark or light.
### theme
- type: PopoverSkin
- description: No description
### onShow
- type: () =&gt; void
- description: Callback to invoke when popover is shown
### onHide
- type: () =&gt; void
- description: Callback to invoke when popover is hidden
### interactive
- type: boolean
- description: Enables hovering the popover content.
### overlay
- type: ReactNode
- description: Enables overlay for content.


