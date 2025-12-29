
### animateOnLoad
- type: boolean
- description: Shows enter animation on component mount.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests.
### children
- type: ReactNode
- description: Allows to render any component as a child item.
### enterAnimation
- type: EnterAnimation
- description: Sets a type of animation that happens on enter animation.
 - fadeIn -
```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;enterEasing&#39; | &#39;standardEasing&#39;;
 }
 ```
 - moveIn -
 ```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   direction:
     | &#39;topToBottom&#39;
     | &#39;bottomToTop&#39;
     | &#39;leftToRight&#39;
     | &#39;rightToLeft&#39;;
   distance: string;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;enterEasing&#39; | &#39;standardEasing&#39;;
 }
 ```
 - expand -
 ```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   direction:
     | &#39;topToBottom&#39;
     | &#39;bottomToTop&#39;
     | &#39;leftToRight&#39;
     | &#39;rightToLeft&#39;;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;enterEasing&#39; | &#39;standardEasing&#39;;
 }
 ```
 - scaleUp -
 ```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   direction:
     | &#39;center&#39;
     | &#39;top&#39;
     | &#39;topEnd&#39;
     | &#39;right&#39;
     | &#39;bottomEnd&#39;
     | &#39;bottom&#39;
     | &#39;bottomStart&#39;
     | &#39;left&#39;
     | &#39;topStart&#39;;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;enterEasing&#39; | &#39;standardEasing&#39;;
   scale: string;
 }
 ```
### exitAnimation
- type: ExitAnimation
- description: Sets a type of animation that happens on exit animation.
 - fadeOut -
 ```javascript
{
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;exitEasing&#39; | &#39;standardEasing&#39;;
 }
 ```
 - moveOut -
 ```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   direction:
     | &#39;topToBottom&#39;
     | &#39;bottomToTop&#39;
     | &#39;leftToRight&#39;
     | &#39;rightToLeft&#39;;
   distance: string;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;exitEasing&#39; | &#39;standardEasing&#39;
 }
 ```
 - collapse -
 ```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   direction:
     | &#39;topToBottom&#39;
     | &#39;bottomToTop&#39;
     | &#39;leftToRight&#39;
     | &#39;rightToLeft&#39;;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;exitEasing&#39; | &#39;standardEasing&#39;;
 }
 ```
 - scaleDown -
 ```javascript
 {
   delay?: &#39;short&#39; | &#39;medium&#39; | &#39;long&#39;;
   direction:
     | &#39;center&#39;
     | &#39;top&#39;
     | &#39;topEnd&#39;
     | &#39;right&#39;
     | &#39;bottomEnd&#39;
     | &#39;bottom&#39;
     | &#39;bottomStart&#39;
     | &#39;left&#39;
     | &#39;topStart&#39;;
   duration:
     | &#39;fast01&#39;
     | &#39;fast02&#39;
     | &#39;medium01&#39;
     | &#39;medium02&#39;
     | &#39;slow01&#39;
     | &#39;slow02&#39;;
   easing?: &#39;exitEasing&#39; | &#39;standardEasing&#39;;
   scale: string;
 }
 ```
### mountOnEnter
- type: boolean
- description: Lazy-mounts the component. If false, will be mounted immediately. It true, will be mounted with first enter.
### onStart
- type: (animationTiming?: AnimationTiming) =&gt; void
- description: Defines a callback function which is called immediately after the animation starts. animationTiming notes if the animation is enter or exit.
### onEnd
- type: (animationTiming?: AnimationTiming) =&gt; void
- description: Defines a callback function which is called immediately after the animation ends. animationTiming notes if the animation is enter or exit.
### show
- type: boolean
- description: Shows animation when set to true.
### unmountOnExit
- type: boolean
- description: Unmounts the component after it finishes exiting. If false, will stay mounted after exit.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.


