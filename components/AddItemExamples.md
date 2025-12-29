
## Feature Examples


### Size
- description: <p>Control the size of a component with <code>size</code> prop:</p><li><code>large</code> - use when item height is >212 px.</li><li><code>medium</code> - use when item height is between 162 px and 212 px.</li><li><code>small</code> - use when item height is between 120 px and 162 px.</li><li><code>tiny</code> (default) - use when item height is between 48 px and 120 px.</li><p></p><p><code>size</code> prop affects component's padding and icon size. Its height and width also depend on a parent container.</p><p></p><p>Minimum height of a component is:</p><li>48 px for <code>dashes</code>,</li><li>42 px for <code>plain</code>, and</li><li>81×81 px for <code>image</code> themes.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddItem size="large">Large</AddItem>
  <AddItem size="medium">Medium</AddItem>
  <AddItem size="small">Small</AddItem>
  <AddItem size="tiny">Tiny</AddItem>
</StorybookComponents.Stack>;
```

### Theme
- description: <p>Control the style of a component with <code>theme</code> prop:</p><li><code>dashes</code> (default) - use it outside of a card, in a table or a list that contains images.</li><li><code>plain</code> - use for in-card lists and tables that mainly consist of text.</li><li><code>filled</code> - use for small in-card items, when a prominent call to action is needed.</li><li><code>image</code> - use to add images inside a card.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddItem theme="dashes">Dashes</AddItem>
  <AddItem theme="plain">Plain</AddItem>
  <AddItem theme="filled">Filled</AddItem>
  <AddItem theme="image">Image</AddItem>
</StorybookComponents.Stack>;
```

### Alignment
- description: <p>Control content alignment with <code>alignItems</code> prop:</p><li><code>left</code></li><li><code>center</code> (default)</li><li><code>right</code></li><p></p><p>Use <code>left</code> alignment with a <code>plain</code> component theme to maintain visual consistency with a remaining list inside a card.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddItem theme="plain" alignItems="left">
    Left
  </AddItem>
  <AddItem theme="plain" alignItems="center">
    Center
  </AddItem>
  <AddItem theme="plain" alignItems="right">
    Right
  </AddItem>
</StorybookComponents.Stack>;
```

### Padding
- description: <p>Control whether a component has padding with <code>removePadding</code> prop.</p><p></p><p>Use it in special cases only, when component is used in dense and narrow layouts.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddItem>Default</AddItem>
  <AddItem removePadding>No padding</AddItem>
</StorybookComponents.Stack>;
```

### Border radius
- description: <p>Control the border radius of a component with <code>borderRadius</code> prop.</p><p></p><p>By default, component has a corner radius of 8 px. Change it in custom scenarios, for example, when user needs to add a round avatar photo.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="min-content" height="100px">
  <AddItem borderRadius="8px" />
  <AddItem borderRadius="100%" />
</StorybookComponents.Stack>;
```

### Title
- description: <p>Emphasize action with a <code>title</code>.</p><p></p><p>If no title is shown, display it in a tooltip on item hover with <code>tooltipContent</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddItem>Title</AddItem>
  <AddItem tooltipContent="Title"></AddItem>
</StorybookComponents.Stack>;
```

### Subtitle
- description: <p>Add a description below the title using <code>subtitle</code> prop.</p><p></p><p>Use it to explain item details, such as a supported file format of a maximum allowed file size.</p>
- example: 
```jsx 
<AddItem subtitle="Subtitle">Title</AddItem>;
```

### Icon
- description: <p>Control a '+' icon visibility with <code>showIcon</code> prop. The icon is always shown by default.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddItem>Default</AddItem>
  <AddItem showIcon={false}>No icon</AddItem>
</StorybookComponents.Stack>;
```

### Custom icon or illustration
- description: <p>Override a default '+' icon with a custom icon or illustration by passing it to <code>icon</code> prop. </p><p></p><p>Align dimensions of the icon or illustration based on add item <code>size</code>:</p><li>Use S2 illustrations in <code>large</code> and <code>medium</code> size components.</li><li>Use S1 for <code>small</code> size component.</li><li>Use 24×24 px or 18×18 px icons for <code>tiny</code> size component.</li>
- example: 
```jsx 
<StorybookComponents.Stack width="50%" flexDirection="column">
  <Box height="212px">
    <AddItem
      size="large"
      icon={
        <StorybookComponents.Placeholder width="96px" height="96px">
          <StorybookComponents.Stack
            justifyContent="center"
            height="100%"
            alignItems="center"
          >
            <Text weight="bold" secondary>
              S2
            </Text>
          </StorybookComponents.Stack>
        </StorybookComponents.Placeholder>
      }
    >
      Large
    </AddItem>
  </Box>
  <Box height="162px">
    <AddItem
      size="medium"
      icon={
        <StorybookComponents.Placeholder width="96px" height="96px">
          <StorybookComponents.Stack
            justifyContent="center"
            height="100%"
            alignItems="center"
          >
            <Text weight="bold" secondary>
              S2
            </Text>
          </StorybookComponents.Stack>
        </StorybookComponents.Placeholder>
      }
    >
      Medium
    </AddItem>
  </Box>
  <Box height="120px">
    <AddItem
      size="small"
      icon={
        <StorybookComponents.Placeholder width="60px" height="60px">
          <StorybookComponents.Stack
            justifyContent="center"
            height="100%"
            alignItems="center"
          >
            <Text weight="bold" secondary>
              S1
            </Text>
          </StorybookComponents.Stack>
        </StorybookComponents.Placeholder>
      }
    >
      Small
    </AddItem>
  </Box>
  <Box>
    <AddItem size="tiny" icon={<Icons.Image />}>
      Tiny
    </AddItem>
  </Box>
  <Box>
    <AddItem size="tiny" icon={<Icons.ImageSmall />}>
      Tiny with small icon
    </AddItem>
  </Box>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Disable all component interactions with <code>disabled</code> prop. Use it to show that no new item can be added to the list at a moment.</p>
