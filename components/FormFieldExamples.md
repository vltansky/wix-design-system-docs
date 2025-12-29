
## Feature Examples


### Structure
- description: <p>A form field consists of <code>label</code>, <code>suffix</code> and <code>children</code> areas. Children areas can include any kind of form element.</p>
- example: 
```jsx 
<FormField
  label="Label"
  suffix={
    <StorybookComponents.Placeholder>
      Suffix area
    </StorybookComponents.Placeholder>
  }
>
  <StorybookComponents.Placeholder>
    Any form element
  </StorybookComponents.Placeholder>
</FormField>;
```

### Label placement
- description: <p>Control the label position with the <code>labelPlacement</code> prop. It supports 3 options:</p><li>Use <code>top</code> in all common cases.</li><li>Use <code>left</code> to save vertical space in less spacious layouts. This only works well with short labels. When using, be mindful of localization.</li><li>For <code><ToggleSwitch/></code>, use <code>right</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FormField label="Top" labelPlacement="top">
    <Input />
  </FormField>
  <FormField label="Left" labelPlacement="left">
    <Input />
  </FormField>
  <FormField label="Right" labelPlacement="right" stretchContent={false}>
    <ToggleSwitch checked />
  </FormField>
</StorybookComponents.Stack>;
```

### Label alignment
- description: <p>When the field label is placed on the side, its vertical position can be controlled with the <code>labelAlignment</code> prop. It supports 2 options:</p><li>For larger form elements like <code><InputArea/></code> or <code><RadioGroup/></code>, use <code>top</code>.</li><li>Use <code>middle</code> for single line inputs.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <FormField label="Top" labelPlacement="left" labelAlignment="top">
    <InputArea minHeight="90px" />
  </FormField>
  <FormField label="Middle" labelPlacement="left" labelAlignment="middle">
    <Input />
  </FormField>
</StorybookComponents.Stack>;
```

### Required
- description: <p>Mark mandatory fields with an asterisk by using <code>required</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <FormField label="Mandatory field" required>
    <Input />
  </FormField>
  <FormField label="Not mandatory field (optional)">
    <Input />
  </FormField>
</StorybookComponents.Stack>;
```

### Status and message
- description: <p>To change the status and display an inline message below any component, use the <code>status</code> and <code>statusMessage</code> props. </p><li>For error messages, set the <code>status</code> prop to <code>error</code>.</li><li>For warning messages, set the <code>status</code> prop to <code>warning</code>.</li><li>For loading messages, set the <code>status</code> prop to <code>loading</code>.</li><li>To show helper text, use the <code>statusMessage</code> prop with no <code>status</code>.  </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FormField
    labelSize="small"
    label="Label"
    status="error"
    statusMessage="This is an error message."
  >
    <Input />
  </FormField>
  <FormField
    labelSize="small"
    label="Label"
    status="warning"
    statusMessage="This is a warning message."
  >
    <Input />
  </FormField>
  <FormField
    labelSize="small"
    label="Label"
    status="loading"
    statusMessage="This is a loading message."
  >
    <Input />
  </FormField>
  <FormField
    labelSize="small"
    label="Label"
    statusMessage="This is helper text."
  >
    <Input />
  </FormField>
</StorybookComponents.Stack>;
```

### Additional info
- description: <p>Use a tooltip to provide users with more information about the field and what they need to input.</p>
- example: 
```jsx 
<FormField
  label="Hover over info icon"
  infoContent="This tooltip provides additional info about what the user needs to put in the input field."
>
  <Input />
</FormField>;
```

### Suffix
- description: <p>Add a custom element on the top right of the input to provide more options or information. This area accepts any component as a child.</p><p></p><p><em>Note:</em> The suffix area replaces the character count; they can’t be used simultaneously.</p>
- example: 
```jsx 
<FormField
  label="Label"
  suffix={
    <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />}>
      Go to External Site
    </TextButton>
  }
>
  <InputArea />
</FormField>;
```

