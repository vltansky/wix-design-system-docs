
## Feature Examples


### Size
- description: <p>Adjust the component's size using the <code>size</code> prop.  Three sizes are supported:</p><li><code>large</code> is the default used in form layouts.</li><li><code>medium</code> is for card headers and dense layouts.</li><li><code>small</code> should only be used in very concentrated layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ToggleSwitch size="large" checked />
  <ToggleSwitch size="medium" checked />
  <ToggleSwitch size="small" checked />
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Style the component using the <code>skin</code> prop. Four skins are supported:</p><li><code>standard</code> is the default used for all common cases.</li><li><code>success</code> can be used to highlight that a toggle is "available" or "successfully working."</li><li><code>error</code> highlights that a value is destructive or invalid.</li><li><code>urgent</code> highlights the switch for extra attention.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ToggleSwitch skin="standard" checked />
  <ToggleSwitch skin="success" checked />
  <ToggleSwitch skin="error" checked />
  <ToggleSwitch skin="urgent" checked />
</StorybookComponents.Stack>;
```

### States
- description: <p>Disable the component with the <code>disabled</code> prop.</p><p></p><p>Use the <code>checked</code> prop to show a toggle switch is "on." </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack>
    <FormField label="Default" stretchContent={false} labelPlacement="right">
      <ToggleSwitch />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <FormField label="Checked" stretchContent={false} labelPlacement="right">
      <ToggleSwitch checked />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <FormField label="Checked Disabled" stretchContent={false} labelPlacement="right">
      <ToggleSwitch checked disabled />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <FormField label="Disabled" stretchContent={false} labelPlacement="right">
      <ToggleSwitch disabled />
    </FormField>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the toggle switch by wrapping it in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<FormField status="error" statusMessage="This is an error message.">
  <ToggleSwitch />
</FormField>;
```




    


## Common Use Case Examples


### With a label
- description: <p>Wrap toggle switch in <code><FormField/></code> to:</p><li>Give it a <code>label</code>.</li><li>Mark it as <code>required</code>.</li><li>Give additional information in the hover tooltip.</li>
- example: 
```jsx 
() => {
  const [toggleChecked, setToggleChecked] = React.useState(true);

  return (
    <Box>
      <FormField
        labelPlacement="right"
        label="Label"
        required
        infoContent="This tooltip provides some additional info about the control."
        stretchContent={false}
      >
        <ToggleSwitch
          checked={toggleChecked}
          onChange={() => setToggleChecked(!toggleChecked)}
        />
      </FormField>
    </Box>
  );
};
```

### Settings
- description: <p>Use toggle switch to turn settings on and off.</p>
- example: 
```jsx 
() => {
  const renderListItem = ({ title, subtitle, padding, toggleChecked }) => {
    const [checked, setChecked] = React.useState(toggleChecked);

    return (
      <Box verticalAlign="middle" align="space-between" padding={padding}>
        <Box direction="vertical">
          <Text weight="normal">{title}</Text>
          <Text secondary size="small">
            {subtitle}
          </Text>
        </Box>
        <ToggleSwitch checked={checked} onChange={() => setChecked(!checked)} />
      </Box>
    );
  };

  return (
    <Card>
      <Card.Header
        title="Default emails"
        subtitle="Send default notifications about this event."
      />
      <Card.Divider />
      <Card.Content>
        <Box direction="vertical">
          {renderListItem({
            title: 'Confirmation',
            subtitle: 'Let guests know their spot is confirmed.',
            padding: '0px 0px 18px',
            toggleChecked: false,
          })}
          <Divider />

          {renderListItem({
            title: 'Reminder',
            subtitle: 'Send a friendly reminder when the event is coming up.',
            padding: '18px 0px',
            toggleChecked: true,
          })}
          <Divider />

          {renderListItem({
            title: 'Cancelation',
            subtitle: 'Notify guests if this event is canceled.',
            padding: '18px 0px 0px',
            toggleChecked: true,
          })}
        </Box>
      </Card.Content>
    </Card>
  );
};
```

### Forms
- description: <p>Use toggle switch to control the state of items.</p>
- example: 
```jsx 
() => {
  const [toggleChecked, setToggleChecked] = React.useState(true);

  return (
    <Card>
      <Card.Header title="Product info" />
      <Card.Divider />
      <Card.Content>
        <Layout cols={12}>
          <Cell span={12}>
            <Heading size="tiny">Basic info</Heading>
          </Cell>
          <Cell span={8}>
            <FormField label="Product name">
              <Input placeholder=" " />
            </FormField>
          </Cell>
          <Cell span={4}>
            <FormField label="Ribbon">
              <Input placeholder="e.g., New Arrival" />
            </FormField>
          </Cell>
          <Cell span={4}>
            <FormField label="Price">
              <NumberInput
                prefix={<Input.Affix>$</Input.Affix>}
                hideStepper
                value="12"
              />
            </FormField>
          </Cell>
          <Cell span={12}>
            <Box>
              <FormField stretchContent={false} label="On sale" labelPlacement="right">
                <ToggleSwitch
                  checked={toggleChecked}
                  onChange={() => setToggleChecked(!toggleChecked)}
                />
              </FormField>
            </Box>
          </Cell>
          <Cell span={4}>
            <FormField label="Discount">
              <NumberInput
                suffix={<Input.Affix>%</Input.Affix>}
                hideStepper
                value="20"
              />
            </FormField>
          </Cell>
          <Cell span={4}>
            <FormField label="Sale price">
              <NumberInput
                prefix={<Input.Affix>$</Input.Affix>}
                hideStepper
                value="12"
              />
            </FormField>
          </Cell>
          <Cell span={12}>
            <FormField label="Description">
              <RichTextInputArea minHeight="120px" />
            </FormField>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};
```

### Required fields
- description: <p>Use toggle switch to set a field as required or optional.</p>
- example: 
```jsx 
() => {
  const [selectedOption, setSelectedOption] = React.useState(0);
  const [value, setValue] = React.useState(2);
  const [toggleChecked, setToggleChecked] = React.useState(true);

  const options = [
    { id: 0, value: 'Image' },
    { id: 1, value: 'Video' },
    { id: 2, value: 'Image and video' },
    { id: 3, value: 'Document' },
    { id: 4, value: 'Audio' },
  ];
  return (
    <SidePanel maxHeight="576px" width="288px" skin="floating">
      <SidePanel.Header title="Upload Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Supported file type">
            <Dropdown
              placeholder="Select"
              size="small"
              options={options}
              onSelect={(option) => setSelectedOption(option.id)}
              selectedId={selectedOption}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            gap="small"
            legend="Max number of files"
            columns="auto 72px"
          >
            <Slider
              onChange={setValue}
              min={0}
              max={10}
              value={value}
              displayMarks={false}
            />
            <Input
              size="small"
              value={value}
              onChange={(e) => setValue(e.target.value)}
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="Is required" labelPlacement="left" labelWidth="1fr">
            <ToggleSwitch
              checked
              size="medium"
              checked={toggleChecked}
              onChange={() => setToggleChecked(!toggleChecked)}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Section title="Display settings">
          <SidePanel.Field>
            <FormField label="Field title">
              <Input size="small" placeholder="Enter field title" />
            </FormField>
          </SidePanel.Field>
          <SidePanel.Field>
            <FormField label="Button text">
              <Input size="small" value="Choose file" />
            </FormField>
          </SidePanel.Field>
        </SidePanel.Section>
      </SidePanel.Content>
    </SidePanel>
  );
};
```


