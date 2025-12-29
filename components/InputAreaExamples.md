
## Feature Examples


### Size
- description: <p>Adjust the size of the input using the <code>size</code> prop. It supports 2 sizes:</p><li>For most common cases, use the default <code>medium.</code></li><li>Use <code>small</code> for more dense and compact layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputArea placeholder="Medium" size="medium" />
  <InputArea placeholder="Small" size="small" />
</StorybookComponents.Stack>;
```

### Height
- description: <p>Control the height of an area by defining a minimum or maximum number of pixels, or a certain number of rows.</p><li>To define the minimum and maximum height in pixels, use <code>minHeight</code> and <code>maxHeight</code>.</li><li>Define the height of a specified number of rows with <code>rows</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputArea
    placeholder="Height defined in pixels"
    minHeight="120px"
    maxHeight="300px"
  />
  <InputArea placeholder="Height that fits 4 rows of text" rows={4} />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control the status of the input using the <code>status</code> prop. It supports 3 states:</p><li><code>error</code> demonstrates that a required input is missing something or the entry was invalid.</li><li><code>warning</code>  highlights an input value that might have a significant impact to a user.</li><li><code>loading</code> shows when an input value is being uploaded to the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputArea placeholder="Error" status="error" />
  <InputArea placeholder="Warning" status="warning" />
  <InputArea placeholder="Loading" status="loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the component is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <InputArea placeholder="See message below" tooltipPlacement="top-end" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <InputArea
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
      tooltipPlacement="top-end"
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Read-only and disabled
- description: <p>Inputs can also be made read-only or disabled entirely.</p><li><code>readOnly</code> disables adding or editing, but allows the user to copy the current value.</li><li><code>disabled</code>removes all interactions and creates a disabled input state. Use it to highlight functions that are unavailable.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputArea value="Read-only" readOnly />
  <InputArea value="Disabled" disabled />
</StorybookComponents.Stack>;
```

### Resize
- description: <p>Allow users to manually adjust the size of the input area by enabling the<code>resizable</code> prop.</p>
- example: 
```jsx 
<InputArea
  placeholder="Drag the handle in the bottom right corner to change the height of an area."
  resizable
/>;
```

### Character count
- description: <p>Indicate how many characters the input area contains by enabling the <code>hasCounter</code> prop. To display a counter, specify the <code>maxLength</code> of characters allowed in the field.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(
    'This is a sentence that uses only some of the allowed characters.',
  );

  return (
    <InputArea
      value={value}
      onChange={e => setValue(e.target.value)}
      maxLength={100}
      hasCounter
    />
  );
};
```

### Auto grow
- description: <p>Grow and shrink area size according to the input by enabling <code>autoGrow</code>. Specify the starting height of an area with <code>minRowsAutoGrow</code>.</p>
- example: 
```jsx 
<InputArea
  placeholder="Enter a lot of text into this area to see how it grows according to the length of content."
  autoGrow={true}
  minRowsAutoGrow={1}
/>;
```

### Auto select
- description: <p>Click to select/highlight all the text in the area with the <code>autoSelect</code> prop.</p>
- example: 
```jsx 
<InputArea value="Click on the field to select the entire text." autoSelect />;
```




## Developer Examples


### Controlled
- description: <p>Component can be used in controlled mode by passing <code>value</code> and <code>onChange</code> props.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(0);
  return <InputArea value={value} onChange={(e) => setValue(e.target.value)} />;
};

```

### Force autogrow when controlled externally
- description: <p>Auto grow feature does not work when component is used in controlled way which means using <code>value</code> and <code>onChange</code> properties. To force auto grow behaviour on state change just call ref method of component called <code>calculateComputedRows</code> which will recalculate rows on every value change.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');
  const ref = React.useRef();

  React.useEffect(() => {
    ref.current?.calculateComputedRows();
  }, [value]);

  const onInsertText = () => {
    setValue((prevValue) => prevValue + 'field grows on every click ');
  };

  return (
    <StorybookComponents.Stack width="100%" justifyContent="space-between">
      <Button onClick={onInsertText}>Insert Text</Button>
      <div style={{ width: '100%' }}>
        <InputArea
          ref={ref}
          value={value}
          onChange={(e) => setValue(e.target.value)}
          autoGrow
          placeholder="Click on Insert Text"
          minRowsAutoGrow={1}
        />
      </div>
    </StorybookComponents.Stack>
  );
};

```


    


## Common Use Case Examples


### Forms
- description: <p>Use input area when the user needs to enter multiple lines of text such as product descriptions and policies.</p><p></p><p>Use <code><FormField/></code> to provide a label for the field.</p>
- example: 
```jsx 
() => {
  const [visibleChecked, setVisibleChecked] = React.useState(true);
  const [nameInputValue, setNameInputValue] = React.useState('My New Menu');
  const [value, setValue] = React.useState('');

  return (
    <CustomModalLayout
      primaryButtonText="Create Menu"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => {}}
      title="Create new menu"
    >
      <Layout gap="24px">
        <Cell span={12}>
          <FormField label="Name">
            <Input
              value={nameInputValue}
              onChange={e => setNameInputValue(e.target.value)}
            />
          </FormField>
        </Cell>
        <Cell span={12}>
          <FormField label="Description">
            <InputArea
              placeholder="Get people excited about your menu and your food."
              rows={4}
              maxLength={300}
              hasCounter
              resizable
              value={value}
              onChange={e => setValue(e.target.value)}
            />
          </FormField>
        </Cell>
        <Cell span={12}>
          <FormField
            label="Visible to customers"
            labelPlacement="right"
            stretchContent={false}
          >
            <ToggleSwitch
              checked={visibleChecked}
              onChange={() => setVisibleChecked(!visibleChecked)}
            />
          </FormField>
        </Cell>
      </Layout>
    </CustomModalLayout>
  );
};
```

### Settings panel
- description: <p>Use input area in settings panels to allow users to edit longer descriptions and titles.</p><p></p><p></p><p></p><p></p><p></p><p></p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');
  return (
    <SidePanel maxHeight="576px" width="288px" skin="floating">
      <SidePanel.Header title="Text Box Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Description">
            <InputArea
              placeholder="This input area is great for longer descriptions with multiple lines of text." size="small"
              rows={3}
              maxLength={300}
              hasCounter
              resizable
              value={value}
              onChange={(e) => setValue(e.target.value)}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="What does the button do?">
            <SegmentedToggle size="small" defaultSelected="Open">
              <SegmentedToggle.Button value="Open">
                Expand
              </SegmentedToggle.Button>
              <SegmentedToggle.Button value="Closed">
                Link
              </SegmentedToggle.Button>
            </SegmentedToggle>
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="Link button text">
            <Input size="small" placeholder="Link to full article" />
          </FormField>
        </SidePanel.Field>
      </SidePanel.Content>
    </SidePanel>
  );
};  
```


