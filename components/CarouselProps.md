
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### images
- type: array
- description: Defines an array of objects where each contains the `src` of an image (in `&lt;img src=&#34;your_src&#34; /&gt;`)
### imagesPosition
- type: string
- description: Sets the image&#39;s position
### imagesFit
- type: enum
- description: Sets the image’s fit
### children
- type: node
- description: Accepts any component as a child item. Most commonly used to display `&lt;Card/&gt;`,  `&lt;Image/&gt;` or video files.
### buttonSkin
- type: enum
- description: Sets the skin of the control (next / previous) buttons
### showControlsShadow
- type: bool
- description: Drops a shadow below the control buttons
### infinite
- type: bool
- description: Loops images endlessly
### autoplay
- type: bool
- description: Auto-plays images
### dots
- type: bool
- description: Controls if the bottom dots are visible or hidden
### variableWidth
- type: bool
- description: Shows one slide at a time (default) or stacks one slide after another horizontally
### initialSlideIndex
- type: number
- description: Sets the slide to start a presentation with
### afterChange
- type: func
- description: Index change callback. `index =&gt; ...`
### beforeChange
- type: func
- description: Index change callback. `(oldIndex, newIndex) =&gt; ...`
### controlsPosition
- type: enum
- description: Sets the control buttons’ position
### controlsSize
- type: enum
- description: Sets the control buttons’ size
### controlsStartEnd
- type: enum
- description: Controls if the next / previous control buttons are visible, hidden or disabled at the start and end of the slideshow
### gradientColor
- type: string
- description: Controls gradient color when controlsPosition set to overlay
### gradient
- type: bool
- description: Enables gradient on when controlsPosition set to overlay


