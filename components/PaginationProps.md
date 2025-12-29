
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### totalPages
- type: number
- description: Sets a number of available pages to show in the component
### currentPage
- type: number
- description: Specifies a currently selected page
### onChange
- type: (event: { event: SyntheticEvent&lt;Element, Event&gt;; page: number; }) =&gt; void
- description: Defines a callback function which returns a selected page or an arrow ({`event`,`page`})
### pageUrl
- type: (pageNumber: number) =&gt; string
- description: Get pageNumber and returns url
### nextLabel
- type: string
- description: Sets next page label
### previousLabel
- type: string
- description: Sets previous page label
### focusableOnFocus
- type: React.FocusEventHandler&lt;E&gt;
- description: No description
### focusableOnBlur
- type: React.FocusEventHandler&lt;E&gt;
- description: No description
### ref
- type: React.RefObject&lt;E&gt;
- description: No description


