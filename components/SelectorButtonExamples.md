
## Feature Examples


### Size
- description: <p>Control selector button <code>size</code> with size prop:</p><li><code>large</code> is best for calls to action that require more emphasis.</li><li><code>medium</code> is for layouts where other medium sized elements are used.</li><li><code>small</code> is default for panels. Provides more compact UI layout.</li><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack 
  width="240px"
  flexDirection="column"
  >
 <SelectorButton
  fullWidth
  size="large"
  suffixIcon={<Icons.Link />}
  > Large 
</SelectorButton>
   <SelectorButton 
  fullWidth
  size="medium"
  suffixIcon={<Icons.Link />}
  > Medium 
</SelectorButton>
     <SelectorButton 
  fullWidth
  size="small"
  suffixIcon={<Icons.LinkSmall />}
  > Small 
</SelectorButton>
</StorybookComponents.Stack>;
```

### Suffix
- description: <p>Add more context to actions with suffix icons:</p><li>Indicate that an action will open a popover or navigate users to another page with a <code>suffixIcon</code>.</li><li>Use suffix to indicate what type of action the button does. </li><p></p>
- example: 
```jsx 
<StorybookComponents.Stack
  flexDirection="column"
  width="240px">
 <SelectorButton
  fullWidth
  size="medium"
  suffixIcon={<Icons.Text />}
  > Heading 1 
</SelectorButton>
   <SelectorButton
  fullWidth
  size="medium"
  suffixIcon={<Icons.Link />}
  > Choose a link 
</SelectorButton>
  </StorybookComponents.Stack> 
```

### Disabled
- description: <p>To disable a button, use the <code>disabled</code> prop which indicates a button can't be selected.</p>
- example: 
```jsx 
<StorybookComponents.Stack
  flexDirection="column"
  width="240px">
 <SelectorButton
  disabled
  fullWidth
  size="medium"
  suffixIcon={<Icons.Add/>}
  > Disabled 
</SelectorButton>
  </StorybookComponents.Stack> 
```

### Text overflow
- description: <p>Use the <code>ellipsis</code> prop for overflow text. The full text will be displayed in a <code><Tooltip/> </code>when a user hovers over the button. Control the style of the tooltip using the <code>tooltipProps</code>.</p><p></p><p><em>Note</em>: Try to avoid lengthy action labels. CTA text should be short and clear – one to two words, or max three for specific use cases.</p>
- example: 
```jsx 
<StorybookComponents.Stack
  flexDirection="column"
  width="240px">
 <SelectorButton
  ellipsis
  fullWidth
  size="medium"
  suffixIcon={<Icons.Link/>}
  > This is a very long label that does not fit inside a button 
</SelectorButton>
  </StorybookComponents.Stack> 
```

### Full width
- description: <p>Use the <code>fullWidth</code> prop to fill the button to 100% of the parent container.</p>
- example: 
```jsx 
 <SelectorButton
  fullWidth
  ellipsis
  size="medium"
  suffixIcon={<Icons.Add/>}
  > Full width 
</SelectorButton>
```




    


## Common Use Case Examples


### Font picker in panels
- description: <p>Use the Selector Button in app settings panels to provide an entry point for opening a font picker.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(50);
  const [opacity, setOpacity] = React.useState(100);
  return (
    <SidePanel
      skin="floating"
      width="420px"
      onCloseButtonClick
      onHelpButtonClick
    >
      <SidePanel.Header title="Wix Comments" />
      <Box height="480px">
        <VerticalTabs size="small" activeTabId={2} onChange={() => {}}>
          <VerticalTabs.TabItem id={0}>Display</VerticalTabs.TabItem>
          <VerticalTabs.TabItem id={1}>Layout</VerticalTabs.TabItem>
          <VerticalTabs.TabItem id={2}>Design</VerticalTabs.TabItem>
          <VerticalTabs.TabItem id={3}>Text</VerticalTabs.TabItem>
        </VerticalTabs>
        <Divider direction="vertical" />
        <SidePanel.Content noPadding>
          <SidePanel.Field>
            <Button
              priority="secondary"
              size="tiny"
              prefixIcon={<Icons.ChevronLeft />}
            >
              Back
            </Button>
          </SidePanel.Field>
          <SidePanel.Field>
            <FieldSet legend="Text font and color" columns="auto 30px">
  <SelectorButton fullWidth size="small" suffixIcon={<Icons.TextSmall />}>
    {'Heading 1'}
  </SelectorButton>
              <FillPreview fill="#839788" aspectRatio={1} />
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <FieldSet gap="small" legend="Border width" columns="auto 72px">
              <Slider
                onChange={setValue}
                min={0}
                max={100}
                value={value}
                displayMarks={false}
              />
              <Input
                value={value}
                size="small"
                suffix={<Input.Affix>px</Input.Affix>}
                onChange={(e) => setValue(e.target.value)}
              />
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Section title="Divider">
            <SidePanel.Field>
              <FieldSet
                legend="Color"
                legendSize="small"
                legendPlacement="top"
                alignment="center"
                columns="30px auto 72px"
              >
                <FillPreview fill="#000000" aspectRatio={1} />
                <Box margin="0 8px">
                <Slider
                  gradientColor="#000000"
                  min={0}
                  max={100}
                  displayMarks={false}
                  onChange={(value) => setOpacity(value)}
                  value={opacity}
                />
                </Box>
                <NumberInput
                  value={opacity}
                  min={0}
                  max={100}
                  onChange={(value) => setOpacity(value)}
                  suffix={<Input.Affix>%</Input.Affix>}
                  size="small"
                  hideStepper
                />
              </FieldSet>
            </SidePanel.Field>
          </SidePanel.Section>
        </SidePanel.Content>
      </Box>
    </SidePanel>
  );
};

```

### Panels with links
- description: <p>Use the Selector Button in panels to provide an entry point for opening the link settings panel.</p>
- example: 
```jsx 
<SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px">
  <SidePanel.Header title="Button settings" />
  <SidePanel.Content noPadding>
 
    <SidePanel.Field>
      <FormField label="Text">
        <Input placeholder="Add button text" size="small" />
      </FormField>
    </SidePanel.Field>
    <SidePanel.Field>
      <FormField label="Name">
  <SelectorButton fullWidth size="small" suffixIcon={<Icons.LinkSmall />}>
    {'Choose a link '}
  </SelectorButton>
      </FormField>
    </SidePanel.Field>
  </SidePanel.Content>
</SidePanel>;
```


