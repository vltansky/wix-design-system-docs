
## Feature Examples


### Status
- description: <p>Control the indication type with the <code>status</code> prop:</p><li><code>error</code> - use it to highlight invalid values, failed actions and processes.</li><li><code>warning</code> - use it to highlight areas that require extra attention, like if a password has been compromised.</li><li><code>success</code> - use it to highlight valid values, successful actions or processes.</li><li><code>loading</code> - use it to show that an input value is being loaded.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack alignItems="center">
    <StatusIndicator status="error" />
    <Text>Error</Text>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack alignItems="center">
    <StatusIndicator status="warning" />
    <Text>Warning</Text>
  </StorybookComponents.Stack>
    <StorybookComponents.Stack>
    <StatusIndicator status="success" />
    <Text>Success</Text>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <StatusIndicator status="loading" />
    <Text>Loading</Text>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Message
- description: <p>Explain the status with a <code>message</code> prop.</p><p></p><p>The message is revealed in a tooltip when the users’ mouse hovers over the status icon.</p>
- example: 
```jsx 
<StatusIndicator message="Message in a tooltip explains the status" />;
```

### Tooltip placement
- description: <p>Position the tooltip with the <code>tooltipPlacement</code> prop:</p><li><code>top</code> (default)</li><li><code>right</code></li><li><code>bottom</code></li><li><code>left</code></li>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="center">
  <Text>Top:</Text>
  <StatusIndicator message="Top" tooltipPlacement="top" />
  <Text>Left:</Text>
  <StatusIndicator message="Left" tooltipPlacement="left" />
  <Text>Bottom:</Text>
  <StatusIndicator message="Bottom" tooltipPlacement="bottom" />
  <Text>Right:</Text>
  <StatusIndicator message="Right" tooltipPlacement="right" />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Built-in part of form elements
- description: <p>A status indicator is used as a building block for a variety of form components that require validation or data processing. Avoid using these indicators for status messages unless absolutely necessary, like for very compact layouts.</p><p></p><p>Showing the status message directly below the component is preferred in all default cases. For this, use <code><FormField/></code> prop <code>statusMessage</code>.</p>
- example: 
```jsx 
<Layout gap="48px">
  <Cell span={4}>
    <Box direction="vertical" gap="12px">
      <Heading size="tiny">For narrow layouts only:</Heading>
      <Box direction="vertical" gap="40px">
        <FormField label="Product name">
          <Input status="error" statusMessage="This field is mandatory" />
        </FormField>
        <FormField label="Select color">
          <AutoComplete
            status="warning"
            value="Green"
            statusMessage="This color already exists"
          />
        </FormField>
      </Box>
    </Box>
  </Cell>
  <Cell span={8}>
    <Box direction="vertical" gap="12px">
      <Heading size="tiny">For all default cases:</Heading>
      <FormField
        label="Product name"
        status="error"
        statusMessage="This field is mandatory"
      >
        <Input />
      </FormField>
      <FormField
        label="Select color"
        status="warning"
        statusMessage="This color already exists"
      >
        <AutoComplete value="Green" />
      </FormField>
    </Box>
  </Cell>
</Layout>;
```


