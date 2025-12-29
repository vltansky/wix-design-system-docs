
## Feature Examples


### Range
- description: Specify a range of a slider by defining `min` and `max` values.
- example: 
```jsx 

<Slider min={1} max={20} value={3} />;

```

### Values
- description: Specifies what `value` slider will represent:<br/>
        &emsp;- `number` (default) - use it to select value within a given range.<br/>
        &emsp;- `array` - use it to select a range of values within a given range.
- example: 
```jsx 

<StorybookComponents.Stack flexDirection="column">
  <Slider min={0} max={50} value={10} />
  <Slider min={0} max={50} value={[10, 25]} />
</StorybookComponents.Stack>;

```

### Start point
- description: Control the starting point of a slider with `startPoint` prop.
        A default starting point is a minimum value from a defined range.
- example: 
```jsx 

<StorybookComponents.Stack flexDirection="column">
  <Slider startPoint={0} min={0} max={50} />
  <Slider startPoint={0} min={-25} max={25} />
</StorybookComponents.Stack>;

```

### Marks
- description: Use marks to indicate allowed selections that slider thumb will snap to.
        Marks are enabled by default, but can be hidden using `displayMarks` prop.<br/>
        <br/>
        Default marks display numeric values of start and end of a range.
- example: 
```jsx 

<StorybookComponents.Stack flexDirection="column">
  <Slider min={0} max={50} displayMarks={true} />
  <Slider min={0} max={50} displayMarks={false} />
</StorybookComponents.Stack>;

```

### Marks label alignment
- description: <p>Control mark label alignment with the <code>marksLabelAlignment</code> prop, choose between:</p><p></p><li><code>center (default)</code> - marks title will overflow outside slider bounds.</li><li><code>inside</code> - marks will be aligned inside slider edges.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Slider min={-100} max={100} marksLabelAlignment="center" />
  <Slider min={-100} max={100} marksLabelAlignment="inside" />
</StorybookComponents.Stack>;
```

### Custom marks
- description: Define custom marks for each accepted selection value via `marks` prop. It accepts numeric or string values.
- example: 
```jsx 

() => {
  const marks = {
    0: '$20',
    1: '$40',
    2: '$80',
    3: '$160',
    4: '$300',
    5: '$500',
  };

  return <Slider marks={marks} min={0} max={5} />;
};

```

### Step
- description: Define a step to reduce the amount of accepted values within a range.
        Default step is 1 and might not work well for larger value ranges, such as 1-1000. 
- example: 
```jsx 

<Slider min={0} max={100} step={10} />;

```

### Direction
- description: <p>Sets the slider’s orientation:</p><p><code>horizontal</code> (default) — renders along the x‑axis.</p><p><code>vertical</code> — renders along the y‑axis, useful for tight or tall layouts.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Slider min={0} max={50} direction="horizontal" />
  <Box height="150px"><Slider min={0} max={5} direction="vertical" /></Box>
</StorybookComponents.Stack>;
```

### Pushable &amp; crossing handles
- description: Control whether range slider handles should cross or push one another. By default handles are allowed to cross.
        If `pushable` prop is set, moving the handle on top of another one will move the whole selected range.
- example: 
```jsx 

() => {
  const [firstValue, setFirstValue] = React.useState([10, 25]);
  const [secondValue, setSecondValue] = React.useState([15, 30]);

  return (
    <StorybookComponents.Stack flexDirection="column">
      Crossing handles
      <Slider onChange={setFirstValue} min={0} max={50} value={firstValue} />
      Pushable handles
      <Slider
        onChange={setSecondValue}
        min={0}
        max={50}
        value={secondValue}
        pushable={5}
      />
    </StorybookComponents.Stack>
  );
};

```

### Opacity
- description: <p>Use slider to control the opacity of a selected color with <code>gradientColor</code> prop.</p><p></p><p>Pass any color in color names, RGB or HEX formats.</p>
- example: 
```jsx 
<Slider gradientColor="#229954" displayMarks={false} />;
```

### Disabled
- description: Disable all slider interactions with `disabled` prop. Use it to highlight a temporary unavailable function.
- example: 
```jsx 

<Slider min={1} max={10} disabled />;

```




    


## Common Use Case Examples


### Editable slider
- description: <p>Let users enter an exact value with an editable text field. </p>
- example: 
```jsx 

() => {
  const [value, setValue] = React.useState(50);

  return (
    <Layout>
      <Cell>
        <FormField label="Opacity">
          <Box gap="12px">
            <Box display="block" width="100%">
              <Slider
                onChange={setValue}
                min={0}
                max={100}
                value={value}
                displayMarks={false}
              />
            </Box>
            <Box width="60px">
              <Input value={value} onChange={e => setValue(e.target.value)} />
            </Box>
          </Box>
        </FormField>
      </Cell>
    </Layout>
  );
};

```

