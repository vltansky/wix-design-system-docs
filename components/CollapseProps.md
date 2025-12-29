
### dataHook
- type: string
- description: Adds a `data-hook` attribute for testing purposes.
### position
- type: &#34;static&#34; | &#34;sticky&#34;
- description: Determines if the collapse stays fixed at the top of its container.
### open
- type: boolean
- description: Determines whether the collapse is open.
### mountOnEnter
- type: boolean
- description: Delays mounting the component until it is displayed.
If `false`, the component mounts immediately. If `true`, it mounts on first display.
### unmountOnExit
- type: boolean
- description: Unmounts the component after it finishes exiting. If `false`, the component stays mounted after exit.
### onExpandAnimationEnd
- type: (animationTiming?: AnimationTiming) =&gt; void
- description: Triggered when the expand animation completes.
### onCollapseAnimationEnd
- type: (animationTiming?: AnimationTiming) =&gt; void
- description: Triggered when the collapse animation completes.
### children
- type: React.ReactNode
- description: Content to render inside the collapse.


