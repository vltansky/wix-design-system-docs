
## Feature Examples


### Size
- description: <p>Control the size of a heading with the <code>size</code> prop.</p><li><code>extraLarge</code> (heading tag – h1)</li><li><code>large</code> (h2)</li><li><code>medium</code> (h3)</li><li><code>small</code> (h4)</li><li><code>tiny</code> (h5)</li><li><code>extraTiny</code> (h6)</li><p></p><p>Note: Building a page with proper heading structure is essential for accessibility. If the heading size has a tag that doesn’t fit the structure, it should be overridden using the <code>as</code> prop (see the 'Custom HTML tag' section).</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Heading size="extraLarge">XL - Page Title (e.g., Contact List)</Heading>
  <Heading size="large">L - Modal title (e.g., Create a new contact)</Heading>
  <Heading size="medium">M - Card title (e.g., Subscribers)</Heading>
  <Heading size="small">S - Page section title (e.g., Contact info)</Heading>
  <Heading size="tiny">T - Card section title (e.g., Notes)</Heading>
  <Heading size="extraTiny">XT - Caption (e.g., Last activity)</Heading>
</StorybookComponents.Stack>;
```

### Light
- description: <p>Invert the skin of a heading with the <code>light</code> prop. Use this skin for headings on backgrounds with colors or images.  </p>
- example: 
```jsx 
<StorybookComponents.Background skin="dark">
  <StorybookComponents.Stack flexDirection="column" padding="30px">
    <Heading size="extraLarge" light>
      XL - Page Title (e.g., Contact List)
    </Heading>
    <Heading size="large" light>
      L - Modal title (e.g., Create a new contact)
    </Heading>
    <Heading size="medium" light>
      M - Card title (e.g., Subscribers)
    </Heading>
    <Heading size="small" light>
      S - Page section title (e.g., Contact info)
    </Heading>
    <Heading size="tiny" light>
      T - Card section title (e.g., Notes)
    </Heading>
    <Heading size="extraTiny" light>
      XT - Caption (e.g., Last activity)
    </Heading>
  </StorybookComponents.Stack>
</StorybookComponents.Background>;
```

### Ellipsis
- description: <p>By default, the header wraps if the text is too long, but can be truncated at the end of a sentence with the <code>ellipsis</code> prop. </p><p></p><p>Note: For accessibility, avoid using the <code>ellipsis</code> prop on headings. Keep all heading text visible on the screen at all times.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="400px">
  <Heading ellipsis>
    Create specific audiences with Segments
  </Heading>
</StorybookComponents.Stack>;
```

### Children
- description: <p>Render any kind of component within the <code><Heading> </code>tag. This is most commonly used to display an alternative style of text inline with the title.</p>
- example: 
```jsx 
() => {
  const renderHeadingWithDifferentColor = () => (
    <Box marginLeft="SP1" color="D40" inline>
      5
    </Box>
  );
  return (
    <Heading>
      Contact List
      {renderHeadingWithDifferentColor()}
    </Heading>
  );
};
```

### Custom HTML tag
- description: <p>Render the heading as an HTML tag with the <code>as</code> prop. </p><li>Using <code><h1></code> to <code><h6></code> overrides the default size heading tag. This is useful for creating an accessible page heading structure without changing the design.</li><li><code><div></code> or <code><span></code> can be used when a heading shouldn't be perceived as a title.</li><p></p><p>All attributes will be passed to the rendered HTML tag.</p>
- example: 
```jsx 
<Heading size="medium" as="h1">
  Medium size heading that appears as the main page header h1
</Heading>;
```




    


## Common Use Case Examples


### Content hierarchy
- description: <p>Use headings to emphasize main sections of a page and group related content together.</p>
- example: 
```jsx 
() => {
  const [address, setAddress] = React.useState('');

  const renderProfile = () => {
    return (
      <Cell>
        <Layout>
          <Cell>
            <Page.Section title="Main info" showDivider />
          </Cell>
          <Cell span={12}>
            <Card>
              <Card.Header title={<Heading size="medium">Profile</Heading>} />
              <Card.Divider />
              <Card.Content>
                <Layout>
                  <Cell span={8}>
                    <FormField label="Business name">
                      <Input placeholder="" />
                    </FormField>
                  </Cell>
                  <Cell span={8}>
                    <FormField label="Description">
                      <InputArea
                        placeholder="Use short, catchy text to tell people what your business offers."
                        minHeight={120}
                      />
                    </FormField>
                  </Cell>
                </Layout>
              </Card.Content>
            </Card>
          </Cell>
        </Layout>
      </Cell>
    );
  };
  const renderLocationAndAddress = () => (
    <>
      <Cell span={12}>
        <Heading size="tiny">Location</Heading>
        <Text size="small" secondary>
          Let customers know where your business is based. You can add one or
          multiple locations.
        </Text>
      </Cell>
      <Cell span={8}>
        <FormField label="Address">
          <AddressInput
            value={address}
            border="standard"
            onChange={(event) => setAddress(event.target.value)}
            onClear={() => setAddress('')}
          />
        </FormField>
      </Cell>
    </>
  );

  const renderContactInfo = () => (
    <>
      <Cell span={12}>
        <Heading size="tiny">Contact info</Heading>
        <Text size="small" secondary>
          Add your business details so people can get in touch easily.
        </Text>
      </Cell>
      <Cell span={4}>
        <FormField label="Email">
          <Input placeholder="" />
        </FormField>
      </Cell>
      <Cell span={4}>
        <FormField label="Phone">
          <Input placeholder="" />
        </FormField>
      </Cell>
    </>
  );

  const renderBusinessHours = () => (
    <>
      <Cell span={12}>
        <Heading size="tiny">Business hours</Heading>
        <Text size="small" secondary>
          Tell customers when your business is open.
        </Text>
      </Cell>
      <Cell span={8}>
        <Box
          padding="SP3 SP4"
          border="1px solid #c1e4fe"
          borderRadius="6px"
          verticalAlign="middle"
          align="space-between"
        >
          <Box direction="vertical" gap="3px">
            <Text size="small" weight="bold">
              Everyday
            </Text>
            <Text size="small" secondary>
              6:00AM - 8:00PM
            </Text>
          </Box>
          <Box>
            <TextButton size="small" prefixIcon={<Icons.EditSmall />}>
              Edit
            </TextButton>
          </Box>
        </Box>
      </Cell>
    </>
  );

  const renderLocationAndContactInfo = () => {
    return (
      <Cell>
        <Layout>
          <Cell>
            <Page.Section
              title="Location and contact info"
              showDivider
              actionsBar={
                <TextButton prefixIcon={<Icons.Add />}>Add Location</TextButton>
              }
            />
          </Cell>
          <Cell span={12}>
            <Card>
              <Card.Header
                title={<Heading size="medium">Default info</Heading>}
              />
              <Card.Divider />
              <Card.Content>
                <Layout>
                  {renderLocationAndAddress()}
                  <Cell span={12}>
                    <Divider />
                  </Cell>
                  {renderContactInfo()}
                  <Cell span={12}>
                    <Divider />
                  </Cell>
                  {renderBusinessHours()}{' '}
                </Layout>
              </Card.Content>
            </Card>
          </Cell>
        </Layout>
      </Cell>
    );
  };

  return (
    <Page>
      <Page.Header title="Business Info"></Page.Header>
      <Page.Content>
        <Layout>
          {renderProfile()}
          {renderLocationAndContactInfo()}
        </Layout>
      </Page.Content>
    </Page>
  );
};
```


