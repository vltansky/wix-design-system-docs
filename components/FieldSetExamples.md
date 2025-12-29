
## Feature Examples


### Structure
- description: <p>A field set consists of <code>legend</code>, <code>suffix</code> and <code>children</code> areas.</p><p></p><p>Children and suffix areas can include any actions or form components.</p>
- example: 
```jsx 
<FieldSet
  legend="Legend"
  suffix={
    <StorybookComponents.Placeholder>Suffix</StorybookComponents.Placeholder>
  }
>
  <StorybookComponents.Placeholder height="36px">
    Children
  </StorybookComponents.Placeholder>
</FieldSet>;
```

### Legend placement
- description: <p>Control the legend position with the <code>legendPlacement</code>. It supports 4 options:</p><li>For all common cases use <code>top</code> (default).</li><li>Use <code>left</code> or <code>right</code> to save vertical space in less spacious layouts. This only works well with short legends. When using, be mindful of localization.</li><li>Use <code>none</code> to visually hide the legend. It will still be available for screen readers.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet legend="Top (default)">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Left" legendPlacement="left">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Right" legendPlacement="right">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Hidden legend" legendPlacement="none">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
</StorybookComponents.Stack>;
```

### Legend alignment
- description: <p>When legend is placed on the side, its vertical position can be controlled with <code>legendAlignment</code>. It supports 2 options:</p><p></p><li>For all common cases use <code>top</code> (default).</li><li>Use <code>middle</code> for single line inputs.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet legend="Top" legendAlignment="top" legendPlacement="left">
    <StorybookComponents.Placeholder height="60px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Middle" legendAlignment="middle" legendPlacement="left">
    <StorybookComponents.Placeholder height="60px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
</StorybookComponents.Stack>;
```

### Required
- description: <p>Mark mandatory field sets with an asterisk by using <code>required</code>.</p>
- example: 
```jsx 
<FieldSet legend="Required" required>
  <StorybookComponents.Placeholder height="36px" />
  <StorybookComponents.Placeholder />
</FieldSet>;
```

### Status and message
- description: <p>To change the status and display a message below the field set, use <code>status</code> and <code>statusMessage</code>. </p><li>For an error message, set the <code>status</code> to <code>error</code>.</li><li>For a warning message, set the <code>status</code> to <code>warning</code>.</li><li>To show helper text, use the <code>statusMessage</code> with no <code>status</code>.  </li><p></p><p><em>Note</em>: to set the status and message for individual child components, use the same props within that component's <code>FormField</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet
    legend="Field set in error state"
    status="error"
    statusMessage="This is an error message."
  >
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>

  <FieldSet
    legend="Field set in warning state"
    status="warning"
    statusMessage="This is a warning message."
  >
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>

  <FieldSet
    legend="Field set in default state"
    statusMessage="This is helper text."
  >
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
</StorybookComponents.Stack>;
```

### Additional info
- description: <p>Use a tooltip to provide users with more information about the field set and what they need to input.</p><p></p><p>To add info icon content use <code>infoContent</code>.</p>
- example: 
```jsx 
<FieldSet
  legend="Hover over info icon"
  infoContent="This tooltip provides additional info about what the user needs to put in the field set elements."
>
  <StorybookComponents.Placeholder height="36px" />
  <StorybookComponents.Placeholder />
</FieldSet>;
```

### Suffix
- description: <p>Add a custom element in the top-right corner of the field set to add extra actions or information. Any component can be used in this area.</p><p></p><p>Or use <code>charCount</code> to show how many characters are left in a text input.</p><p></p><p><em>Note:</em> Choose either <code>charCount</code> or a custom element inside suffix; using both together is not possible.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet
    legend="Custom suffix"
    suffix={
      <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />}>
        Go to External Site
      </TextButton>
    }
  >
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Character count in suffix" charCount={20}>
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
</StorybookComponents.Stack>;
```

### Content direction
- description: <p>Choose how child components are arranged in the field set:</p><p></p><li><code>horizontal</code> (default) arranges them in a row.</li><li><code>vertical</code> arranges them in a column.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet legend="Horizontal" columns="auto 120px">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Vertical" direction="vertical">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder height="36px" width="120px" />
  </FieldSet>
