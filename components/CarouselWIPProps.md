
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### children
- type: ReactNode
- description: Any element to render inside
### images
- type: CarouselWIPImage[]
- description: Array of objects where each contains the `src` of an image (in \&lt;img src=&#34;your_src&#34; /\&gt;)
### controlsSkin
- type: &#34;standard&#34; | &#34;inverted&#34; | &#34;light&#34; | &#34;transparent&#34;
- description: Sets the skin of the arrow buttons
### showControlsShadow
- type: boolean
- description: Show a shadow for the carousel controls
### infinite
- type: boolean
- description: Images loop endlessly
### initialSlideIndex
- type: number
- description: An index of the slide to start on
### afterChange
- type: (index: number) =&gt; void
- description: Index change callback. `index =&gt; ...`
### beforeChange
- type: (oldIndex: number, newIndex: number) =&gt; void
- description: Index change callback. `(oldIndex, newIndex) =&gt; ...`
### controlsPosition
- type: &#34;sides&#34; | &#34;overlay&#34; | &#34;bottom&#34; | &#34;none&#34;
- description: Sets the arrows position
### controlsSize
- type: &#34;medium&#34; | &#34;tiny&#34; | &#34;small&#34;
- description: Sets the arrows position
### controlsStartEnd
- type: &#34;disabled&#34; | &#34;hidden&#34;
- description: Configure the start and end controls to be shown disabled or hidden. Relevant when infinite prop is set to false.
### slidingType
- type: &#34;align-to-start&#34; | &#34;reveal-one&#34; | &#34;reveal-chunk&#34;
- description: Sliding behaviour type for the carousel
### startEndOffset
- type: number
- description: Number of pixels for showing &#34;peeking&#34; cards on the edges of the carousel
### gutter
- type: number
- description: Number of pixels dividing between slides
### sidesGradientColor
- type: string
- description: Color for the gradients on the sides of the carousel
### imagesPosition
- type: string
- description: Sets the images position
### imagesFit
- type: &#34;none&#34; | &#34;fill&#34; | &#34;contain&#34; | &#34;cover&#34; | &#34;scale-down&#34;
- description: Sets the images fit
### autoplay
- type: boolean
- description: Auto-playing of images
### hideDots
- type: boolean
- description: Hide dots
### variableWidth
- type: boolean
- description: 🚧 Variable width of children
### animationDuration
- type: number
- description: Animation duration
### easing
- type: (t: number) =&gt; number
- description: Animation function


