
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### description
- type: string
- description: Sets a short description for the page
### descriptionMaxLines
- type: number
- description: Truncates description text at a specific number of lines
### favicon
- type: string
- description: Specifies an URL link to favicon source. If not provided, a fallback favicon will be displayed.
### onDescriptionClick
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function triggered when description is clicked
### onDescriptionMouseEnter
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Defines a callback function which is called when cursor enters the description
### onDescriptionMouseLeave
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Defines a callback function which is called when cursor leaves the description
### onTitleClick
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function triggered when title is clicked
### onTitleMouseEnter
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Defines a callback function which is called when cursor enters the title
### onTitleMouseLeave
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Defines a callback function which is called when cursor leaves the title
### onWebsiteInfoClick
- type: MouseEventHandler&lt;HTMLElement&gt;
- description: Callback function triggered when website info section (favicon, site name and preview URL) is clicked
### previewUrl
- type: string
- description: Sets the link for the site
### siteName
- type: string
- description: Sets the site name of the website
### skin
- type: &#34;light&#34; | &#34;transparent&#34;
- description: Sets widget background color
### title
- type: string
- description: Sets the title of the page
### titleMaxLines
- type: number
- description: Truncates title text at a specific number of lines
### websiteInfoTooltipContent
- type: React.ReactNode
- description: When provided, a tooltip will be displayed on website info section (favicon, site name and preview URL) hover
### websiteInfoTooltipProps
- type: Partial&lt;TooltipCommonProps&gt;
- description: Allows to pass tooltip common props to website info tooltip.


