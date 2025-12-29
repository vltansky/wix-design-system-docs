
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used to create driver in testing.
### hideShadow
- type: boolean
- description: Hide Accordion shadow effect
### contentPadding
- type: &#34;none&#34;
- description: Targets Accordion Item content padding. When not provided, uses default paddings.
### horizontalPadding
- type: HorizontalPaddings
- description: Change horizontal padding
### items
- type: AccordionItemType[]
- description: Provide items
- Available items props:
```javascript
{
render?: func;
title?: React.ReactNode;
subtitle?: React.ReactNode;
icon?: React.ReactNode;
children?: React.ReactNode;
expandLabel?: React.ReactNode;
collapseLabel?: React.ReactNode;
showLabel?: &#39;hover&#39; | &#39;always&#39;;
buttonType?: &#39;textButton&#39; | &#39;button&#39; | &#39;node&#39;;
disabled?: boolean;
onToggle?: React.MouseEventHandler&lt;HTMLElement&gt;;
onMouseEnter?: React.MouseEventHandler&lt;HTMLElement&gt;;
onMouseLeave?: React.MouseEventHandler&lt;HTMLElement&gt;;
open?: boolean;
initiallyOpen?: boolean;
}
```
### multiple
- type: boolean
- description: allow multiple rows to be opened simultaneously
### onAnimationEnter
- type: () =&gt; void
- description: Callback fired immediately after the animation is started
### onAnimationExit
- type: () =&gt; void
- description: Callback fired immediately after the animation is ended
### size
- type: Sizes
- description: Change items size
### skin
- type: Skins
- description: Accordion skin color
### transitionSpeed
- type: TransitionSpeeds
- description: Change expand and collapse animation speed
### titleSize
- type: TitleSizes
- description: Accordion title and subtitle size


