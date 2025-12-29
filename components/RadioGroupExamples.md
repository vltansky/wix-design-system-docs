
## Feature Examples


### Structure
- description: <p>The component consists of a list of options with radio buttons wrapped inside <code><RadioGroup></code>.</p><p></p><p>Option labels are plain text by default, but they can be replaced with any other component or set of components.</p>
- example: 
```jsx 
<RadioGroup value={1}>
  <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
  <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
  <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  <RadioGroup.Radio value={4}>Option 4</RadioGroup.Radio>
</RadioGroup>;
```

### Size
- description: <p>Adjust the component size using the size prop. It supports 2 sizes:</p><p></p><p><code>medium</code> (default) - use in all common cases</p><p><code>small</code> - use in more dense layouts</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <RadioGroup size="medium" value={1}>
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup size="small" value={1}>
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
</StorybookComponents.Stack>;
```

### Layout
- description: <p>Control the layout of the options with the <code>display</code> prop. Choose from 2 layouts:</p><li>For most common cases, use the default <code>vertical</code>.</li><li>Use <code>horizontal</code> for options with short labels (e.g., Yes/No selections in a form), or when there is limited space.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <RadioGroup value={1} display="vertical">
    <RadioGroup.Radio value={1}>Vertical 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Vertical 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Vertical 3</RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup value={1} display="horizontal">
    <RadioGroup.Radio value={1}>Horizontal 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Horizontal 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Horizontal 3</RadioGroup.Radio>
  </RadioGroup>
</StorybookComponents.Stack>;
```

### Spacing
- description: <p>Control the pixel spacing between options with the <code>spacing</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack gap="72px">
  <RadioGroup spacing="12px">
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup spacing="18px">
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup spacing="24px">
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
</StorybookComponents.Stack>;
```

### Button alignment
- description: <p>Control how the radio buttons align to the text with the <code>vAlign</code> prop. Choose from 2 alignments:</p><li><code>center</code> (the default) aligns the radio button to the middle of the text. It is recommended for most common cases.</li><li><code>top</code> aligns the radio buttons to the top of the text. This is good for options that go over 3 or more lines of text.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <RadioGroup vAlign="center">
    <RadioGroup.Radio>
      <Heading size="small">Center aligned radio</Heading>
      <Text secondary size="small">
        Subtitle
      </Text>
    </RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup vAlign="top">
    <RadioGroup.Radio>
      <Heading size="small">Top aligned radio</Heading>
      <Text secondary size="small">
        Subtitle
      </Text>
    </RadioGroup.Radio>
  </RadioGroup>
</StorybookComponents.Stack>;
```

### Disabled buttons
- description: <p>Radio options can be disabled in 2 ways:</p><li>Disable all options at once with <code>disabled</code>.</li><li>Choose which options to disable with <code>disabledRadios</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack gap="60px">
  <RadioGroup disabled value={1}>
    <RadioGroup.Radio value={1}>All disabled</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>All disabled</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>All disabled</RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup disabledRadios={[3]} value={1}>
    <RadioGroup.Radio value={1}>Selected</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Unselected</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Disabled</RadioGroup.Radio>
  </RadioGroup>
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the radio group by wrapping it in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<FormField status="error" statusMessage="This is an error message.">
  <RadioGroup>
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
</FormField>;
```

### Button area
- description: <p>Highlight the clickable area of an option by controlling the design. It's recommended to always use this on mobile.</p><li>Specify when the button area should be highlighted (on hover, always, or not at all) with <code>selectionArea</code>.</li><li>To choose a filled or outlined design, use <code>selectionAreaSkin</code>.</li><li>Define the white pixel spacing around each radio button with <code>selectionAreaPadding</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <RadioGroup
    value={1}
    selectionArea="always"
    selectionAreaSkin="outlined"
    selectionAreaPadding="12px 18px"
  >
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
  <RadioGroup
    value={1}
    selectionArea="hover"
    selectionAreaSkin="filled"
    selectionAreaPadding="12px 18px"
  >
    <RadioGroup.Radio value={1}>Option 1</RadioGroup.Radio>
    <RadioGroup.Radio value={2}>Option 2</RadioGroup.Radio>
    <RadioGroup.Radio value={3}>Option 3</RadioGroup.Radio>
  </RadioGroup>
</StorybookComponents.Stack>;
```

### Additional content
- description: <p>Use the <code>content</code> prop to show additional details for an option. It accepts any kind of content and places it outside of a radio option.</p>
- example: 
```jsx 
<RadioGroup value={1} selectionArea="always">
  <RadioGroup.Radio
    value={1}
    content={
      <StorybookComponents.Placeholder margin={2}>
        Details about Option 1
      </StorybookComponents.Placeholder>
    }
  >
    Option 1
  </RadioGroup.Radio>
  <RadioGroup.Radio
    value={2}
    content={
      <StorybookComponents.Placeholder margin={2}>
        Details about Option 2
      </StorybookComponents.Placeholder>
    }
  >
    Option 2
  </RadioGroup.Radio>
</RadioGroup>;
```




    


## Common Use Case Examples


