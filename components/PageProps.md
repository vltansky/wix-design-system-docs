
### children
- type: ReactNode
- description: Accepts compound components as child items:
- `&lt;Page.Header/&gt;`
- `&lt;Page.Content/&gt;`
- `&lt;Page.Tail/&gt;`
- `&lt;Page.Section/&gt;`
- `&lt;Page.Footer/&gt;`
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### backgroundImageUrl
- type: string
- description: Provides a link to the background image source (URL). Image will be displayed at the top of a page, underneath the \&lt;Page.Header/&gt;.
### maxWidth
- type: number
- description: Sets the maximum width of the page (paddings excluded)
### minWidth
- type: number
- description: Sets the minimum width of the page (paddings excluded)
### height
- type: string
- description: Sets the height of the page in pixels (px), viewport height (vh), etc.
### sidePadding
- type: number
- description: Sets the side paddings of a page
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### gradientClassName
- type: string
- description: Specifies a CSS class name that defines a gradient background for \&lt;Page.Header/&gt;
### scrollableContentRef
- type: (ref: HTMLElement) =&gt; void
- description: Defines a reference called together with page scrollable content ref after page mount.
&lt;br/&gt;
**Note** - if you need this ref only for listening to scroll events on the scrollable content then use this prop instead:
`scrollProps = {onScrollChanged/onScrollAreaChanged}`
### zIndex
- type: number
- description: Specifies the stack order (z-index) of a page
### horizontalScroll
- type: boolean
- description: Enables page content to scroll horizontally when its width exceed maximum allowed width
### scrollProps
- type: ScrollableContainerCommonProps
- description: Pass properties related to the scrollable content of the page.
&lt;br/&gt;
**onScrollAreaChanged** - defines a handler function for scroll area changes.
Function is triggered when the user scrolls to a different area of the scrollable content. See signature for possible areas:
`function({area: {y: AreaY, x: AreaX}, target: HTMLElement}) =&gt; void`
`AreaY`: top | middle | bottom | none
`AreaX`: start | middle | end | none (not implemented yet)
&lt;br/&gt;
**onScrollAreaChanged** - defines a general handler for scroll changes with throttling (100ms):
`function({target: HTMLElement}) =&gt; void`


