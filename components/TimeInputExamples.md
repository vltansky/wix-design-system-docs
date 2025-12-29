
## Feature Examples


### Size
- description: <p>Adjust the size of the input using the <code>size</code> prop. 3 sizes are supported:</p><li>For most common cases, use the default <code>medium</code>.</li><li>Use <code>large</code> when the time input needs emphasis.</li><li>In more dense and compact layouts, use <code>small</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TimeInput size="large" placeholder="Large" />
  <TimeInput size="medium" placeholder="Medium" />
  <TimeInput size="small" placeholder="Small" />
</StorybookComponents.Stack>;
```

### Width
- description: <p>Control the width of the input with the <code>width</code> property. 2 values are supported:</p><li>To adjust the width of the field according to the size of the value use the default <code>auto</code>.</li><li>Fill the parent container completely with <code>100%</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack>
    <TimeInput width="auto" placeholder="Auto" />
  </StorybookComponents.Stack>
  <TimeInput width="100%" placeholder="Full width" />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Style the component using the <code>border</code> prop. It supports 4 styles:</p><li>For most common cases, use <code>standard</code>.</li><li>To build inputs that can be used to filter data, use <code>round</code>.</li><li>Use <code>bottomLine</code> to create an editable, underlined title field.</li><li>When a component provides its own hover and focus styles, such as a table or spreadsheet cells, use <code>none</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TimeInput border="standard" placeholder="Standard" />
  <TimeInput border="round" placeholder="Round" />
  <TimeInput border="bottomLine" placeholder="Bottom Line" />
  <TimeInput border="none" placeholder="None" />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control the status of the time input using the <code>status</code> prop. It supports 3 states:</p><li><code>error</code> demonstrates that something is missing or the entry was invalid. The conditions for an error status must be defined when using this prop.</li><li><code>warning</code> highlights an input value that might have a significant impact to the user or it can't be validated.</li><li><code>loading</code> shows when an input value is being uploaded to the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TimeInput status="error" placeholder="Error" />
  <TimeInput status="warning" placeholder="Warning" />
  <TimeInput status="loading" placeholder="Loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>{' '}
    <FormField status="error" statusMessage="This is an error message.">
      <TimeInput placeholder="See message below" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <TimeInput
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Invalid message
- description: <p>To add predefined validations to the Time Input, use the <code>invalidMessage</code> prop.</p><p></p><p>The error icon and tooltip message are triggered when a user enters an invalid syntax, e.g., 15:99 am.</p><p></p><p>To exclude past times from the calendar view, use the <code>excludePastTimes</code> prop. To exclude specific times, use the <code>filterTime</code> prop.</p><p></p><p>The error message shows in a tooltip on hover over the icon by default. The message can be updated or removed. </p><p></p><p>Note: When both <code>statusMessage</code> and <code>invalidMessage</code> props are used, the input will display the <code>statusMessage</code>, unless internal validation fails. Then it would display the <code>invalidMessage</code>.  </p>
- example: 
```jsx 
<TimeInput invalidMessage="Enter a time in 12 hour format using AM or PM." />;
```

### Disabled
- description: <p>Disable all input interactions with the <code>disabled</code> prop. Use it to demonstrate that the user cannot select the time.</p>
- example: 
```jsx 
<TimeInput disabled />;
```

### Prefix &amp; suffix
- description: <p>Add text, icons or a button at the beginning or end of an input field using <code>prefix</code> and <code>suffix</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TimeInput
    prefix={<Input.Affix>From</Input.Affix>}
    suffix={<Input.Affix>GMT+1</Input.Affix>}
  />
</StorybookComponents.Stack>;
```

### Locale
- description: <p>Specify a correct time formatting (e.g., AM/PM or military time) per country using the <code>locale</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TimeInput locale="en" />
  <TimeInput locale="de" />
</StorybookComponents.Stack>;
```

### Time style
- description: <p>Control whether to display the time zone info with <code>timeStyle</code>. It supports 2 values:</p><li><code>short</code> (the default) displays the time only.</li><li><code>long</code> shows the time together with the time zone.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TimeInput timeStyle="short" />
  <TimeInput timeStyle="long" />
</StorybookComponents.Stack>;
```

