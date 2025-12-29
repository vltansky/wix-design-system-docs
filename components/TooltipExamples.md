
## Feature Examples


### Structure
- description: <p>To display a tooltip, two parts need to be defined:</p><li>A trigger element that calls a tooltip when hover or focus occurs (e.g., an <code><IconButton/></code>). The trigger element goes inside the <code><Tooltip/></code> wrapper as its child item.</li><li>The <code>content</code>, which is the text displayed inside of a tooltip.</li>
- example: 
```jsx 
<Tooltip inline content="Tooltip content goes here.">
  <TextButton>Hover or focus to see tooltip</TextButton>
</Tooltip>

```

### Size
- description: <p>Control tooltip dimensions with the <code>size</code> prop:</p><li>For dense layouts (e.g., in a composer), use <code>small</code>.</li><li>The default size used in any other case is <code>medium</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Tooltip inline content="This is a small tooltip." size="small">
    <TextButton>Small tooltip</TextButton>
  </Tooltip>
  <Tooltip inline content="This is a medium (default) tooltip.">
    <TextButton>Medium tooltip</TextButton>
  </Tooltip>
</StorybookComponents.Stack>;
```

### Max width
- description: <p>Control tooltip width with <code>maxWidth</code>. When the maximum width is reached, text inside the tooltip will wrap onto multiple lines.</p><p></p><p>Default <code>maxWidth</code> is <code>204</code> px.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Tooltip
    inline
    content="This is a tooltip with content wrapped using the default max width."
  >
    <TextButton>Default max width</TextButton>
  </Tooltip>
  <Tooltip
    inline
    content="This is a tooltip with content wrapped using 360px max width."
    maxWidth={360}
  >
    <TextButton>Max width = 360 px</TextButton>
  </Tooltip>
</StorybookComponents.Stack>

```

### Placement
- description: <p>Use the <code>placement</code> prop to select the position of a tooltip in relation to its trigger element:</p><li><code>top</code> (default)</li><li><code>right</code></li><li><code>bottom</code></li><li><code>left</code></li><p></p><p>In each of these standard positions, the tooltip aligns itself to the center of the corresponding axis and appears outside the trigger element.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" alignItems="center">
  <Tooltip inline content="Top (default)">
    <TextButton>Top (default)</TextButton>
  </Tooltip>
  <Box gap="24">
    <Tooltip inline content="Left" placement="left">
      <TextButton>Left</TextButton>
    </Tooltip>
    <Tooltip inline content="Right" placement="right">
      <TextButton>Right</TextButton>
    </Tooltip>
  </Box>
  <Tooltip inline content="Bottom" placement="bottom">
    <TextButton>Bottom</TextButton>
  </Tooltip>
</StorybookComponents.Stack>

```

### Text alignment
- description: <p>The <code>textAlign</code> prop controls how tooltip content is aligned:</p><li><code>start</code> (default) </li><li><code>center</code> </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Tooltip inline content="Content is aligned to the left (default).">
    <TextButton>Start (default)</TextButton>
  </Tooltip>
  <Tooltip inline content="Content is aligned to the center." textAlign="center">
    <TextButton>Center</TextButton>
  </Tooltip>
</StorybookComponents.Stack>

```

### Delay
- description: <p>Delay the showing or hiding of a tooltip, for a specific amount of time, by using <code>enterDelay</code> and <code>exitDelay</code>.</p><p></p><p>Delay times are counted by milliseconds and both are 0 by default.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Tooltip inline content="Tooltip was shown after 450 ms." enterDelay={450}>
    <TextButton>Enter delay</TextButton>
  </Tooltip>
  <Tooltip inline content="Tooltip will fade after 450 ms." exitDelay={450}>
    <TextButton>Exit delay</TextButton>
  </Tooltip>
</StorybookComponents.Stack>

```

### Interactive
- description: <p>Decide whether tooltip can be hovered on not by using <code>interactive</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Tooltip
    inline
    content={
      <Box direction="vertical">
        <Text size="small" skin="light">
          This is an interactive tooltip.
        </Text>
        <TextButton size="small" skin="standard-light">
          Learn more
        </TextButton>
      </Box>
    }
  >
    <TextButton>Interactive</TextButton>
  </Tooltip>
  <Tooltip
    inline
    interactive={false}
    content="This is a non-interactive tooltip."
  >
    <TextButton>Non-Interactive</TextButton>
  </Tooltip>
</StorybookComponents.Stack>

```

### On disabled trigger elements
- description: <p>By default, disabled trigger elements (e.g., <code><Button disabled/></code>) do not show tooltips on mouse hover or keyboard focus.</p><p></p><p>To show a tooltip on mouse hover, set the <code>disabled</code> prop to <code>false</code>.</p><p></p><p><em>Note</em>: such tooltip content will not be accessible to keyboard focus, so it's best not to use tooltip to give additional information on a disabled component. Instead, use <code><InfoIcon/></code>, <code><Text/></code> <a href="https://www.wix-style-react.com/storybook/?path=/story/components-form--infoicon"></a><a href="https://www.wix-style-react.com/storybook/?path=/story/components-typography-text--text"></a>or other components near the disabled component.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Tooltip inline content="Tooltip content will not be shown">
    <TextButton disabled>No tooltip (default)</TextButton>
  </Tooltip>
  <Tooltip
    inline
    content="Tooltip content is shown on mouse hover"
    disabled={false}
  >
    <TextButton disabled>Tooltip on mouse hover</TextButton>
  </Tooltip>
</StorybookComponents.Stack>

```




    


## Common Use Case Examples


### To label icon buttons
- description: <p>Show a text label or other brief helpful information for an <code><IconButton/></code><a href="https://www.wix-style-react.com/storybook/?path=/story/components-actions--iconbutton"></a> in a tooltip.</p>
- example: 
```jsx 
<Card>
  <Box direction="horizontal">
    <Image
      height="120px"
      width="180px"
      borderRadius="8px 0px 0px 8px"
      src="running_man.png"
    />
    <Box
      direction="vertical"
      borderRadius="0px 8px 8px 0px"
      verticalAlign="space-between"
      padding="18px 24px"
      backgroundColor="D80"
      flexGrow={1}
    >
      <Box verticalAlign="space-between" flexGrow={1}>
        <Box direction="vertical" gap="3px">
          <Heading size="small">Running for beginners program</Heading>
          <Text size="small" secondary>
            Scheduled | 57 days
          </Text>
        </Box>
        <Tooltip content="Edit program">
          <IconButton priority="secondary" size="small">
            <Icons.Edit />
          </IconButton>
        </Tooltip>
      </Box>
      <Box marginRight={3}>
        <Text size="small" secondary>
          Created on September 26, 2022
        </Text>
      </Box>
    </Box>
  </Box>
</Card>;
```


