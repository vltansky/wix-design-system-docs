
## Feature Examples


### Size
- description: Supports two sizes:<br/> 
        &emsp;- `small` - Use it next to small and tiny texts.<br/>
        &emsp;- `medium` Use it next to headings and medium texts.<br/>
- example: 
```jsx 

<StorybookComponents.Stack>
  <InfoIcon size="small" content="Small" />
  <InfoIcon size="medium" content="Medium" />
</StorybookComponents.Stack>;
```

### Adding a text link
- description: Use the `TextButton` with skin `light` when you need to add a link for more information.<br/><br/>
      The link should lead to Wix Help Center.
- example: 
```jsx 

<InfoIcon
  tooltipProps={{ maxWidth: '240px' }}
  content={
    <Box direction="vertical" gap="6px">
      <Text light size="small">
        This message explains the purpose of some feature.
      </Text>
      <TextButton size="small" underline="always" skin="light">
        Learn more about this feature
      </TextButton>
    </Box>
  }
/>;
```




    


## Common Use Case Examples


### Using InfoIcon in a form
- description: Some components like `FormField` and `SidePanel` appear with a built-in info icon.
        In other cases, insert the InfoIcon inline to a Text component. 
- example: 
```jsx 
<Card>
  <Card.Header
    title="Edit Jeniffer Meli's Profile"
    subtitle={
      <Text secondary>
        Note: Make sure your staff has given you the right to add their information and image
        <InfoIcon content="This information will be public and seen by customers" />
      </Text>
    }
  />
  <Divider />
  <Card.Content>
    <Layout>
      <Cell span={6}>
        <FormField label="Title">
          <Input defaultValue="Jeniffer Meli" />
        </FormField>
      </Cell>
      <Cell span={6}>
        <FormField
          label="Description"
          infoContent="Describe your staff member’s role and expertise. Clients will see this in the Staff Members Widget on your site."
        >
          <Input />
        </FormField>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;
```


