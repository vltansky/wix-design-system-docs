
## Feature Examples


### Size
- description: <p>Adjust the component size using the <code>size</code> prop. It supports 3 sizes:</p><li><code>large</code> - use when the input needs emphasis.</li><li><code>medium</code> (default) - use for all common cases.</li><li><code>small</code> - use in dense and narrow layouts.</li>
- example: 
```jsx 
() => {
  const options = [
    { id: 1, value: 'tag 1' },
    { id: 2, value: 'tag 2' },
    { id: 3, value: 'tag 3' },
  ];

  const renderMultiSelect = ({ size, tagSize }) => {
    const [tags, setTags] = React.useState([
      {
        size: tagSize,
        id: '1',
        label: 'tag 1',
      },
      {
        size: tagSize,
        id: '2',
        label: 'tag 2',
      },
    ]);

    const handleOnSelect = (tag) =>
      setTags([...tags, { id: tag.id, label: tag.value, size: tagSize }]);

    const handleOnRemoveTag = (tagId) =>
      setTags(tags.filter((currTag) => currTag.id !== tagId));

    return (
      <MultiSelect
        size={size}
        options={options}
        tags={tags}
        onSelect={handleOnSelect}
        onRemoveTag={handleOnRemoveTag}
      />
    );
  };

  return (
    <StorybookComponents.Stack flexDirection="column">
      <FormField label="Large">
        {renderMultiSelect({ size: 'large', tagSize: 'medium' })}
      </FormField>
      <FormField label="Medium">
        {renderMultiSelect({ size: 'medium', tagSize: 'small' })}
      </FormField>
      <FormField label="Small">
        {renderMultiSelect({ size: 'small', tagSize: 'tiny' })}
      </FormField>
    </StorybookComponents.Stack>
  );
};
```

### Status
- description: <p>Control the component status using the <code>status</code> prop. It supports 3 states:</p><li><code>error</code> - use to highlight an invalid input.</li><li><code>warning</code> - use to highlight inputs that impact users or can’t be validated.</li><li><code>loading</code> - use to show that the value is being uploaded to the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <VariableInput
    initialValue="{{status}} is error"
    variableParser={(value) => (value === 'status' ? 'Status' : false)}
    status="error"
  />
  <VariableInput
    initialValue="{{status}} is warning"
    variableParser={(value) => (value === 'status' ? 'Status' : false)}
    status="warning"
  />
  <VariableInput
    initialValue="{{status}} is loading"
    variableParser={(value) => (value === 'status' ? 'Status' : false)}
    status="loading"
  />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <VariableInput
        initialValue="See message {{below}}"
        variableParser={(value) => (value === 'below' ? 'below' : false)}
      />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <VariableInput
      initialValue="{{hover}} on status icon"
      variableParser={(value) => (value === 'hover' ? 'Hover' : false)}
      status="error"
      statusMessage="This is an error message."
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Read-only and disabled
- description: <p>Control input interaction with:</p><li><code>readOnly</code> - disables writing new values, but allows to copy the current value.</li><li><code>disabled</code> - disables all input interactions. Use to highlight unavailable functions.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <VariableInput
    initialValue="{{interactions}} are read only"
    variableParser={(value) =>
      value === 'interactions' ? 'Interactions' : false
    }
    readOnly
  />
  <VariableInput
    initialValue="{{interactions}} are disabled"
    variableParser={(value) =>
      value === 'interactions' ? 'Interactions' : false
    }
    disabled
  />
</StorybookComponents.Stack>;
```

### Rows
- description: <p>Set the height of a component to fit a specified number of text lines with <code>rows</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <VariableInput
    rows={1}
    initialValue="Example with 1 {{rows}}"
    variableParser={(value) => (value === 'rows' ? 'row' : false)}
  />
  <VariableInput
    rows={5}
    initialValue="Example with 5 {{rows}}"
    variableParser={(value) => (value === 'rows' ? 'rows' : false)}
  />
</StorybookComponents.Stack>;
```

### Multiline
- description: <p>Control content scroll direction with the <code>multiline</code> prop.</p><p></p><p>Multiline is allowed by default. Disabling it results in content scrolling horizontally inside of an input.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack width="50%">
    <VariableInput
      initialValue="Field that have {{multiline}} enabled scroll content vertically"
      multiline={true}
      variableParser={(value) => (value === 'multiline' ? 'multiline' : false)}
    />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack width="50%">
    <VariableInput
      initialValue="Field that have {{multiline}} disabled scroll content horizontally"
      multiline={false}
      variableParser={(value) => (value === 'multiline' ? 'multiline' : false)}
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Manual embed
- description: <p>Use a button outside of an input to allow user to embed variables from a predefined list manually.</p>
- example: 
```jsx 

() => {
  const bodyRef = React.useRef();
  const variables = [
    {
      key: 'event.date',
      value: 'Event date',
    },
    {
      key: 'last.name',
      value: 'Guest last name',
    },
    {
      key: 'first.name',
      value: 'Guest first name',
    },
    {
      key: 'event.location',
      value: 'Event location',
    },
    {
      key: 'event.name',
      value: 'Event name',
    },
  ];

  const insertVariable = variable =>
    bodyRef.current.insertVariable(variable.key);

  return (
    <Box gap="10px">
      <VariableInput
        placeholder="Pick variables and/ or enter strings..."
        variableParser={value => {
          const variable = variables.find(item => item.key === value);

          return variable ? variable.value : false;
        }}
        ref={bodyRef}
        rows={3}
      />
      <PopoverMenu triggerElement={<TextButton>Insert Variable</TextButton>}>
        {variables.map(variable => (
          <PopoverMenu.MenuItem
            text={variable.value}
            onClick={() => insertVariable(variable)}
          />
        ))}
      </PopoverMenu>
    </Box>
  );
};

```

### Automations
- description: Use the variable input to send personalized messages and updates.
- example: 
```jsx 

() => {
  const [selectedAction, setSelectedAction] = React.useState(1);

  return (
    <Card>
      <Card.Header
        title="Action"
        subtitle="Do this: send a message"
      ></Card.Header>
      <Card.Divider></Card.Divider>
      <Card.Content>
        <Layout>
          <Cell>
            <Layout gap="12px">
              <Cell span={4}>
                <Thumbnail
                  selected={selectedAction === 1}
                  onClick={() => setSelectedAction(1)}
                  title="Send a chat message"
                  size="small"
                />
              </Cell>
              <Cell span={4}>
                <Thumbnail
                  selected={selectedAction === 2}
                  onClick={() => setSelectedAction(2)}
                  title="Get notified by email"
                  size="small"
                />
              </Cell>
              <Cell span={4}>
                <Thumbnail
                  selected={selectedAction === 3}
                  onClick={() => setSelectedAction(3)}
                  title="Send email to contacts"
                  size="small"
                />
              </Cell>
            </Layout>
          </Cell>

          <Cell>
            <FormField label="Message" required>
              <VariableInput
                rows={5}
                initialValue="Hey {{user.name}}! Thanks for reaching out. We'll be right with you."
                variableParser={value =>
                  value === 'user.name' ? 'Name' : false
                }
              />
            </FormField>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};

```


