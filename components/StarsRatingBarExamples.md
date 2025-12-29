
## Feature Examples


### Mode
- description: <p>Specify the mode of component:</p><li>Interactive (default) - used to collect individual feedback.</li><li><code>readOnly</code> - used to display overall rating.</li>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(3);

  return (
    <StorybookComponents.Stack>
      <StarsRatingBar value={value} onChange={setValue} />
      <StarsRatingBar value={3} readOnly />
    </StorybookComponents.Stack>
  );
};
```

### Size
- description: <p>Control the size of a component:</p><li><code>large</code></li><li><code>medium</code></li><li><code>small</code></li><li><code>tiny</code></li><p></p><p>Interactive mode, which requires input from the user, supports <code>large</code> and <code>medium</code> sizes only.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
<StorybookComponents.Stack flexDirection="column">
  <StarsRatingBar size="large" />
  <StarsRatingBar size="medium" />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <StarsRatingBar size="large" readOnly />
    <StarsRatingBar size="medium" readOnly />
    <StarsRatingBar size="small" readOnly />
    <StarsRatingBar size="tiny" readOnly />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Captions
- description: <p>Give more context to the rating scale by providing value labels.</p><p></p><p>Captions will be shown only if all 5 labels are defined.</p>
- example: 
```jsx 
() => {
  const descriptionValues = ['Very bad', 'Bad', 'Ok', 'Good', 'Very good'];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <StarsRatingBar descriptionValues={descriptionValues} value={1} />
      <StarsRatingBar descriptionValues={descriptionValues} value={2} />
      <StarsRatingBar descriptionValues={descriptionValues} value={3} />
      <StarsRatingBar descriptionValues={descriptionValues} value={4} />
      <StarsRatingBar descriptionValues={descriptionValues} value={5} />
    </StorybookComponents.Stack>
  );
};
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the rating bar by wrapping it in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<FormField status="error" statusMessage="This is an error message.">
  <StarsRatingBar />
</FormField>;
```




    


## Common Use Case Examples


### Collecting feedback
- description: Use an interactive rating bar to collect feedback from your users.
- example: 
```jsx 

() => {
  const [value, setValue] = React.useState(3);
  const descriptionValues = ['Very bad', 'Bad', 'Ok', 'Good', 'Very good'];

  const renderRatingBar = (
    <FormField label="How would you rate this app?">
      <StarsRatingBar
        descriptionValues={descriptionValues}
        value={value}
        onChange={setValue}
      />
    </FormField>
  );

  const renderReviewTitle = (
    <FormField label="Review Title">
      <Input placeholder="What's most important for people to know?" />
    </FormField>
  );

  const renderReview = (
    <FormField label="Review (optional)">
      <InputArea
        minHeight="90px"
        placeholder="Describe your experience. What did you like or dislike about this app?"
      />
    </FormField>
  );

  return (
    <CustomModalLayout
      primaryButtonText="Post Review"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => {}}
      title="Share Your Experience!"
    >
      <Layout gap="24px">
        <Cell span={12}>{renderRatingBar}</Cell>
        <Cell span={12}>{renderReviewTitle}</Cell>
        <Cell span={12}>{renderReview}</Cell>
      </Layout>
    </CustomModalLayout>
  );
};
```

### Displaying feedback
- description: <p>Use <code>readOnly</code> mode to display individual or general ratings of an item or service.</p>
- example: 
```jsx 

<Card>
  <Card.Content>
    <Box gap="18px">
      <Avatar color="A2" name={'John Doe'} />
      <Box direction="vertical" gap="6px">
        <Box>
          <Text size="small">Pauline0187 </Text>
          <Text size="small" secondary>
            / Apr 07, 2021
          </Text>
        </Box>
        <StarsRatingBar value={4} readOnly size="small" />
        <Text weight="bold">Amazing App, Amazing Support team</Text>
        <Text weight="thin">
          I love this app! I have a Membership only website with over 100 pages.
          Site Search let's a user type in any word they want to find on the
          site and it serv... <a>Read more</a>
        </Text>
      </Box>
    </Box>
  </Card.Content>
</Card>;
```


