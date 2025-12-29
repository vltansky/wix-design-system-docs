
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests.
### children
- type: ReactNode
- description: Allows to render any component as a child item.
### menuArrow
- type: boolean
- description: Specifies whether input should have a dropdown menu arrow on the right side.
### focused
- type: boolean | &#34;auto&#34;
- description: Controls visual focus state.
### size
- type: ValuesOf&lt;{ readonly tiny: &#34;tiny&#34;; readonly small: &#34;small&#34;; readonly medium: &#34;medium&#34;; readonly large: &#34;large&#34;; }&gt;
- description: Controls the size of the input. Default value: `medium`
### placeholder
- type: ReactNode
- description: Sets a placeholder message to display
### as
- type: &#34;button&#34; | &#34;div&#34;
- description: Renders the component as button.
Renders the component as div.
### disabled
- type: boolean
- description: Specifies whether user interactions are disabled.
### tabIndex
- type: number
- description: Indicates that element can be focused and where it participates in sequential keyboard navigation.
### aria-haspopup
- type: boolean | &#34;menu&#34; | &#34;listbox&#34; | &#34;tree&#34; | &#34;grid&#34; | &#34;dialog&#34; | &#34;true&#34; | &#34;false&#34;
- description: Indicates the element can trigger a popup and what kind of popup will be displayed.
### aria-controls
- type: string
- description: Identifies the element whose contents or presence are controlled by the component.
### onClick
- type: MouseEventHandler&lt;HTMLButtonElement&gt; | MouseEventHandler&lt;HTMLDivElement&gt;
- description: A callback function called on component click.