### Character count
- description: <p>Define the maximum length of the field value by using the <code>charCount</code> prop. Any value over the allowed character count will not be added.</p>
- example: 
```jsx 
() => {
  const [charCount, setCharCount] = React.useState(0);
  const [value, setValue] = React.useState('');

  const handleOnChange = value => {
    if (value.length <= 20) {
      setValue(value);
      setCharCount(value.length);
    }
  };
  return (
    <FormField label="Enter more than 20 characters" charCount={20 - charCount}>
      <Input
        value={value}
        onChange={event => handleOnChange(event.target.value)}
      />
    </FormField>
  );
};
```

### Stretch content
- description: <p>Control the container width with <code>stretchContent</code>. This property is enabled by default and must be turned off when the form element has a fixed width, like when a <code><ToggleSwitch/></code> is used.</p>
- example: 
```jsx 
<FormField
  label="Not stretched content"
  labelPlacement="right"
  stretchContent={false}
>
  <ToggleSwitch checked />
</FormField>;
```

### Text overflow
- description: <p>Use the <code>ellipsis</code> prop for overflow text. The full text will be displayed in a <code><Tooltip/></code> when a user hovers over the button. Control the style of the tooltip using the <code>tooltipProps</code>. </p><p></p><p>To display label in multiple lines, use <code>maxLines</code> to define how many lines should be visible. <code>maxLines</code> can be used together with <code>ellipsis</code> to control after how many lines label would get truncated. </p><p></p><p>NOTE: it's not recommended to have labels longer than two lines, as the content would become too text heavy. </p>
- example: 
```jsx 
<StorybookComponents.Stack>
<SidePanel width="288px">
      <SidePanel.Field>
        <FormField label="This is an example text that overflows and is shown in tooltip">
    <Input placeholder="Placeholder" />
        </FormField>
      </SidePanel.Field>
    </SidePanel>
<SidePanel width="288px">
      <SidePanel.Field>
        <FormField         ellipsis
        maxLines="2" label="This is an example text that fits and is shown in two lines">
    <Input placeholder="Placeholder" />
        </FormField>
      </SidePanel.Field>
    </SidePanel>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Regular form
- description: <p>Use a top label on forms whenever possible. This creates a clear hierarchy and is the most readable format. </p>
- example: 
```jsx 
<Card>
  <Card.Header title="New dish" />
  <Card.Divider />
  <Card.Content>
    <Layout>
      <Cell span={4}>
        <FormField label="Image">
          <ImageViewer width="100%" height="176px" />
        </FormField>
      </Cell>
      <Cell span={8}>
        <Layout gap="24px">
          <Cell span={8}>
            <FormField label="Name">
              <Input value="My New Dish" />
            </FormField>
          </Cell>
          <Cell span={4}>
            <FormField label="Price">
              <Input value="0" prefix={<Input.Affix>$</Input.Affix>} />
            </FormField>
          </Cell>
          <Cell>
            <FormField label="Description">
              <InputArea
                placeholder="Describe your dish in a few sentences."
                resizable
                rows={3}
              />
            </FormField>
          </Cell>
        </Layout>
      </Cell>
      <Cell span={6}>
        <FormField label="Dietary preferences" infoContent="Choose which dietary preferences your dish is appropriate for.">
          <Layout>
            <Cell span={6}>
              <Box direction="vertical" gap="12px">
                <Checkbox>No salt</Checkbox>
                <Checkbox>Vegan</Checkbox>
                <Checkbox>Vegetarian</Checkbox>
              </Box>
            </Cell>
            <Cell span={6}>
              <Box direction="vertical" gap="12px">
                <Checkbox>Gluten free</Checkbox>
                <Checkbox>Organic</Checkbox>
                <Checkbox>Spicy</Checkbox>
              </Box>
            </Cell>
          </Layout>
        </FormField>
      </Cell>
      <Cell span={3}>
        <FormField label="Visibility">
          <Checkbox checked>Visible on site</Checkbox>
        </FormField>
      </Cell>
      <Cell span={3}>
        <FormField label="Availability">
          <Checkbox checked>In stock</Checkbox>
        </FormField>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;
```

### Settings panel
- description: <p>Use a top label or a left label depending on the layout. For example, a left label works best with a single toggle button. </p>
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
            columns="auto 60px"
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
          <FormField
            label="Is required"
            labelPlacement="left"
            labelWidth="1fr"
          >
            <ToggleSwitch
              checked
              size="small"
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