</StorybookComponents.Stack>;
```

### Content alignment
- description: <p>Choose how child components are aligned using <code>alignment</code>.</p><p></p><p>In <code>horizontal</code>:</p><li><code>start</code> (default) aligns to the top.</li><li><code>center</code> aligns to the middle.</li><li><code>end</code> to aligns to the bottom.</li><p></p><p>In <code>vertical</code>:</p><li><code>start</code> (default) aligns to the left.</li><li><code>center</code> aligns to the center.</li><li><code>end</code> to aligns to the right.</li>
- example: 
```jsx 
<Layout>
  <Cell span={6}>
    <Text secondary weight="normal">
      Horizontal direction
    </Text>
  </Cell>
  <Cell span={6}>
    <Text secondary weight="normal">
      Vertical direction
    </Text>
  </Cell>
  <Cell span={6}>
    <FieldSet legend="Start" columns="auto 120px">
      <StorybookComponents.Placeholder height="36px" />
      <StorybookComponents.Placeholder height="18px" />
    </FieldSet>
  </Cell>
  <Cell span={6}>
    <FieldSet legend="Start" direction="vertical">
      <StorybookComponents.Placeholder height="36px" />
      <StorybookComponents.Placeholder height="18px" width="120px" />
    </FieldSet>
  </Cell>
  <Cell span={6}>
    <FieldSet legend="Center" columns="auto 120px" alignment="center">
      <StorybookComponents.Placeholder height="36px" />
      <StorybookComponents.Placeholder height="18px" />
    </FieldSet>
  </Cell>
  <Cell span={6}>
    <FieldSet legend="Center" direction="vertical" alignment="center">
      <StorybookComponents.Placeholder height="36px" />
      <StorybookComponents.Placeholder height="18px" width="120px" />
    </FieldSet>
  </Cell>{' '}
  <Cell span={6}>
    <FieldSet legend="End" columns="auto 120px" alignment="end">
      <StorybookComponents.Placeholder height="36px" />
      <StorybookComponents.Placeholder height="18px" />
    </FieldSet>
  </Cell>
  <Cell span={6}>
    <FieldSet legend="End" direction="vertical" alignment="end">
      <StorybookComponents.Placeholder height="36px" />
      <StorybookComponents.Placeholder height="18px" width="120px" />
    </FieldSet>
  </Cell>
</Layout>;
```

### Content width
- description: <p>Use <code>columns</code> to control the width of each field set child component. Check developer examples for more guidelines.</p><p></p><p><em>Note</em>: <code>columns</code> only works with <code>horizontal</code> direction.</p>
- example: 
```jsx 
<FieldSet legend="Custom content width" columns="auto 120px 60px">
  <StorybookComponents.Placeholder height="36px" />
  <StorybookComponents.Placeholder />
  <StorybookComponents.Placeholder />
</FieldSet>;
```

### Gap
- description: <p>Control the space between field set child components with <code>gap</code>:</p><li>For all common cases use <code>small</code> (default).</li><li>Use <code>medium</code> in more spacious layouts.</li><li>Use <code>large</code> for extra space between components.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet legend="Small gap" gap="small">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Medium gap" gap="medium">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
    <StorybookComponents.Placeholder />
  </FieldSet>
  <FieldSet legend="Large gap" gap="large">
    <StorybookComponents.Placeholder height="36px" />
    <StorybookComponents.Placeholder />
    <StorybookComponents.Placeholder />
  </FieldSet>
</StorybookComponents.Stack>;
```




## Developer Examples


### Custom content width
- description: <p>Set the width of each child component using <code>columns</code>.</p><p></p><li>Use <code>min-content</code> to make the child component as narrow as possible.</li><li>Use <code>auto</code> to make the child component fill in all available space.</li><li>Use <code>px</code> to set the component's width.</li><li>Use <code>fr</code> to set the column proportions. For example, use <code>1fr 1fr</code> for equal width child components and <code>1fr 3fr</code> to make the first child fill 25% and second to fill 75% of available width.</li><li>Use a combination of all 4 values to create custom content layouts.</li><p></p><p><em>Note</em>: Do not use percentage values as they will cause child components to exceed the field set width.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FieldSet
    legend="Opacity and color"
    columns="auto 90px min-content"
    alignment="center"
  >
    <Slider
      displayMarks={false}
      gradientColor="purple"
      min={0}
      max={100}
      value={50}
    />
    <Input value="50" suffix={<Input.Affix>%</Input.Affix>} />
    <FillButton fill="purple" tooltipContent="Pick a color" />
  </FieldSet>
  <FieldSet
    legend="Assign color to a team"
    columns="auto min-content"
    alignment="center"
  >
    <Dropdown placeholder="Select a team" />
    <FillButton fill="purple" tooltipContent="Pick a color" />
  </FieldSet>
  <FieldSet
    legend="Select a time range"
    alignment="end"
    columns="1fr 1fr min-content"
  >
    <FormField label="From">
      <TimeInput value={new Date()} />
    </FormField>
    <FormField label="To">
      <TimeInput value={new Date()} />
    </FormField>
    <IconButton priority="secondary">
      <Icons.Edit />
    </IconButton>
  </FieldSet>
