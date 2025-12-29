
## Feature Examples


### Size
- description: <p>Adjust the size of the input using the <code>size</code> prop. It supports 3 sizes:</p><li>For most common cases, use the default <code>medium.</code></li><li>To emphasize specific inputs in onboarding flows, use <code>large</code>.</li><li>Use <code>small</code> for more dense and compact layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Input size="large" placeholder="Large" />
  <Input size="medium" placeholder="Medium" />
  <Input size="small" placeholder="Small" />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Style the input using the <code>border</code> prop. It supports 4 styles:</p><li>For forms and most common cases, use <code>standard</code>.</li><li>To build inputs that can be used to filter data, use <code>round</code>.</li><li>Use <code>bottomLine</code> to create an editable, underlined title field.</li><li>When a component provides its own hover and focus styles, such as a table or spreadsheet cells, use <code>none</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Input border="standard" placeholder="Standard" />
  <Input border="round" placeholder="Round" />
  <Input border="bottomLine" placeholder="Bottom line" />
  <Input border="none" placeholder="None" />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control the status of the input using the <code>status</code> prop. It supports 3 states:</p><li><code>error</code> demonstrates that a required input is missing something or the entry was invalid.</li><li><code>warning</code>  highlights an input value that might have a significant impact to a user.</li><li><code>loading</code> shows when an input value is being uploaded to the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Input status="error" placeholder="Error" />
  <Input status="warning" placeholder="Warning" />
  <Input status="loading" placeholder="Loading" />
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
      <Input placeholder="See message below" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <Input
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
      tooltipPlacement="top-end"
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Read-only and disabled
- description: <p>Inputs can also be made read-only or disabled entirely.</p><li><code>readOnly</code> disables adding or editing, but allows the user to copy the current value. Use it to display URLs, code, etc.</li><li><code>disabled</code>removes all interactions and creates a disabled input state. Use it to highlight functions that are unavailable.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Input readOnly value="Read-only" />
  <Input disabled value="Disabled" />
</StorybookComponents.Stack>;
```

### Prefix &amp; suffix
- description: <p>Add text, icons or a button at the beginning or end of a text field using <code>prefix</code> and <code>suffix</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Input
    prefix={<Input.Affix>https://</Input.Affix>}
    suffix={<Input.Affix>.com</Input.Affix>}
    value=""
  />
  <Input
    prefix={
      <Input.IconAffix>
        <Icons.GitHub />
      </Input.IconAffix>
    }
    suffix={
      <Input.IconAffix>
        <TextButton>Button</TextButton>
      </Input.IconAffix>
    }
    value=""
  />
</StorybookComponents.Stack>;
```

### Clear button
- description: <p>Enable a button that lets users easily clear the input value by using the <code>clearButton</code> prop.</p>
- example: 
```jsx 
() => {
  const [inputText, setInputText] = React.useState(
    'Click the clear button to erase this value.',
  );

  return (
    <Input
      value={inputText}
      clearButton
      onChange={e => setInputText(e.target.value)}
      onClear={() => setInputText('')}
    />
  );
};
```

### Text overflow
- description: <p>Control long text values with the <code>textOverflow</code> prop. There are 2 options:</p><li><code>clip</code> (the default) cuts off text that is longer than the input field. </li><li><code>ellipsis</code> truncates the additional text with an ellipsis. This is especially useful with the <code>bottomLine</code> input style.</li>
- example: 
```jsx 
<Input
  textOverflow="ellipsis"
  border="bottomLine"
  value="This is an extremely long sentence that takes up far more space than can fit inside this input field, so it has to be shortened so that the beginning can be read, but with an ellipsis to indicate there is more text than can be shown at once."
/>;
```




    


## Common Use Case Examples


### Compound input
- description: <p>When multiple inputs represent the same kinds of data, like phone numbers or addresses, fields can be shown together under a single title using the <code><Layout/></code> component.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');

  const getDisplayValue = value => {
    const [, group1, group2, group3] = value
      .replace(/\D/g, '')
      .match(/(\d{0,2})(\d{0,3})(\d{0,4})/);
    return (
      (!group2 ? group1 : group1 + ' ') + group2 + (group3 ? '-' + group3 : '')
    );
  };

  const options = [
    listItemSelectBuilder({ id: 0, title: 'Israel', suffix: '+972' }),
    listItemSelectBuilder({ id: 1, title: 'Japan', suffix: '+81' }),
    listItemSelectBuilder({ id: 2, title: 'Australia', suffix: '+61' }),
  ];

  const onChange = e => {
    const { value } = e.target;
    if (value.length < 12) {
      setValue(getDisplayValue(value));
    }
  };

  const renderAutoComplete = () => (
    <AutoComplete
      popoverProps={{ placement: 'bottom-start' }}
      value="+972"
      options={options}
    />
  );

  return (
    <FormField label="Phone number">
      <Layout gap={6}>
        <Cell span={2}>{renderAutoComplete()}</Cell>
        <Cell span={10}>
          <Input placeholder="00 000-0000" onChange={onChange} value={value} />
        </Cell>
      </Layout>
    </FormField>
  );
};
```

### Input as a title
- description: <p>Inputs can also be used as card titles to help organize groups and files. This works best with the <code>bottomLine</code> border.</p>
- example: 
```jsx 
() => {
  const renderCard = (imageSrc, inputValue) => (
    <Card>
      <Box direction="vertical" padding="SP1 SP1 SP2">
        <Layout gap={12}>
          <Cell>
            <Box padding="6px 6px 0px">
              <Image borderRadius="4px" height="180px" src={imageSrc} />
            </Box>
          </Cell>

          <Cell>
            <Input
              border="bottomLine"
              textOverflow="ellipsis"
              defaultValue={inputValue}
            />
          </Cell>
        </Layout>
      </Box>
    </Card>
  );

  return (
    <Layout>
      <Cell span={6}>{renderCard('', 'Empty photo album')}</Cell>
      <Cell span={6}>{renderCard('example.jpg', 'Cooking recipes album')}</Cell>
    </Layout>
  );
};
```


