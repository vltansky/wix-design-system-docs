
## Feature Examples


### Fill
- description: <p>Render preview content with <code>fill</code> prop. It accepts:</p><li>colors</li><li>gradients</li><li>colors with opacity</li><li>images</li><li>SVGs</li>
- example: 
```jsx 
<StorybookComponents.Stack width="24px">
  <FillPreview size="medium" fill="#3399ff" />
  <FillPreview
    size="medium"
    fill="linear-gradient(to right top, #3399ff, #ffffff)"
  />
  <FillPreview size="medium" fill={['rgba(0, 0, 0, 0.2)', 'rgba(0, 0, 0, 1)']} />
  <FillPreview
    size="medium"
    fill="https://images.unsplash.com/photo-1559825481-12a05cc00344?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8b2NlYW58ZW58MHx8MHx8&auto=format&fit=crop&w=500&q=60"
  />
  <FillPreview size="medium" fill={<Icons.HomeSmall />} />
</StorybookComponents.Stack>;
```

### Multiple colors
- description: <p>Display up to four selected colors in the fill preview. Use the <code>fill</code> prop to pass definitions for up to four colors, including those with opacity. This feature is useful for visualizing selections that involve semi-transparent colors.</p><p></p><p><strong>Note</strong>: Each color segment is not individually interactive, the entire element is a single clickable area to ensure a sufficient hit target.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="24px">
  <FillPreview aspectRatio={1} fill="#3399ff" size="medium" />
  <FillPreview
    aspectRatio={1}
    fill={['rgba(51, 153, 255, 0.4)', '#3399ff']}
    size="medium"
  />
  <FillPreview
    aspectRatio={1}
    fill={['rgb(0, 0, 0, 0.3)', 'rgb(0, 0, 0, 1)', '#59A96A']}
    size="medium"
  />
  <FillPreview
    aspectRatio={1}
    fill={['#E1F0C4', '#9BDEAC', '#636940', '#59A96A']}
    size="medium"
  />
</StorybookComponents.Stack>;
```

### Size
- description: <p>Control the component size with the size prop. The component supports <strong>five</strong> <strong>sizes</strong>:</p><p></p><li><code>extraTiny</code> – use in very dense layouts for display purposes only. Keep in mind that this size does not provide a sufficient clickable area, so use it sparingly.</li><li><code>tiny</code> – use in tight layouts where space is limited.</li><li><code>small</code> – use to display rows of color selections. This size is also used in other components, such as <code><ColorPicker/></code>.</li><li><code>medium</code> – use in design settings panels.</li><li><code>large</code> – use in spacious layouts, especially when only a few <FillPreview/> components are present.</li>
- example: 
```jsx 
<StorybookComponents.Stack width="24px">
  <FillPreview size="extraTiny" fill="#3399ff" />
  <FillPreview size="tiny" fill="#3399ff" />
  <FillPreview size="small" fill="#3399ff" />
  <FillPreview size="medium" fill="#3399ff" />
  <FillPreview size="large" fill="#3399ff" />
</StorybookComponents.Stack>;
```

### Preview ratio
- description: <p>Control preview ratio with the <code>aspectRatio</code> prop. By default, the component maintains a 1:1 ratio when the width of parent container is defined.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="24px">
  <FillPreview aspectRatio={1 / 4} fill="#3399ff" />
  <FillPreview aspectRatio={1 / 3} fill="#3399ff" />
  <FillPreview aspectRatio={1 / 2} fill="#3399ff" />
  <FillPreview aspectRatio={1} fill="#3399ff" />
</StorybookComponents.Stack>;
```

