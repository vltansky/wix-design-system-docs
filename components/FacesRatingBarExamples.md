
## Feature Examples


### Mode
- description: <p>Specify the mode of component:</p><li><code>interactive</code> (default) - use it to collect individual feedback.</li><li><code>readOnly</code> - use it to display an overall rating.</li>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(3);
  return (
    <StorybookComponents.Stack>
      <FacesRatingBar value={value} onChange={setValue} />
      <FacesRatingBar value={3} readOnly />
    </StorybookComponents.Stack>
  );
};
```

### Description
- description: <p>Show descriptions for each face in a tooltip.</p><p></p><p>Descriptions will only be shown if all 5 labels are defined.</p>
- example: 
```jsx 
() => {
  const descriptionValues = [
    'Strong Negative',
    'Negative',
    'Neutral',
    'Positive',
    'Strong Positive',
  ];
  return <FacesRatingBar descriptionValues={descriptionValues} />;
};
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the rating bar by wrapping it in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
() => {
  const descriptionValues = [
    'Strong Negative',
    'Negative',
    'Neutral',
    'Positive',
    'Strong Positive',
  ];
  return (
    <FormField status="error" statusMessage="This is an error message.">
      <FacesRatingBar descriptionValues={descriptionValues} />
    </FormField>
  );
};
```




    


## Common Use Case Examples


### Collecting feedback
- description: Use an interactive mode to collect feedback from your users.
- example: 
```jsx 

() => {
  const [value, setValue] = React.useState(3);
  const descriptionValues = ['Terrible', 'Bad', 'Okay', 'Good', 'Great'];
  const renderRatingBar = (
    <FormField label="How was the help you received from customer support?">
      <FacesRatingBar
        value={value}
        descriptionValues={descriptionValues}
        onChange={setValue}
      />
    </FormField>
  );
  const renderInput = (
    <FormField label="Review (optional)">
      <InputArea
        minHeight="90px"
        placeholder="Describe your experience. What went well and where could we improve?"
      />
    </FormField>
  );
  return (
    <CustomModalLayout
      primaryButtonText="Send a Review"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => {}}
      title="Rate your experience"
    >
      <Layout>
        <Cell span={12}>{renderRatingBar}</Cell>
        <Cell span={12}>{renderInput}</Cell>
      </Layout>
    </CustomModalLayout>
  );
};
```

### Displaying feedback
- description: Use read only mode to display ratings.
- example: 
```jsx 

<Card>
  <Card.Content>
    <Box direction="vertical" gap="18px">
      <Heading size="tiny">Collaboration</Heading>
      <FacesRatingBar value={4} readOnly />
      <Box gap="12px">
        <Text weight="bold" size="small">
          Positive:
        </Text>
        <Text weight="thin" size="small">
          Knows how to work in a team, seems like a good team player.
        </Text>
      </Box>
    </Box>
  </Card.Content>
</Card>;
```