### Settings panel
- description: <p>Only use small size radio buttons in settings panels to ensure consistency across all panels.</p>
- example: 
```jsx 
() => {
  const [defaultStateselected, setDefaultStateSelected] = React.useState(1);
  const [homepageTypeSelected, setHomepageTypeSelected] = React.useState(1);

  return (
    <SidePanel maxHeight="576px" width="288px" skin="floating">
      <SidePanel.Header title="Breadcrumbs Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Default state">
            <RadioGroup
              value={defaultStateselected}
              onChange={setDefaultStateSelected}
              size="small"
            >
              <RadioGroup.Radio value={1}>Full trail</RadioGroup.Radio>
              <RadioGroup.Radio value={2}>Hide homepage</RadioGroup.Radio>
              <RadioGroup.Radio value={3}>Hide current page</RadioGroup.Radio>
            </RadioGroup>
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="Display homepage as">
            <RadioGroup
              value={homepageTypeSelected}
              onChange={setHomepageTypeSelected}
              size="small"
            >
              <RadioGroup.Radio value={1}>Text</RadioGroup.Radio>
              <RadioGroup.Radio value={2}>Icon</RadioGroup.Radio>
            </RadioGroup>
          </FormField>
        </SidePanel.Field>
      </SidePanel.Content>
    </SidePanel>
  );
};

```

### Default selection
- description: <p>Have a default option selected whenever possible, ideally a neutral choice such as "None" or "All". </p>
- example: 
```jsx 
() => {
  const [selected, setSelected] = React.useState(1);

  return (
    <RadioGroup value={selected} onChange={setSelected}>
      <RadioGroup.Radio value={1}>All</RadioGroup.Radio>
      <RadioGroup.Radio value={2}>In stock</RadioGroup.Radio>
      <RadioGroup.Radio value={3}>Out of stock</RadioGroup.Radio>
    </RadioGroup>
  );
};
```

### Additional info
- description: <p>Use <code><InfoIcon/></code> to add a tooltip next to an option to provide additional information.</p>
- example: 
```jsx 
() => {
  const [selected, setSelected] = React.useState(2);

  return (
    <FormField label="How would you like to add tax?">
      <RadioGroup value={selected} onChange={setSelected}>
        <RadioGroup.Radio value={1}>Include in the price</RadioGroup.Radio>
        <RadioGroup.Radio value={2}>
          Add at checkout
          <Box inline>
            <InfoIcon content="Tax will not be included in the price of your plans. Customers will see the tax added on at checkout." />
          </Box>
        </RadioGroup.Radio>
      </RadioGroup>
    </FormField>
  );
};
```

### Horizontal layout
- description: <p>Use a horizontal layout when displaying radio lists with 2-3 options and short descriptions. This layout is great for situations where vertical space is limited.</p>
- example: 
```jsx 
() => {
  const [selected, setSelected] = React.useState(2);
  return (
    <CustomModalLayout
      title="Add an area for local delivery"
      subtitle="Set a delivery area within a radius or certain postal codes."
      primaryButtonText="Add Area"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => {}}
    >
      <Layout cols={1}>
        <FormField label="Area name">
          <Input placeholder="e.g., Lower East Side" />
        </FormField>
        <FormField label="Set area by">
          <RadioGroup
            display="horizontal"
            value={selected}
            onChange={setSelected}
          >
            <RadioGroup.Radio value={1}>Radius</RadioGroup.Radio>
            <RadioGroup.Radio value={2}>Postal codes</RadioGroup.Radio>
          </RadioGroup>
        </FormField>
        <FormField label="Add postal codes that all have the same delivery rate">
          <InputArea placeholder="Separate postal codes with commas, e.g., 10002, 10003, 10009" />
        </FormField>
      </Layout>
    </CustomModalLayout>
  );
};
```

### Custom button
- description: <p>Other components can also be used in radio option labels (e.g., avatar, illustration, additional text).</p>
- example: 
```jsx 
() => {
  const [selected, setSelected] = React.useState(1);
  return (
    <Card>
      <Card.Header
        title="Business type"
        subtitle="Define your business type for legal purposes."
      />
      <Card.Divider />
      <Card.Content>
        <RadioGroup
          selectionArea="always"
          selectionAreaSkin="outlined"
          selectionAreaPadding="18px"
          spacing="12px"
          value={selected}
          onChange={setSelected}
        >
          <RadioGroup.Radio value={1}>
            <Box gap={2} verticalAlign="middle">
              <Avatar />
              <Box direction="vertical">
                <Text weight="normal">Individual</Text>
                <Text size="small">
                  You own and run the business with a personal bank account.
                </Text>
              </Box>
            </Box>
          </RadioGroup.Radio>
          <RadioGroup.Radio value={2}>
            <Box gap={2} verticalAlign="middle">
              <Avatar shape="square" />
              <Box direction="vertical">
                <Text weight="normal">Partnership, LLC or Corporation</Text>
                <Text size="small">
                  You have a business registration number and a business bank
                  account.
                </Text>
              </Box>
            </Box>
          </RadioGroup.Radio>
        </RadioGroup>
      </Card.Content>
    </Card>
  );
};
```


