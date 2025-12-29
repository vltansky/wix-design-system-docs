
## Feature Examples


### Size
- description: <p>Adjust the size using the <code>size</code> prop. There are 3 supported  sizes:</p><li>When the input needs to be emphasized, like in onboarding flows, use <code>large.</code></li><li>In most cases, use the default <code>medium.</code></li><li>For dense and narrow layouts where space is tight, use <code>small.</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NumberInput size="large" placeholder="Large" />
  <NumberInput size="medium" placeholder="Medium" />
  <NumberInput size="small" placeholder="Small" />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Style the field using the <code>border</code> prop. It supports 4 styles:</p><li>For most common cases, like forms, use <code>standard</code>.</li><li>To build inputs that can be used to filter data, use <code>round</code>.</li><li>Use <code>bottomLine</code> to create an editable, underlined title field.</li><li>When a component provides its own hover and focus styles, such as a table or spreadsheet cells, use <code>none</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NumberInput border="standard" placeholder="Standard" />
  <NumberInput border="round" placeholder="Round" />
  <NumberInput border="bottomLine" placeholder="Bottom line" />
  <NumberInput border="none" placeholder="None" />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control the status of the input using the <code>status</code> prop. It supports 3 states:</p><p></p><li><code>error</code> demonstrates that a required input is missing something or the entry was invalid.</li><li><code>warning</code> highlights an input value that might have a significant impact to a user.</li><li><code>loading</code> shows when an input value is being uploaded to the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NumberInput status="error" placeholder="Error" />
  <NumberInput status="warning" placeholder="Warning" />
  <NumberInput status="loading" placeholder="Loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <NumberInput placeholder="See message below" tooltipPlacement="top-end" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <NumberInput
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
      tooltipPlacement="top-end"
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Prefix and suffix
- description: <p>Add text, icons or a button at the beginning or end of the input field using <code>prefix</code> and <code>suffix</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NumberInput prefix={<Input.Affix>$</Input.Affix>} value="20.00" />
  <NumberInput suffix={<Input.Affix>%</Input.Affix>} value="10" />
  <NumberInput
    prefix={
      <Input.IconAffix>
        <Icons.Users />
      </Input.IconAffix>
    }
    value="2"
    suffix={<Input.Affix>guests</Input.Affix>}
  />
</StorybookComponents.Stack>;
```

### Read-only and disabled
- description: <p>Inputs can also be made read-only or disabled entirely.</p><li><code>readOnly</code> disables the field, so users can't enter new values. The current value can still be copied.</li><li><code>disabled</code> removes all interactions and creates a disabled input state. Use it to highlight functions that are unavailable.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NumberInput placeholder="Read-only" readOnly />
  <NumberInput placeholder="Disabled" disabled />
</StorybookComponents.Stack>;
```

### Clear button
- description: <p>Enable a button that lets users easily clear the input value by using the <code>clearButton</code> prop. Use it when the input value is optional or has to be cleared often.</p>
- example: 
```jsx 
() => {
  const [inputText, setInputText] = React.useState('20');

  return (
    <NumberInput
      value={inputText}
      clearButton
      onChange={setInputText}
      onClear={() => setInputText('')}
    />
  );
};
```

### Increment by steps
- description: <p>Use the <code>step</code> prop to specify what the increments are when clicking up or down on the arrows.</p><p></p><p>The arrows controls can be hidden with <code>hideStepper</code>. When the arrows are hidden, the field value can still be incremented by the set <code>step</code> when the field is changed using the arrow keys on the keyboard.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NumberInput
    step={20}
    placeholder="Click on the arrows to change the value by 20 units at a time."
  />
  <NumberInput
    step={20}
    hideStepper
    placeholder="Click the up and down arrow keys to change the value by 20 when the arrows are hidden."
  />
</StorybookComponents.Stack>;
```

### Min and max values
- description: <p>If the user inputs something outside of the minimum or maximum, explain that it's invalid using the <code>invalidMessage</code> prop. </p><p></p><p>Get informed about invalid message events by using the <code>onInvalid</code> callback function.</p>
- example: 
```jsx 
<NumberInput
  min={-5}
  max={5}
  invalidMessage="Enter a number between -5 and 5."
  placeholder="Try typing a number less than -5 or more than 5"
/>;
```




## Developer Examples


### Controlled
- description: <p>Use NumberInput in controlled mode by passing <code>value</code> and <code>onChange</code> props.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('0');

  return (
    <NumberInput
      value={value}
      onChange={(numberValue, stringValue) => setValue(stringValue)}
    />
  );
};

```

### Range validation
- description: <p>The <code>min</code> and <code>max</code> properties enable built-in range validation, so no need to add <code>onChange</code> and <code>value.</code></p><p></p><p>Users will still be able to enter invalid numbers, but will be notified that what they entered is invalid. Set the error message using <code>invalidMessage.</code></p><p></p><p>Don't allow users to submit a form with an invalid input value. Use <code>onInvalid</code> to get an invalid event.</p>
- example: 
```jsx 
() => {
  const ref = React.useRef();
  const [invalid, setInvalid] = React.useState(false);
  const [errorMessage, setErrorMessage] = React.useState('');

  const onInvalid = value => {
    if (Number(value) < 2) {
      setErrorMessage('You must order at least 2 tickets.');
    }

    if (Number(value) > 20) {
      setErrorMessage('You can only order up to 20 tickets at a time.');
    }
  };

  const onSubmit = () => {
    if (errorMessage) {
      ref.current.focus();
    }
  };

  return (
    <Layout>
      <Cell>
        <FormField
          label="Number of tickets"
          infoContent="You can buy between 2 and 20 tickets at a time."
        >
          <NumberInput
            ref={ref}
            min={5}
            max={20}
            invalidMessage={errorMessage}
            onInvalid={onInvalid}
            placeholder="How many tickets would you like?"
          />
        </FormField>
      </Cell>
      <Cell>
        <Button onClick={onSubmit}>Purchase</Button>
      </Cell>
    </Layout>
  );
};
```

