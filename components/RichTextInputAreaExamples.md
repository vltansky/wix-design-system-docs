
## Feature Examples


### Height
- description: <p>Control the height of the text area (excluding the toolbar):</p><p></p><li><code>minHeight</code> sets a minimum height in pixels.</li><li><code>maxHeight</code> sets a maximum height in pixels. Once the maximum height is reached, an inner scroll appears.</li><p></p><p>If undefined, the text area height is dynamic and grows or shrinks based on the user input.</p>
- example: 
```jsx 
<RichTextInputArea minHeight="120px" maxHeight="400px" />;
```

### Status
- description: <p>Control this component's status by using a <code>status</code> prop.  </p><li><code>error</code> demonstrates that required input is missing something or the entry was invalid.</li><li><code>warning</code> highlights an input value that might have a significant impact to a user.</li><li><code>loading</code> shows that text is being saved.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <RichTextInputArea status="error" placeholder="Error" />
  <RichTextInputArea status="warning" placeholder="Warning" />
  <RichTextInputArea status="loading" placeholder="Loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input area is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <RichTextInputArea placeholder="See message below" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <RichTextInputArea
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Text format
- description: <p>This component supports the following formatting:</p><li>Bold</li><li>Italic</li><li>Underline</li><li>Link</li><li>Bullet list</li><li>Numbered list</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <RichTextInputArea initialValue="<strong>Bold text</strong>" />
  <RichTextInputArea initialValue="<em>Italic text</em>" />
  <RichTextInputArea initialValue="<u>Underline text</u>" />
  <RichTextInputArea initialValue='<a target="_blank" href="http://www.wix.com">Link</a>' />
  <RichTextInputArea initialValue="<ul><li>Bullet list item</li><li>Bullet list item</li><li>Bullet list item</li></ul>" />
  <RichTextInputArea initialValue="<ol><li>Numbered list item</li><li>Numbered list item</li><li>Numbered list item</li></ol>" />
</StorybookComponents.Stack>;
```

### Custom button labels
- description: <p>Customize the label for each of the formatting buttons by using a <code>toolbarButtons</code> prop.</p>
- example: 
```jsx 
<RichTextInputArea
  placeholder="Hover on the toolbar items to view the custom button labels."
  texts={{
    toolbarButtons: {
      boldButtonLabel: 'Bold',
      italicButtonLabel: 'Italic',
      underlineButtonLabel: 'Underline',
      linkButtonLabel: 'Link',
      bulletedListButtonLabel: 'Bulleted list',
      numberedListButtonLabel: 'Numbered list',
    },
  }}
/>;
```

### Spell check
- description: <p>Enable standard browser spell check functionality with the <code>spellCheck</code> prop. This doesn't work on the IE browsers.</p>
- example: 
```jsx 
<RichTextInputArea
  spellCheck
  initialValue="This text is mispeled. Click here to see the error underlined in red."
/>;
```




    


## Common Use Case Examples


### Form
- description: <p>The rich text input area is often used when there are multiple paragraphs of text.</p><p></p><p>When content is longer than a sentence or two, text formatting greatly improves readability and allows people to scan easily. </p>
- example: 
```jsx 
<Card>
  <Card.Header title="Event description" />
  <Card.Divider />
  <Card.Content>
    <FormField label="Add more details about the event">
      <RichTextInputArea
        minHeight="120px"
        placeholder="Add details dates, schedule and speakers."
      />
    </FormField>
  </Card.Content>
</Card>;
```


