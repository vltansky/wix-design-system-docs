
## Feature Examples


### Size
- description: <p>Adjust the size using the <code>size</code> prop. It supports 3 sizes:</p><li>Use <code>large</code> when the date input needs emphasis.</li><li>For most common cases, use the default <code>medium</code>.</li><li>In more dense and compact layouts, use <code>small</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <DatePicker placeholderText="Large" size="large" width="240px"/>
  <DatePicker placeholderText="Medium" size="medium" width="240px"/>
  <DatePicker placeholderText="Small" size="small" width="240px"/>
</StorybookComponents.Stack>;

```

### Status
- description: <p>Control the status using the <code>status</code> prop. There are 3 states:</p><li><code>error</code> highlights invalid dates.</li><li><code>warning</code> highlights dates that can't be validated or might impact the user negatively.</li><li><code>loading</code> shows that the server is loading the selected value.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <DatePicker value={new Date()} status="error" width="240px" />
  <DatePicker value={new Date()} status="warning" width="240px" />
  <DatePicker value={new Date()} status="loading" width="240px" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the date picker is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <DatePicker placeholderText="See message below" width="240px" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <DatePicker
      placeholderText="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
      width="240px"
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Read-only and disabled
- description: <p>Control the input interaction with these props:</p><li>Use <code>readOnly</code> to display dates that cannot be overwritten (but can still be copied). </li><li>Disable all input interactions with the <code>disabled</code> prop. Use it to highlight an unavailable selection.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <DatePicker value={new Date()} placeholderText="Select a date" readOnly width="240px"/>
  <DatePicker placeholderText="Select date" disabled width="240px"/>
</StorybookComponents.Stack>;
```

### Clear button
- description: <p>Use the <code>clearButton</code> prop to add a button that clears the selected date easily.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(new Date());

  return (
    <DatePicker
      placeholderText="Select date"
      value={value}
      clearButton
      onClear={() => setValue(null)}
      onChange={setValue}
      width="240px"
    /> 
  );
};
```

### Locale and date style
- description: <p>Set appropriate formatting per country with <code>locale</code> and <code>dateStyle</code> props.</p><p></p><p><code>dateStyle</code> supports 2 values:</p><li>In most cases, the default style should be <code>short.</code></li><li>Give the month more emphasis with the <code>medium</code> prop.</li><li>Show day and month in more detail with the <code>long</code> prop.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <DatePicker value={new Date()} locale="en" dateStyle="short" width="240px"/>
  <DatePicker value={new Date()} locale="en" dateStyle="medium" width="240px"/>
  <DatePicker value={new Date()} locale="en" dateStyle="long" width="240px" />
</StorybookComponents.Stack>;
```

### First day of the week
- description: <p>Use <code>firstDayOfWeek</code> to adjust which day of the week is shown first in the calendar view. Overwrite the default value for Sunday (0) with a number representing any other day of the week (Monday = 1, Tuesday = 2, etc.).</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <DatePicker
    placeholderText="First day is Sunday"
    firstDayOfWeek={0}
    width="240px"
  />
  <DatePicker
    placeholderText="First day is Monday"
    firstDayOfWeek={1}
    width="240px"
  />
</StorybookComponents.Stack>;
```

### Year and month selections
- description: <p>Make it easier for users to select dates far in the past or future with the <code>showMonthDropdown</code> and <code>showYearDropdown</code>. These dropdowns will show inside the calendar view.</p>
- example: 
```jsx 
<DatePicker value={new Date()} showMonthDropdown showYearDropdown width="240px"/>;
```

### Excluding dates
- description: <p>Control the date ranges that users can select with the following props:</p><li>Stop users from selecting dates in the past with <code>excludePastDates</code>.</li><li>Don't allow users to select a specific set or range of dates with <code>filterDate</code> .</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <DatePicker
    placeholderText="Select a date in the future"
    excludePastDates
    width="50%"
  />
  <DatePicker
    placeholderText="Select one of the available dates"
    filterDate={date => date < new Date()}
    width="50%"
  /> 
</StorybookComponents.Stack>;
```




## Developer Examples


### Built-in date validation
- description: <p>The component's built-in validation feature covers these cases:</p><li><code>formatError</code> - when a user types in a date that is invalid and impossible to parse.</li><li><code>outOfBoundsError</code> - when a user types in a date that is out of the accepted range. This validation is triggered when the <code>excludePastDates</code> or <code>filterDate</code> props are enabled.</li><p></p><p>Get informed about a validation event by using the <code>onValidate</code> callback function. It provides these parameters: <code>validationType</code>, input <code>value</code> and <code>format</code>.</p>
- example: 
```jsx 
() => {
  const [date, setDate] = React.useState(new Date())
  const [error, setError] = React.useState('')

  const handleValidation = ({ validationType, value, format }) => {
    if (validationType === 'formatError') {
      setError(`Dates must be in this format: ${format}`)
    } else if (validationType === 'outOfBoundsError') {
      setError('Enter a date that is in the future')
    } else if (validationType === 'valid') {
      setError('')
    }
  }

  return (
    <FormField
      status={error ? 'error' : undefined}
      statusMessage={
        error
          ? error
          : 'Try entering invalid date (e.g. 88/10/2023) or a past date (e.g. 08/10/2000)'
      }
    >
      <DatePicker
        value={date}
        placeholderText="MM/DD/YYYY"
        onValidate={handleValidation}
        width="240px"
        excludePastDates
      />
    </FormField>
  )
}

```

