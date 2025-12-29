
### show
- type: bool
- description: when set to `true`, notification is shown
### skin
- type: enum
- description: Notification skin
### theme
- type: enum
- description: No description
### type
- type: enum
- description: Sets how &lt;Notification/&gt; should be displayed:
- `type=&#34;global&#34;` will take up space and push the content down.
- `type=&#34;local&#34;` will not take up space and will be displayed on top of content
- `type=&#34;sticky&#34;` will not take up space and will be displayed at the top of whole page and on top of content (position: fixed;)
### autoHideTimeout
- type: number
- description: When provided, then the Notification will be hidden after the specified timeout.
### zIndex
- type: number
- description: Notification z-index
### onClose
- type: func
- description: No description
### children
- type: node
- description: Can be either:
- `&lt;Notification.TextLabel/&gt;` (required)
- `&lt;Notification.CloseButton/&gt;`
- `&lt;Notification.ActionButton/&gt;`