### Integrating with react-hook-form
- description: <p>react-hook-form reduces the amount of code you need to write while removing unnecessary re-renders. The preview here demonstrates form validation in action while using the number input.</p>
- example: 
```jsx 
() => {
  const [state, setState] = React.useState({});
  const {
    handleSubmit,
    formState: { errors },
    control,
  } = useForm();

  const { field } = useController({
    name: 'tickets',
    control,
    rules: { min: 2, max: 20 },
    defaultValue: 2,
  });

  const status = errors.tickets && 'error';
  const statusMessage =
    errors.tickets && errors.tickets.type === 'min'
      ? 'You must order at least 2 tickets.'
      : 'You can only order up to 20 tickets at a time.';

  const onSubmit = data => setState(data);

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <Layout>
        <Cell>
          <FormField
            label="Number of tickets"
            infoContent="You can buy between 2 and 20 tickets at a time."
          >
            <NumberInput
              {...field}
              inputRef={field.ref}
              status={status}
              statusMessage={statusMessage}
              placeholder="How many tickets would you like?"
            />
          </FormField>
        </Cell>
        <Cell>
          <Layout alignItems="center">
            <Cell span={2}>
              <Button type="submit">Purchase</Button>
            </Cell>
            <Cell span={10}>
              <SectionHelper appearance="preview">
                {JSON.stringify(state)}
              </SectionHelper>
            </Cell>
          </Layout>
        </Cell>
      </Layout>
    </form>
  );
};
```


    


## Common Use Case Examples


### Settings panel
- description: <p>Use number input with other components like <code><Slider/></code> in a <code><FieldSet/></code> wrapper to group them together and let users define the exact numerical value. </p>
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
      <SidePanel.Header title="Events" />
      <Box height="480px">
        <VerticalTabs size="small" activeTabId={1} onChange={() => {}}>
          <VerticalTabs.TabItem id={0}>Main</VerticalTabs.TabItem>
          <VerticalTabs.TabItem id={1}>Design</VerticalTabs.TabItem>
          <VerticalTabs.TabItem id={2}>Text</VerticalTabs.TabItem>
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
          <SidePanel.Section title="Background">
            <SidePanel.Field>
              <FieldSet
                legend="Background color"
                legendSize="small"
                legendPlacement="top"
                alignment="center"
                columns="30px auto 72px"
              >
                <FillPreview fill="#000000" aspectRatio={1} />
                <Slider
                  gradientColor="#000000"
                  min={0}
                  max={100}
                  displayMarks={false}
                  onChange={(value) => setOpacity(value)}
                  value={opacity}
                />
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
            <SidePanel.Field>
              <FieldSet gap="small" legend="Border width" columns="auto 60px">
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
                  onChange={(e) => setValue(e.target.value)}
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

### Compound input
- description: <p>Stack items next to each other with <code><Box/> </code>when fields represent the same data, or when a change in one input affects one or more other fields.</p>
- example: 
```jsx 
() => {
  const signs = {
    amount: '$',
    percentage: '%',
  };
  const [value, setValue] = React.useState(20);
  const [signValue, setSignValue] = React.useState('amount');

  const onClick = (_, value) => {
    setSignValue(value);
  };

  return (
    <FormField
      label="Discount"
      infoContent="This is how much will be taken off the final price. Discount can be offered in percentage off the starting price or a specific amount."
    >
      <Box gap="12px" width="100%">
        <Box direction="vertical" width="100%">
          <NumberInput
            prefix={
              signValue === 'amount' ? (
                <Input.Affix>{signs[signValue]}</Input.Affix>
              ) : null
            }
            suffix={
              signValue === 'percentage' ? (
                <Input.Affix>{signs[signValue]}</Input.Affix>
              ) : null
            }
            onChange={setValue}
            value={value}
          />
        </Box>
        <Box direction="vertical">
          <SegmentedToggle
            defaultSelected="amount"
            onClick={onClick}
            selected={signValue}
          >
            <SegmentedToggle.Button value="amount" tooltipText="Fixed amount">
              {signs.amount}
            </SegmentedToggle.Button>
            <SegmentedToggle.Button value="percentage" tooltipText="Percentage">
              {signs.percentage}
            </SegmentedToggle.Button>
          </SegmentedToggle>
        </Box>
      </Box>
    </FormField>
  );
};
```

### Disabled stepper
- description: <p>Disable the arrows once the minimum or maximum value has been reached.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(20);

  return (
    <FormField
      label="Number of tickets"
      statusMessage="Between 2 and 20 tickets"
    >
      <NumberInput
        min={2}
        max={20}
        value={value}
        onChange={setValue}
        placeholder="How many tickets would you like?"
        strict={true}
      />
    </FormField>
  );
};
```