- example: 
```jsx 
<AddItem disabled>Disabled</AddItem>;
```

### Tooltip
- description: <p>Describe add item action with <code>tooltipContent</code>. Tooltip is shown when users hover on the item with a mouse.</p><p></p><p>Control tooltip design with <code>tooltipProps</code>. </p>
- example: 
```jsx 
<AddItem
  tooltipContent="Description for the add item action"
  tooltipProps={{ placement: 'bottom' }}
>
  Hover to see tooltip
</AddItem>;
```




    


## Common Use Case Examples


### Inside a card
- description: <p>Use Add item to create a new item inside a card.</p><p></p><p>When the list consists mainly of textual content, use <code>plain</code> theme and adjust component's <code>alignment</code>.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      option: `Size`,
      vars: 'S, M, L',
    },
    {
      option: `Colors`,
      vars: 'Black, Neutral, White',
    },
    {
      option: 'Material',
      vars: 'Cotton, Eco leather',
    },
  ];

  const columns = [
    { title: 'Option', render: (row) => row.option },
    { title: 'Variations', render: (row) => row.vars },
  ];

  return (
    <Box>
      <Card hideOverflow>
        <Card.Header title="Product options"></Card.Header>
        <Table data={records} columns={columns} rowVerticalPadding="medium">
          <Table.Content />
          <AddItem theme="plain" alignItems="left">
            Add New Option
          </AddItem>
        </Table>
      </Card>
    </Box>
  );
};
```

### Inside a page
- description: <p>Use Add item's <code>dashed</code> theme when component is placed directly inside of a <code><Page/></code> layout.</p>
- example: 
```jsx 
<Page>
  <Page.Header title="Events" />
  <Page.Content>
    <Layout>
      <Cell span={12}>
        <Box height={160}>
          <Box align="center" verticalAlign="middle" width={180}>
            <Image
              height="180px"
              borderRadius="8px 0px 0px 8px"
              src="running_man.png"
            />
          </Box>
          <Box
            direction="vertical"
            borderRadius="0px 8px 8px 0px"
            verticalAlign="space-between"
            padding="18px 24px"
            backgroundColor="D80"
            flexGrow={1}
          >
            <Box verticalAlign="space-between" flexGrow={1}>
              <Box direction="vertical" gap="3px">
                <Heading size="small">Get running!</Heading>
                <Text size="small" secondary>
                  Scheduled for April 26, 2021
                </Text>
              </Box>
            </Box>
            <Box align="space-between">
              <Box gap="24px">
                <Box verticalAlign="middle" gap="0px">
                  <Icons.LockUnlockedSmall />
                  <Box marginLeft={1}>
                    <Text size="small">Public</Text>
                  </Box>
                </Box>
                <Box verticalAlign="middle">
                  <Box marginLeft={1}>
                    <Text size="small">Join for Free</Text>
                  </Box>
                </Box>
              </Box>
              <Box>
                <Box verticalAlign="middle">
                  <Box gap="SP2">
                    <IconButton priority="secondary" size="small">
                      <Icons.MoreSmall />
                    </IconButton>
                    <Button priority="secondary" size="small">
                      Edit
                    </Button>
                  </Box>
                </Box>
              </Box>
            </Box>
          </Box>
        </Box>
      </Cell>
      <Cell>
        <Box height={160}>
          <AddItem size="small">Add New Event</AddItem>
        </Box>
      </Cell>
    </Layout>
  </Page.Content>
</Page>;
```

### Add images
- description: <p>Use Add item to upload images.</p><p></p><p>For this, select <code>image</code> theme and show the title inside a tooltip on mouse hover.</p>
- example: 
```jsx 
<Card>
  <Card.Header title="Profile" />
  <Card.Divider />
  <Card.Content>
    <Layout>
      <Cell span={6}>
        <Box direction="vertical" gap="4">
          <FormField labelSize="small" label="Business name">
            <Input placeholder="" />
          </FormField>
          <FormField labelSize="small" label="Short description">
            <InputArea
              placeholder="Add more details about your business."
              rows={3}
              hasCounter
              resizable
            />
          </FormField>
        </Box>
      </Cell>
      <Cell span={6}>
        <FormField labelSize="small" label="Logo">
          <Dropzone onDrop={() => {}}>
            <Dropzone.Content>
              <FileUpload>
                {({ openFileUploadDialog }) => (
                  <Box height="168px">
                    <AddItem
                      theme="image"
                      tooltipContent="Add Logo"
                      size="medium"
                      onClick={openFileUploadDialog}
                    />
                  </Box>
                )}
              </FileUpload>
            </Dropzone.Content>
          </Dropzone>
        </FormField>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;
```


