
### badge
- type: React.ReactNode
- description: Accepts a &lt;Badge/&gt; or any other static indicator. Passed element will be displayed at the top left corner of a card.
### title
- type: React.ReactNode
- description: Set card title.
### subtitle
- type: React.ReactNode
- description: Set card subtitle.
### suffix
- type: React.ReactNode
- description: Accepts any component to be rendered as a suffix of the card&#39;s footer.
### draggable
- type: boolean
- description: Show drag handle
### dragHandleProps
- type: Partial&lt;DragHandleProps&gt;
- description: Extra props to pass to the `&lt;DragHandle /&gt;` element.
### dragging
- type: boolean
- description: Indicates the element is dragging.
### droppable
- type: boolean
- description: Removes buttons when other element is dragging and this card is droppable.
### dragDisabled
- type: boolean
- description: Show disabled drag handle.
### tabIndex
- type: number
- description: Specifies the tab order of the component.
### size
- type: ValuesOf&lt;{ readonly small: &#34;small&#34;; readonly medium: &#34;medium&#34;; }&gt;
- description: Set card size.
### backgroundImageUrl
- type: string
- description: Specifies background image URL.
### backgroundImageNode
- type: React.ReactNode
- description: Accepts any component to be rendered as a background image.
### primaryActionProps
- type: { label?: React.ReactNode; onClick?: React.MouseEventHandler&lt;HTMLDivElement&gt;; disabled?: boolean; disabledMessage?: string; }
- description: Defines properties for the primary action button.
### secondaryActionProps
- type: { label?: React.ReactNode; onClick?: React.MouseEventHandler&lt;HTMLButtonElement&gt;; }
- description: Defines properties for the secondary action button.
### settingsMenu
- type: React.ReactNode
- description: Defines a popover menu to be displayed on hover at the top right corner or a card.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### aspectRatio
- type: string | number
- description: Recommended values:
- Square - 1
- Portrait - 3/4
- Cinema - 16/9
- Landscape - 4/3
- Custom number (e.g. 1.5)
### imagePlacement
- type: &#34;top&#34; | &#34;side&#34;
- description: Sets placement of background image.
### showSuffixOnHover
- type: boolean
- description: Sets suffix behavior to appear only on card hover.
### skin
- type: &#34;standard&#34; | &#34;outlined&#34;
- description: Sets skin to the card item.
### skinVisibility
- type: &#34;always&#34; | &#34;hover&#34;
- description: Sets when the skin is visible.
### footer
- type: React.ReactNode
- description: Accepts any component to be rendered under default footer. Only on imagePlacement &#39;top&#39;.