</StorybookComponents.Stack>;
```


    


## Common Use Case Examples


### In setting panels
- description: <p>Use field sets to group related form components together and give them a title.</p><p></p><p>When individual component labels are descriptive enough, set field set <code>legendPlacement</code> to <code>none</code>.</p>
- example: 
```jsx 
() => {
  const [backgroundOpacity, setBackgroundOpacity] = React.useState(100)
  const [textOpacity, setTextOpacity] = React.useState(100)
  const [hasPublishPeriod, setHasPublishPeriod] = React.useState(true)

  const changeBackgroundOpacity = (value) => {
    setBackgroundOpacity(value)
  }

  const changeTextOpacity = (value) => {
    setTextOpacity(value)
  }

  const items = [
    {
      id: 0,
      label: 'Crop & Rotate',
      icon: <Icons.Crop />,
    },
    {
      id: 1,
      label: 'Enhance',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      label: 'Settings',
      icon: <Icons.Settings />,
    },
  ]

  const renderBackgroundSidePanel = () => {
    return (
      <SidePanel width="480px" onCloseButtonClick={() => {}}>
        <SidePanel.Header title="Settings" showDivider={true} />
        <SidePanel.Content noPadding>
          <SidePanel.Field>
            <FieldSet
              legend="Background color"
              columns="30px auto 72px"
              alignment="center"
            >
              <Box>
                <FillPreview fill="#B7EEFF" />
              </Box>
              <Box marginRight="12px">
                <Slider
                  displayMarks={false}
                  gradientColor="#B7EEFF"
                  min={0}
                  max={100}
                  value={backgroundOpacity}
                  onChange={changeBackgroundOpacity}
                />
              </Box>
              <Input
                value={backgroundOpacity}
                suffix={<Input.Affix>%</Input.Affix>}
                size="small"
                onChange={(e) => changeBackgroundOpacity(e.target.value)}
              />
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <FieldSet
              legend="Text color"
              columns="30px auto 72px"
              alignment="center"
            >
              <Box>
                <FillPreview fill="#454B46" />
              </Box>
              <Box marginRight="12px">
                <Slider
                  displayMarks={false}
                  gradientColor="#454B46"
                  min={0}
                  max={100}
                  value={textOpacity}
                  onChange={changeTextOpacity}
                />
              </Box>
              <Input
                value={textOpacity}
                suffix={<Input.Affix>%</Input.Affix>}
                size="small"
                onChange={(e) => changeTextOpacity(e.target.value)}
              />
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <FieldSet
              legend="Background photo"
              columns="auto min-content min-content"
              alignment="center"
            >
              <Box marginRight="12px">
                <Image src="running_man.png" />
              </Box>
              <Button priority="secondary" size="small">
                Replace
              </Button>
              <Tooltip content="Delete image">
                <IconButton priority="secondary" size="small">
                  <Icons.DeleteSmall />
                </IconButton>
              </Tooltip>
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Section title="Publish period">
            <SidePanel.Field divider={false}>
              <FormField labelPlacement="left" label="Set publish period">
                <ToggleSwitch
                  checked={hasPublishPeriod}
                  onChange={() => setHasPublishPeriod(!hasPublishPeriod)}
                  size="small"
                />
              </FormField>
            </SidePanel.Field>
            <SidePanel.Field>
              {hasPublishPeriod && (
                <FieldSet
                  legend="Publish period"
                  legendPlacement="none"
                  columns="1fr 1fr"
                >
                  <FormField label="From">
                    <DatePicker
                      width="100%"
                      value={new Date()}
                      size="small"
                      popoverProps={{ appendTo: 'window' }}
                    />
                  </FormField>
                  <FormField label="To">
                    <DatePicker
                      width="100%"
                      value={new Date()}
                      size="small"
                      popoverProps={{ appendTo: 'window' }}
                    />
                  </FormField>
                </FieldSet>
              )}
            </SidePanel.Field>
          </SidePanel.Section>
        </SidePanel.Content>
      </SidePanel>
    )
  }

  const renderCreateStep = () => (
    <>
      <ComposerSidebar labelPlacement="bottom" items={items} selectedId={2} />
      {renderBackgroundSidePanel()}

      <Box backgroundColor="D70" width="100%">
        <Box width="100%" padding={4}>
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center" height="100%">
              <Text>Composer content area</Text>
            </Box>
          </StorybookComponents.Placeholder>
        </Box>
      </Box>
    </>
  )

  return (
    <Layout gap={0}>
      <Cell>
        <ComposerHeader backButtonValue="Manage Album">
          <ComposerHeader.Actions justifyContent="end">
            <Button priority="secondary">Preview</Button>
            <Button>Publish</Button>
          </ComposerHeader.Actions>
        </ComposerHeader>
      </Cell>
      <Cell>
        <Box direction="vertical">
          <Box gap="0" height="800px">
            {renderCreateStep()}
          </Box>
        </Box>
      </Cell>
    </Layout>
  )
}

```