### Custom date validations
- description: <p>To apply custom validations to the component, use <code>onChange</code>, <code>value</code> and <code>status</code> together with the <code>statusMessage</code> prop.</p>
- example: 
```jsx 
() => {
  const [date, setDate] = React.useState(new Date())
  const [error, setError] = React.useState('')

  const handleValidation = ({ value }) => {
    if (new Date(value) <= new Date()) {
      setError('Enter a date that is in the future')
    } else {
      setError('')
    }
  }

  return (
    <FormField
      status={error ? 'error' : undefined}
      statusMessage={
        error ? error : 'Try entering a past date (e.g. 08/10/2000)'
      }
    >
      <DatePicker
        value={date}
        placeholderText="MM/DD/YYYY"
        onValidate={handleValidation}
        width="240px"
        excludePastDates
      />
    </FormField>
  )
}

```


    


## Common Use Case Examples


### Settings panel
- description: <p>Use the date picker to control the design of calendar components on the user’s site. </p>
- example: 
```jsx 
() => {
  const [selectedOption, setSelectedOption] = React.useState(0)
  const options = [
    { id: 0, value: 'Monday' },
    { id: 1, value: 'Sunday' },
  ]
  return (
    <SidePanel
      maxHeight="576px"
      width="288px"
      skin="floating"
      onCloseButtonClick={() => {}}
    >
      <SidePanel.Header title="Calendar Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Week starts on">
            <Dropdown
              value=""
              size="small"
              options={options}
              onSelect={(option) => setSelectedOption(option.id)}
              selectedId={selectedOption}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            legend="Set active days"
            legendSize="small"
            legendPlacement="top"
            direction="vertical"
            gap="12px"
          >
            <Checkbox size="small" checked>
              Monday
            </Checkbox>
            <Checkbox size="small" checked>
              Tuesday
            </Checkbox>
            <Checkbox size="small" checked>
              Wednesday
            </Checkbox>
            <Checkbox size="small" checked>
              Thursday
            </Checkbox>
            <Checkbox size="small" checked>
              Friday
            </Checkbox>
            <Checkbox size="small">Saturday</Checkbox>
            <Checkbox size="small">Sunday</Checkbox>
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Section title="Available dates">
          <SidePanel.Field>
            <FieldSet
              alignment="end"
              direction="horizontal"
              legendPlacement="none"
            >
              <FormField label="From">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="Start"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <FormField label="To">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="End"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <Tooltip content="Delete">
                <IconButton size="small" priority="secondary">
                  <Icons.DeleteSmall />
                </IconButton>
              </Tooltip>
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <TextButton size="small" prefixIcon={<Icons.AddSmall />}>
              Add Available Dates
            </TextButton>
          </SidePanel.Field>
        </SidePanel.Section>
        <SidePanel.Section title="Unavailable dates">
          <SidePanel.Field>
            <FieldSet
              alignment="end"
              direction="horizontal"
              legendPlacement="none"
            >
              <FormField label="From">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="Start"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <FormField label="To">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="End"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <Tooltip content="Delete">
                <IconButton size="small" priority="secondary">
                  <Icons.DeleteSmall />
                </IconButton>
              </Tooltip>
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <TextButton size="small" prefixIcon={<Icons.AddSmall />}>
              Add Unavailable Dates
            </TextButton>
          </SidePanel.Field>
        </SidePanel.Section>
      </SidePanel.Content>
    </SidePanel>
  )
}

```

### Together with time input
- description: <p>Use the date picker together with <code><TimeInput/></code> for scheduling appointments, events and more.</p>
- example: 
```jsx 
() => {
  const [startDate, setStartDate] = React.useState(new Date());
  const [endDate, setEndDate] = React.useState(new Date());

  return (
    <Layout cols={12}>
      <Cell span={6}>
        <FormField label="Start date" width="100%" statusMessage="mm/dd/yyyy">
          <Box gap={2}>
            <DatePicker
              value={startDate}
              onChange={setStartDate}
              placeholderText="Select date"
              width="80%"
            />
            <TimeInput />
          </Box>
        </FormField>
      </Cell>
      <Cell span={6}>
        <FormField label="End date" width="100%" statusMessage="mm/dd/yyyy">
          <Box gap={2}>
            <DatePicker
              value={endDate}
              onChange={setEndDate}
              placeholderText="Select date"
              width="80%"
            />
            <TimeInput />
          </Box>
        </FormField>
      </Cell>
    </Layout>
  );
};
```