### States
- description: <p>Control the component state with:</p><li><code>selected</code> - use to highlight active selection.</li><li><code>disabled</code> - use to highlight unavailable option.</li>
- example: 
```jsx 
<StorybookComponents.Stack gap="18px">
  <StorybookComponents.Stack gap="24px" flexDirection="column">
    <FillPreview />
    <FillPreview fill="#3399ff" />
    <FillPreview fill="#3399ff" selected />
    <FillPreview fill="#3399ff" disabled />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack gap="24px" flexDirection="column">
    <StorybookComponents.Stack height="24px" alignItems="center">
      No value
    </StorybookComponents.Stack>
    <StorybookComponents.Stack height="24px" alignItems="center">
      Filled
    </StorybookComponents.Stack>
    <StorybookComponents.Stack height="24px" alignItems="center">
      Selected
    </StorybookComponents.Stack>
    <StorybookComponents.Stack height="24px" alignItems="center">
      Disabled
    </StorybookComponents.Stack>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Render as
- description: <p>Render the preview as another component or DOM tag.</p>
- example: 
```jsx 
<StorybookComponents.Stack gap="18px">
  <StorybookComponents.Stack gap="24px" flexDirection="column">
    <FillPreview fill="#73d2de" as="a" />
    <FillPreview fill="#3399ff" as="button" />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack gap="24px" flexDirection="column">
    <StorybookComponents.Stack height="24px" alignItems="center">
      <p>Rendered as <a/> tag</p>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack height="24px" alignItems="center">
      <p>Rendered as native <button/> tag</p>
    </StorybookComponents.Stack>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Fill type
- description: <p>Use fill preview to show the options of gradient fill types in forms.</p>
- example: 
```jsx 
() => {
  const [inputValue, setInputValue] = React.useState('#ffffff');
  const [selected, setSelected] = React.useState(0);
  const [fillType, setFillType] = React.useState();

  const solidColors = ['#ffbc42', '#d81159', '#8f2d56', '#218380', '#73d2de'];
  const gradientColors = [
    'linear-gradient(45deg, rgba(14,0,255,1) 0%, rgba(0,212,255,1) 80%)',
    'linear-gradient(45deg, rgba(34,193,195,1) 0%, rgba(253,187,45,1) 100%)',
    'linear-gradient(to right top, #dbfd2d, #dd7c00)',
    'linear-gradient(to right, #00dd83, #22a0c3)',
    'linear-gradient(to right, #aa99ff, #aa11ff)',
  ];

  const renderFillPreview = ({ content, color, index }) => (
    <Tooltip appendTo="scrollParent" content={content}>
      <Box width="30px">
        <FillPreview
          selected={selected === index}
          onClick={() => setSelected(index)}
          fill={color}
        />
      </Box>
    </Tooltip>
  );

  return (
    <Card>
      <Card.Header title="Header style" />
      <Card.Divider />
      <Card.Content>
        <Layout>
          <Cell span={6}>
            <FormField label="Background fill type">
              <SegmentedToggle
                defaultSelected="gradient"
                selected={fillType}
                onClick={(_, value) => setFillType(value)}
              >
                <SegmentedToggle.Button value="solid">
                  Solid
                </SegmentedToggle.Button>
                <SegmentedToggle.Button value="gradient">
                  Gradient
                </SegmentedToggle.Button>
              </SegmentedToggle>
            </FormField>
          </Cell>
          <Cell span={6}>
            <FormField label="Background gradient">
              <Box gap="12px" height="36px" verticalAlign="middle">
                {fillType === 'solid'
                  ? solidColors.map((color, index) =>
                      renderFillPreview({
                        content: 'Solid color',
                        color,
                        index,
                      }),
                    )
                  : gradientColors.map((color, index) =>
                      renderFillPreview({
                        content: 'Gradient color',
                        color,
                        index,
                      }),
                    )}
              </Box>
            </FormField>
          </Cell>
          <Cell span={12}>
            <FormField label="Text color">
              <ColorInput value={inputValue} onConfirm={setInputValue} />
            </FormField>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};
```

### Color selection
- description: <p>Use <code><FillPreview/></code> to let users select a color for different items.</p>
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
              <Button
                priority="secondary"
                size="small"
                suffixIcon={<Icons.TextSmall></Icons.TextSmall>}
              >
                Heading 1
              </Button>
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
      <SidePanel.Field>
        <FieldSet
          legend="Background color"
          legendSize="small"
          legendPlacement="top"
          alignment="center"
          columns="30px auto 67px"
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
        </SidePanel.Content>
      </Box>
    </SidePanel>
  );
};
```