### Color opacity
- description: <p>Use slider with the <code>gradientColor</code> prop to control the opacity of a selected color.</p>
- example: 
```jsx 
() => {
  const [isPopoverOpen, setIsPopoverOpen] = React.useState(false);
  const [color, setColor] = React.useState('#B7EEFF');
  const [backgroundOpacity, setBackgroundOpacity] = React.useState(100);

  const changeBackgroundOpacity = (value) => {
    setBackgroundOpacity(value);
  };

  return (
    <FieldSet
      legend="Background color"
      columns="auto 72px 30px"
      alignment="center"
    >
      <Box marginRight="12px">
        <Slider
          displayMarks={false}
          gradientColor={color}
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
      <Box>
        <Popover
          showArrow
          shown={isPopoverOpen}
          appendTo="window"
          onClick={() => setIsPopoverOpen(!isPopoverOpen)}
          onClickOutside={() => setIsPopoverOpen(false)}
        >
          <Popover.Element>
            <FillPreview fill={color} />
          </Popover.Element>
          <Popover.Content>
            <ColorPicker
              value={color}
              onCancel={() => setShown(!shown)}
              onConfirm={(value) => {
                setIsPopoverOpen(false);
                setColor(value.hex());
              }}
              onChange={() => {}}
            />
          </Popover.Content>
        </Popover>
      </Box>
    </FieldSet>
  );
};
```

### Composer
- description: <p>Use sliders in a composer to let users adjust a variety of settings such as opacity, brightness, border radius, border weight, etc.</p>
- example: 
```jsx 

() => {
  const renderSlider = ({ icon, text, initialValue }) => {
    const [value, setValue] = React.useState(initialValue);
    return (
      <FormField
        label=<Box verticalAlign="middle" gap="SP1">
          {icon}
          <Text>{text}</Text>
        </Box>
      >
        <Slider
          onChange={setValue}
          startPoint={0}
          min={-50}
          max={50}
          value={value}
          displayMarks={false}
        />
      </FormField>
    );
  };

  return (
    <SidePanel>
      <SidePanel.Header title="Adjust" />
      <SidePanel.Content>
        <Layout>
          <Cell>
            <Text size="small">Light & Color</Text>
          </Cell>
          <Cell>
            {renderSlider({
              icon: <Icons.BrightnessSmall />,
              text: 'Brightness',
              initialValue: -30,
            })}
          </Cell>
          <Cell>
            {renderSlider({
              icon: <Icons.ContrastSmall />,
              text: 'Contrast',
              initialValue: 25,
            })}
          </Cell>
          <Cell>
            {renderSlider({
              icon: <Icons.HighlightsSmall />,
              text: 'Highlights',
              initialValue: 25,
            })}
          </Cell>
          <Cell>
            {renderSlider({
              icon: <Icons.ShadowsSmall />,
              text: 'Shadows',
              initialValue: 0,
            })}
          </Cell>
        </Layout>
      </SidePanel.Content>
    </SidePanel>
  );
};

```

### Form
- description: <p>Use a slider in a form to let users select a range of values, such as minimum and maximum values.  </p><p></p>
- example: 
```jsx 

() => {
  const [value, setValue] = React.useState({ min: 4, max: 12 });
  return (
    <Card>
      <Card.Header title="Party Size" />
      <Card.Divider />
      <Card.Content>
        <Layout>
          <Cell span={3}>
            <Box gap="12px">
              <FormField label="Min">
                <Input
                  value={value.min}
                  onChange={e => setValue({ ...value, min: e.target.value })}
                />
              </FormField>
              <FormField label="Max">
                <Input
                  value={value.max}
                  onChange={e => setValue({ ...value, max: e.target.value })}
                />
              </FormField>
            </Box>
          </Cell>
          <Cell span={9}>
            <FormField>
              <Slider
                onChange={val => setValue({ min: val[0], max: val[1] })}
                min={1}
                max={20}
                value={[value.min, value.max]}
              />
            </FormField>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};

```

### Design panel
- description: <p>Use sliders to let users control color opacity and border width in a design panel.</p><li>Use a slider with the <code>gradientColor</code> prop to let users control the opacity of a selected color.</li><li>Let users enter an exact border width using an editable text field. </li>
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