### Step
- description: <p>In a dropdown layout, control the interval between timestamps using the <code>step</code> prop.</p><p></p><p>By default, the interval between timestamps is 15 minutes.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="6px">
    15 min (default):
    <TimeInput step={15} />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="6px">
    5 min:
    <TimeInput step={5} />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="6px">
    30 min:
    <TimeInput step={30} />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="6px">
    60 min:
    <TimeInput step={60} />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```




## Developer Examples


### Predefined time validations
- description: <p>The component's validations cover the following cases:</p><li><code>formatError</code>: when a user enters a time that’s invalid and impossible to parse.</li><li><code>outOfBoundsError</code>: when a user types in a time out of the accepted range. This validation is triggered when the <code>excludePastTimes</code> or <code>filterTime</code> props are enabled.</li><p></p><p>Note: In order for the error to be cleared, use <code>onChange</code>. This way, the error will not show when the user enters a valid time. </p>
- example: 
```jsx 
() => {
  const [error, setError] = React.useState()

  const onChange = (value) => {
    setError(undefined)
  }

  const onInvalid = (errorInfo) => {
    if (errorInfo.validationType === 'outOfBoundsError') {
      setError('Past time values are not allowed')
    } else if (errorInfo.validationType === 'formatError') {
      setError('Invalid format')
    }
  }

  return (
    <StorybookComponents.Stack flexDirection="column">
      <FormField
        status={error ? 'error' : undefined}
        statusMessage={
          error
            ? error
            : 'Try entering invalid (e.g. 12:99 PM) or past time values to see different error messages'
        }
      >
        <TimeInput excludePastTimes onChange={onChange} onInvalid={onInvalid} />
      </FormField>
    </StorybookComponents.Stack>
  )
}

```

### Custom time validations
- description: <p>To apply custom validations to the component, use information returned by <code>onChange</code> and <code>onInvalid</code> props. The <code>onInvalid</code> prop provides <code>validationType</code> and input <code>value</code> parameters.</p>
- example: 
```jsx 
() => {
  const [error, setError] = React.useState()

  const onChange = (value) => {
    if (value.date?.getMinutes() !== 0) {
      setError('Value must match 1 hour interval')
    } else {
      setError(undefined)
    }
  }

  const onInvalid = (errorInfo) => {
    if (errorInfo) {
      setError('Invalid value')
    }
  }

  return (
    <StorybookComponents.Stack flexDirection="column">
      <FormField
        status={error ? 'error' : undefined}
        statusMessage={
          error ?? 'Try entering a value with minutes (e.g. 12:15 PM)'
        }
      >
        <TimeInput step={60} onChange={onChange} onInvalid={onInvalid} />
      </FormField>
    </StorybookComponents.Stack>
  )
}

```


    


## Common Use Case Examples


### Scheduling
- description: <p>Use the time input together with a <code><DatePicker/></code> to schedule specific times for events, appointments, delivery hours, etc.</p>
- example: 
```jsx 
() => {
  const [startDate, setStartDate] = React.useState();
  const [endDate, setEndDate] = React.useState();

  return (
    <Layout>
      <Cell span={6}>
        <Box gap={2}>
          <FormField label="Start date">
            <DatePicker
              width="100%"
              placeholderText="Select"
              value={startDate}
              onChange={value => setStartDate(value)}
            />
          </FormField>
          <FormField label="Start time">
            <TimeInput />
          </FormField>
        </Box>
      </Cell>
      <Cell span={6}>
        <Box gap={2}>
          <FormField label="Start date">
            <DatePicker
              width="100%"
              placeholderText="Select"
              value={startDate}
              onChange={value => setStartDate(value)}
            />
          </FormField>
          <FormField label="Start time">
            <TimeInput />
          </FormField>
        </Box>
      </Cell>
    </Layout>
  );
};
```

### Range
- description: <p>Use the <code><Range/></code> component to merge two input fields to specify a time duration.</p>
- example: 
```jsx 
<FormField label="Duration">
  <Range>
    <TimeInput />
    <TimeInput />
  </Range>
</FormField>;
```


