
## Feature Examples


### Size
- description: <p>Control progress bar size with <code>size</code> prop:</p><li><code>large</code> is best for places where progress bar is the only element present.</li><li><code>medium</code> is for common use cases.</li><li><code>small</code> fits into smaller UI elements like cards and widgets.</li><li><code>tiny</code> is used for dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <CircularProgressBar size="large" label="Large" value={20} />
  <CircularProgressBar size="medium" label="Medium" value={20} />
  <CircularProgressBar size="small" label="Small" value={20} />
  <CircularProgressBar size="tiny" label="Tiny" value={20} />
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the appearance with <code>skin</code> prop. It supports 3 styles:</p><li><code>standard</code> is for common cases.</li><li><code>success</code> is best for highligthing the  positive effect of the process.</li><li><code>premium</code> is to prompt users to upgrade their plans to premium subscription. </li>
- example: 
```jsx 
<StorybookComponents.Background skin="light">
  <StorybookComponents.Stack padding="24px">
    <CircularProgressBar skin="standard" label="Standard" value="20" />
    <CircularProgressBar skin="success" label="Success" value="20" />
    <CircularProgressBar skin="premium" label="Premium" value="20" />
  </StorybookComponents.Stack>
</StorybookComponents.Background>;
```

### Light
- description: <p>Invert the skin of a progress bar with the <code>light</code> prop. Use this skin on backgrounds with colors or images.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value={20} skin="stanard" label="20%" />
      <CircularProgressBar value={20} skin="success" label="20%" />
      <CircularProgressBar value={20} skin="premium" label="20%" />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="dark">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value={20} skin="stanard" light label="20%" />
      <CircularProgressBar value={20} skin="success" light label="20%" />
      <CircularProgressBar value={20} skin="premium" light label="20%" />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
</StorybookComponents.Stack>;
```

### Progress indication
- description: <p>Add a label that indicates current progress in percentage with <code>showProgressIndication</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <CircularProgressBar value={20} />
  <CircularProgressBar showProgressIndication value={20} />
</StorybookComponents.Stack>;

```

### Error status
- description: <p>Let users now if process failed using <code>error</code> property.</p><p></p><p>Add text that explains what went wrong or what action the user should take with the <code>errorMessage</code> prop. Message will be revealed on hover over.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value="0" label="0%" />
      <CircularProgressBar value="20" label="20%" />
      <CircularProgressBar value="100" label="100%" />
      <CircularProgressBar
        value="20"
        label="Error"
        error
        errorMessage="This is the message that explains what went wrong."
      />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value="0" skin="success" label="0%" />
      <CircularProgressBar value="20" skin="success" label="20%" />
      <CircularProgressBar value="100" skin="success" label="100%" />
      <CircularProgressBar
        value="20"
        skin="success"
        label="Error"
        error
        errorMessage="This is the message that explains what went wrong."
      />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value="0" skin="premium" label="0%" />
      <CircularProgressBar value="20" skin="premium" label="20%" />
      <CircularProgressBar value="100" skin="premium" label="100%" />
      <CircularProgressBar
        value="20"
        skin="premium"
        label="Error"
        error
        errorMessage="This is the message that explains what went wrong."
      />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
</StorybookComponents.Stack>;
```

### Label
- description: <p>Add custom label for the progress bar using <code>label</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <CircularProgressBar value={20} />
  <CircularProgressBar label="1/5" value={20} />
</StorybookComponents.Stack>;

```

### Label placement
- description: <p>Control custom label position using <code>labelPlacement</code> prop:</p><li><code>bottom</code> (default)</li><li><code>center</code> </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value="20" label="1/5" />
      <CircularProgressBar value="20" skin="success" label="1/5" />
      <CircularProgressBar value="20" skin="premium" label="1/5" />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <CircularProgressBar value="20" label="1/5" labelPlacement="center" />
      <CircularProgressBar
        value="20"
        skin="success"
        label="1/5"
        labelPlacement="center"
      />
      <CircularProgressBar
        value="20"
        skin="premium"
        label="1/5"
        labelPlacement="center"
      />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Setup progress
- description: <p>Use circular progress bar to indicate users where they are in the feature or tool setup process. </p>
- example: 
```jsx 
<Layout>
  <Cell span={5}>
    <Card>
      <Card.Header title="SEO assistant" />
      <Card.Divider />
      <Card.Content>
        <Box direction="vertical" gap="SP2" paddingBottom="SP4">
          <CircularProgressBar
            size="medium"
            value="20"
            label="1/5"
            labelPlacement="center"
          />
          <Text weight="normal">SEO setup checklist</Text>
          <Text size="small" secondary>
            Fix current issues and follow recommendations to improve this site’s
            performance in search results.
          </Text>
        </Box>
        <Button priority="secondary" size="small">
          Continue Setup
        </Button>
      </Card.Content>
    </Card>
  </Cell>
</Layout>;
```


