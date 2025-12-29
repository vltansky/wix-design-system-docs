
### skin
- type: EmptyStateSkin
- description: Sets the style skin for the empty state
### theme
- type: EmptyStateSkin
- description: No description
### title
- type: ReactNode
- description: Sets the content for the title
### subtitle
- type: ReactNode
- description: Sets the content for the subtitle
### image
- type: string | ReactElement&lt;any, string | JSXElementConstructor&lt;any&gt;&gt;
- description: Contains the empty state image. Can be either a string representing the image URL, or a node to render.
### children
- type: ReactNode
- description: Contains components rendered below the subtitle, e.g., `&lt;Button/&gt;` or `&lt;TextButton/&gt;`
### classNames
- type: { imageContainer?: string; }
- description: Sets the empty state image bottom margin. If not specified, use the default padding defined in the CSS.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute to be used in the tests
### align
- type: EmptyStateAlign
- description: Sets the alignment of all empty state contents within the component container
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.


