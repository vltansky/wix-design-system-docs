
## Feature Examples


### Structure
- description: <p>The component consists of a radio and label that represents the selection value. By default, <code>label</code> is a text string but can be overridden to any other component or a set of components.</p>
- example: 
```jsx 
<Radio label="Label" />;
```

### States
- description: <p>Control the state of a component with:</p><li><code>checked</code> - use it to mark an active selection</li><li><code>disabled</code> - use it to mark an item that cannot be selected</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Radio label="Default" />
  <Radio label="Checked" checked />
  <Radio label="Disabled" disabled />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the radio button by wrapping it in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<FormField status="error" statusMessage="This is an error message.">
  <Radio label="Radio button" />
</FormField>;
```

### Alignment
- description: <p>Control radio alignment to a label with <code>alignItems</code> prop. It supports 2 values:</p><li><code>center</code> (default) - use it in all common cases</li><li><code>top</code> - use it to align a radio to the top to handle text overflow</li>
- example: 
```jsx 
<StorybookComponents.Stack width="300px">
  <Radio
    alignItems="top"
    label="Radio button label that wraps to multiple lines"
  />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Custom label
- description: <p>Any component or a set of components can be passed as a radio option label.</p>
- example: 
```jsx 
() => {
  const [checked, setChecked] = React.useState(false);

  return (
    <Radio
      checked={checked}
      onChange={() => setChecked(true)}
      label={
        <Cell>
          <Heading size="small">Free plan</Heading>
          <Text size="small" secondary>
            Offer your plan free of charge.
          </Text>
        </Cell>
      }
    />
  );
};
```

### Additional info
- description: <p>Use <code><InfoIcon/></code> to provide additional information about a selection.</p>
- example: 
```jsx 
() => {
  const [checked, setChecked] = React.useState(false);

  return (
    <Box inline gap="6px">
      <Radio
        label="Add total at checkout"
        checked={checked}
        onChange={() => setChecked(true)}
      />
      <InfoIcon content="Tax is charged to a customer, it won't be included in the price of your plans. They'll see it added to the price at a checkout." />
    </Box>
  );
};
```

### Custom layout
- description: <p>A radio can be used to build custom selection lists using <code><Card/></code> as a base for each option</p>
- example: 
```jsx 
() => {
  const [checkedId, setCheckedId] = React.useState(0);

  return (
    <Layout cols={1} gap="12px">
      <Card>
        <Box padding="18px 24px">
          <Radio
            checked={checkedId === 1}
            onChange={() => setCheckedId(1)}
            label={
              <Box direction="vertical">
                <Heading size="small">Free plan</Heading>
                <Text size="small" secondary>
                  Offer your plan free of charge
                </Text>
              </Box>
            }
          />
        </Box>
      </Card>
      <Card>
        <Box padding="18px 24px">
          <Radio
            checked={checkedId === 2}
            onChange={() => setCheckedId(2)}
            label={
              <Box direction="vertical">
                <Heading size="small">One time payment</Heading>
                <Text size="small" secondary>
                  Charge a single upfront fee
                </Text>
              </Box>
            }
          />
        </Box>
      </Card>
      <Card>
        <Box padding="18px 24px">
          <Radio
            checked={checkedId === 3}
            onChange={() => setCheckedId(3)}
            label={
              <Box direction="vertical">
                <Heading size="small">Recurring payment</Heading>
                <Text size="small" secondary>
                  Charge a weekly, monthly or yearly fee
                </Text>
              </Box>
            }
          />
        </Box>
      </Card>
    </Layout>
  );
};
```


