
## Feature Examples


### Direction
- description: <p>Control how the divider is placed with the <code>direction</code> prop.  </p><li><code>horizontal</code> separates content into rows.  </li><li><code>vertical</code> separates content into columns.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  Horizontal:
  <Divider direction="horizontal" />
  Vertical:
  <StorybookComponents.Stack height="50px" justifyContent="space-between">
    <Divider direction="vertical" />
    <Divider direction="vertical" />
    <Divider direction="vertical" />
    <Divider direction="vertical" />
    <Divider direction="vertical" />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Set the color of a divider with one of these values:</p><li><code>light</code> is the default for common cases on light backgrounds.</li><li><code>dark</code> is for common cases on dark backgrounds.</li><li><code>standard</code> is for light blue backgrounds.</li><li><code>warning</code> is for light orange backgrounds.</li><li><code>destructive</code> is for light red backgrounds.</li><li><code>success</code> is for light green backgrounds.</li><li><code>premium</code> is for light purple backgrounds.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Divider skin="light" />
  <Divider skin="dark" />
  <Divider skin="standard" />
  <Divider skin="warning" />
  <Divider skin="destructive" />
  <Divider skin="success" />
  <Divider skin="premium" />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Lists
- description: <p>Separate entities from one another with a divider for an easy-to-read list.</p>
- example: 
```jsx 
() => {
  const ListItem = ({ title, subtitle }) => {
    const [checked, setChecked] = React.useState(true);
    return (
      <Box align="space-between">
        <Box direction="vertical">
          <Text weight="normal">{title}</Text>
          <Text size="small" secondary>
            {subtitle}
          </Text>
        </Box>
        <Box gap="24px" verticalAlign="middle">
          <ToggleSwitch
            size="medium"
            checked={checked}
            onChange={() => setChecked(!checked)}
          />
          <TextButton>Edit</TextButton>
        </Box>
      </Box>
    );
  };

  return (
    <Card>
      <Card.Header title="Default emails" />
      <Card.Divider />
      <Card.Content>
        <Box direction="vertical" gap="18px">
          <ListItem
            title="Confirmation"
            subtitle="Let guests know their spot is confirmed"
          />
          <Divider />
          <ListItem
            title="Reminder"
            subtitle="Send a friendly reminder when the event is coming up"
          />
          <Divider />
          <ListItem
            title="Cancellation"
            subtitle="Notify guests if this event is canceled"
          />
        </Box>
      </Card.Content>
    </Card>
  );
};
```

### Separated content
- description: <p>Create a full-bleed divider to separate secondary content.</p>
- example: 
```jsx 
<Card>
  <MarketingLayout
    title="Add sessions to get booked"
    description="Set when this service is offered and the staff who provide it."
    actions={<Button size="small">Add Sessions</Button>}
    size="tiny"
    image={
      <Box align="right">
        <Image
          transparent
          width="120px"
          height="120px"
          src="PromotionalBookingsUpgrade.svg"
        />
      </Box>
    }
  />
  <Divider />
  <Box padding="12px 30px">
    <Text size="tiny" skin="standard">
      You can also add sessions directly from your <a>Calendar</a>
    </Text>
  </Box>
</Card>;
```


