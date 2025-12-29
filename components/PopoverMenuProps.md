
### triggerElement
- type: ReactNode | FC&lt;PopoverTriggerElementProps&gt;
- description: Defines a component that calls out a Popover menu (`&lt;IconButton /&gt;`, `&lt;Button /&gt;` or `&lt;Text Button /&gt;`)
### children
- type: ReactNode
- description: Stores Popover menu compound components:
- &lt;PopoverMenu.MenuItem /&gt;
- &lt;PopoverMenu.Divider /&gt; (optional)
- &lt;PopoverMenu.SectionTitle /&gt; (optional)

`&lt;PopoverMenu.MenuItem&gt;` component has these fields:
 * `text` - Sets a label for a Popover menu item
 * `onClick` - Defines a callback function which is called when a Popover menu item is clicked on
 * `skin` - Controls the appearance of a Popover menu item (one of `standard`, `dark`, `destructive`)
 * `prefixIcon` - Contains an icon at the start of a Popover menu item
 * `dataHook` - Applies a data-hook HTML attribute to be used in the tests
 * `suffixIcon` - suffix icon property
 * `disabled` - Disables a Popover menu item
 * `subtitle` - Sets a text for a Popover menu item subtitle\

`&lt;PopoverMenu.Divider&gt;` component has these fields:
* `dataHook` - Applies a data-hook HTML attribute to be used in the tests

`&lt;PopoverMenu.SectionTitle&gt;` component has these fields:
* `dataHook` - Applies a data-hook HTML attribute to be used in the tests
* `title` - Acts as a title for following list items.
### maxWidth
- type: MaxWidth&lt;string | number&gt;
- description: Sets a maximum width for a Popover menu
### minWidth
- type: MinWidth&lt;string | number&gt;
- description: Sets a minimum width for a Popover menu
### maxHeight
- type: string | number
- description: Sets a maximum height for a Popover menu
### zIndex
- type: number
- description: Sets the Popover z-index
### moveBy
- type: MoveByOffset
- description: Moves Popover menu overlay relative to its trigger element by a defined number of px:
- horizontally (on X-axis)
- or vertically (on Y-axis)
### placement
- type: Placement
- description: Defines the Popover menu’s overlay placement in relation to its trigger element:
* auto-start
* auto
* auto-end
* top-start
* top
* top-end
* right-start
* right
* right-end
* bottom-start
* bottom
* bottom-end
* left-start
* left
* left-end
### textSize
- type: &#34;small&#34; | &#34;medium&#34;
- description: Sets the size of text in Popover menu items
### ellipsis
- type: boolean
- description: Truncates menu item text that overflows component’s max Width
### fluid
- type: boolean
- description: Allows truncating the trigger element to a specified parent container width.
### appendTo
- type: AppendTo
- description: Enables calculations in relation to a DOM element
### flip
- type: boolean
- description: Enables the flip behaviour. This behaviour is used to flip the overlay placement when it starts to overlap the trigger element.
### fixed
- type: boolean
- description: Enables the fixed behaviour. This behaviour is used to keep the overlay at its original placement even when it is being positioned outside the boundary.
### showArrow
- type: boolean
- description: Controls visibility of the pointer arrow
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### onHide
- type: () =&gt; void
- description: Defines a callback function which is called when a Popover menu is closed
### onShow
- type: () =&gt; void
- description: Defines a callback function which is called when a Popover menu is opened
### fixedFooter
- type: ReactNode
- description: A fixed footer to the list
### RefAttributes
- type: All props from RefAttributes that comes from @types/react/index.d.ts
- description: No description
### Attributes
- type: All props from Attributes that comes from @types/react/index.d.ts
- description: No description


