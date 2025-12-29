
## Feature Examples


### Dimensions
- description: <p>Specify the component's dimensions in pixels or by percentage using the <code>width</code> and <code>height</code> properties.</p>
- example: 
```jsx 
<ImageViewer width="35%" height="240px" />;
```

### Status
- description: <p>Control the component's status using the <code>status</code> prop. It supports three states:</p><li><code>error</code> indicates when an image failed to upload.</li><li><code>warning</code> highlights that the media can’t be validated.</li><li><code>loading</code> shows that the media file is loading.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ImageViewer status="error" />
  <ImageViewer status="warning" />
  <ImageViewer status="loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the image viewer is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <ImageViewer />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <ImageViewer status="error" statusMessage="This is an error message." />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### States
- description: <p>Supports two states:</p><li>No image source - uses <AddItem/> component to upload media in a required way. Use <code>addImageInfo</code> to specify a message to display in a tooltip when users hover over the component.</li><li>With image source - use <code>imageUrl</code> prop to pass a link to a media file.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ImageViewer />
  <ImageViewer imageUrl="example.jpg" />
</StorybookComponents.Stack>;
```

### Border radius
- description: <p>Remove default corner radius with the <code>removeRoundedBorders</code> prop. Use it when component is used as a part of another widget.</p>
- example: 
```jsx 
<ImageViewer imageUrl="example.jpg" removeRoundedBorders />;
```

### Disabled
- description: <p>Disable all viewer interactions with the <code>disabled</code> prop. Use it to highlight unavailable functions.</p><p></p><p>Customize the tooltip's style with all common <code>tooltipProps</code>.</p>
- example: 
```jsx 
<ImageViewer disabled addImageInfo="Message explaining disabled item status" />;
```

### Actions
- description: <p>Control which actions are visible with the <code>showUpdateButton</code>, <code>showDownloadButton</code> and <code>showRemoveButton</code> props. Tooltip messages explaining the actions can be customized according to their need.</p>
- example: 
```jsx 
<ImageViewer
  imageUrl="example.jpg"
  showUpdateButton={true}
  showDownloadButton={true}
  showRemoveButton={true}
  updateImageInfo="Change image"
  downloadImageInfo="Download image"
  removeImageInfo="Delete image"
  moreImageInfo="More actions"
/>;
```




    


## Common Use Case Examples


### Form
- description: <p>Use image viewer in forms where only a single image can be uploaded at a time, e.g., a cover for an event, group or program.</p>
- example: 
```jsx 
<Card>
  <Card.Header title="Program info" />
  <Card.Divider />
  <Card.Content>
    <Layout>
      <Cell span={8}>
        <Box direction="vertical" gap="12px">
          <FormField label="Program name" required>
            <Input value="Sugar Reset" />
          </FormField>
          <FormField label="Description">
            <InputArea
              value="Want to feel better, have more energy and trim down your waistline at the same time? Removing refined and added sugar from your diet is for you!"
              resizable
              maxLength={100}
              hasCounter
              minHeight={120}
            />
          </FormField>
        </Box>
      </Cell>
      <Cell span={4}>
        <FormField label="Cover image">
          <ImageViewer imageUrl="FoodExample1.jpg" height="218px" />
        </FormField>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;
```


