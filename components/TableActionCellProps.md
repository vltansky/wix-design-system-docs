
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests.
### primaryAction
- type: union
- description: Controls the behaviour and appearance of a primary action:
   - `text` specifies action label
   - `skin` &lt;b&gt;deprecated&lt;/b&gt; property that was previously used to control the visual appearance of a button. It has been replaced by the visibility property, which switches skin properties automatically based on visibility options.
   - `onClick` defines a callback function which is called on button click
   - `disabled` restrict user interactions
   - `prefixIcon` add an icon in front of a button label
   - `suffixIcon` add an icon after button label
   - `as` renders button as another component or a DOM tag
   - `dataHook` applies a data-hook HTML attribute to be used in the tests
   - `disabledDescription` indicates an explanatory text string to display in tooltip when action is visible and disabled
   - `tooltipProps` controls the tooltip appearance
   - `visibility` specifies whether the primary action button is visible. When the value is set to &#34;onHover&#34;, the button is only visible when the mouse hovers over it, and it appears as a primary button. When the value is set to &#34;always&#34;, the button is always visible and appears as a secondary button.
   - `priority` specifies the button priority (only for array format)
### secondaryActions
- type: arrayOf
- description: Controls the behaviour and appearance of secondary actions:

   Action object containing
   - `text` specifies action label to be shown in the tooltip or popover menu
   - `icon` specifies icon of an action
   - `onClick` defines a callback function which is called on button click
   - `subtitle` a subtitle for the action
   - `disabled` restrict user interactions
   - `dataHook` applies a data-hook HTML attribute to be used in the tests
   - `disabledDescription` indicates an explanatory text string to display in tooltip when action is visible and disabled
   - `tooltipProps` controls the tooltip appearance
   - `skin` controls the skin of the item

   OR Divider object containing
   - `divider` displays a divider between the action items in popover menu
### numOfVisibleSecondaryActions
- type: number
- description: Specifies the number of secondary actions to display outside of the popover menu
### alwaysShowSecondaryActions
- type: bool
- description: Specifies whether secondary actions should be visible all the time. By default secondary actions are visible on row hover only.
### alwaysShowPrimaryActions
- type: bool
- description: Specifies whether primary actions should be visible all the time. By default primary actions are visible on row hover only.
### moreActionsTooltipText
- type: string
- description: Sets the tooltip text of more actions icon button
### moreActionsProps
- type: shape
- description: Controls the appearance of the more actions icon button
### popoverMenuProps
- type: shape
- description: Controls the appearance of secondary actions menu with all common popover menu props
### size
- type: enum
- description: Controls the size of action buttons
### onClick
- type: any
- description: No description


