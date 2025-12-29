
## Feature Examples


### Structure
- description: <p>Card layouts can vary, but they can include up to four related components:</p><li><code><Card.Header/></code><a href="https://www.wix-style-react.com/storybook/?path=%2Fstory%2Fcomponents-layout-card--card-header"></a></li><li><code><SectionHeader/></code></li><li><code><Card.Content/></code></li><li><code><Card.Divider/></code><a href="https://www.wix-style-react.com/storybook/?path=%2Fstory%2Fcomponents-layout-card--card-divider"></a></li>
- example: 
```jsx 
<Card>
  <Card.Header title="Card header"></Card.Header>
  <SectionHeader title="Section header" />
  <Card.Content>
    <StorybookComponents.Placeholder height="120px">
      Card content
    </StorybookComponents.Placeholder>
  </Card.Content>
</Card>;
```

### Header
- description: <p>The <code><Card.Header/></code> communicates what the card is about.  It can include three elements:</p><li><code>title</code></li><li><code>subtitle</code> </li><li><code>suffix</code> </li><p></p><p>The suffix can be a button or toggle component.  </p>
- example: 
```jsx 
<Card>
  <Card.Header
    title="Title"
    subtitle="Subtitle"
    suffix={<TextButton>Suffix</TextButton>}
  ></Card.Header>
  <Card.Divider />
  <Card.Content>
    <Box height="120px"/>
  </Card.Content>
</Card>;
```

### Section header
- description: <p>The <code><SectionHeader/></code> divides card content into scannable sections. It can include two elements:</p><p></p><li><code>title</code></li><li><code>suffix</code> </li><p></p><p>Find more information in <code><SectionHeader/></code> story.</p>
- example: 
```jsx 
<Card>
  <Card.Header title="Title" />
  <SectionHeader
    title="Section header title"
    suffix={<TextButton size="small">Suffix</TextButton>}
  ></SectionHeader>
  <Card.Content>
    <Box height="120px" />
  </Card.Content>
</Card>;
```

### Content
- description: <p>Cards can support any type of content. For example, text, radio buttons, and tables all can be used in cards as child components.</p>
- example: 
```jsx 
<Card>
  <Card.Header title="Title" />
  <Card.Divider />
  <Card.Content>
    <StorybookComponents.Placeholder height="120px">
      Content
    </StorybookComponents.Placeholder>
  </Card.Content>
</Card>;
```

### Divider
- description: <p>Dividers separate different content sections within cards.</p><p></p><p>When there's no <code><SectionHeader/></code>, use a divider to separate the header from other content.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Card>
    <Card.Header title="Title" />
    <Card.Divider />
    <Card.Content>
      <Box height="120px" />
    </Card.Content>
  </Card>
  <Card>
    <Card.Header title="Title" />
    <Card.Divider />
    <Card.Content>
      <Layout>
        <Cell span={12}>
          <Box height="120px" />
        </Cell>
        <Cell span={12}>
          <Card.Divider />
        </Cell>
        <Cell span={12}>
          <Box height="120px" />
        </Cell>
      </Layout>
    </Card.Content>
  </Card>
</StorybookComponents.Stack>;
```

### Controls
- description: <p>Add the <code><CloseButton/></code>  (with a default or a help icon) to cards using the <code>controls</code> prop.</p>
- example: 
```jsx 
<Card controls={<CloseButton size="large" skin="dark" />}>
  <Card.Header title="Title" />
  <Card.Divider />
  <Card.Content>
    <Box height="120px" />
  </Card.Content>
</Card>;
```

### Hide overflow
- description: <p>Clip card content into specific card dimensions with the <code>hideOverflow</code> prop.</p><p></p><p>Apply this property when a card contains overflowing components inside, like a scrollable table.</p>
- example: 
```jsx 
<Layout>
  <Cell>
    <StorybookComponents.Stack flexDirection="column" height="300px">
      <Card hideOverflow={true}>
        <Card.Header title="Hidden overflow" />
        <Card.Divider />
        <Card.Content>
          <StorybookComponents.Placeholder height="500px" />
        </Card.Content>
      </Card>
    </StorybookComponents.Stack>
  </Cell>
</Layout>;
```

### Stretch vertically
- description: <p>To make cards expand vertically to fit more content, use the <code>stretchVertically</code> prop.</p>
- example: 
```jsx 
<Layout cols={12}>
  <Cell span={12}>
    <Text secondary weight="normal">
      Default
    </Text>
  </Cell>
  <Cell span={12}>
    <Layout cols={12}>
      <Cell span={4}>
        <Card>
          <Card.Content>
            <StorybookComponents.Placeholder height="180px" />
          </Card.Content>
        </Card>
      </Cell>
      <Cell span={4}>
        <Card>
          <Card.Content>
            <StorybookComponents.Placeholder height="120px" />
          </Card.Content>
        </Card>
      </Cell>
      <Cell span={4}>
        <Card>
          <Card.Content>
            <StorybookComponents.Placeholder height="60px" />
          </Card.Content>
        </Card>
      </Cell>
    </Layout>
  </Cell>
  <Cell span={12}>
    <Text secondary weight="normal">
      With stretchVertically
    </Text>
  </Cell>
  <Cell span={12}>
    <Layout cols={12}>
      <Cell span={4}>
        <Card stretchVertically>
          <Card.Content>
            <StorybookComponents.Placeholder height="180px" />
          </Card.Content>
        </Card>
      </Cell>
      <Cell span={4}>
        <Card stretchVertically>
          <Card.Content>
            <StorybookComponents.Placeholder height="120px" />
          </Card.Content>
        </Card>
      </Cell>
      <Cell span={4}>
        <Card stretchVertically>
          <Card.Content>
            <StorybookComponents.Placeholder height="60px" />
          </Card.Content>
        </Card>
      </Cell>
    </Layout>
  </Cell>
</Layout>;
```

### Show shadow
- description: <p>To highlight a card with no header or subheader, use the <code>showShadow</code> prop. This is most commonly used in widgets.</p>
- example: 
```jsx 
<Card showShadow>
  <Card.Content>
    <Box height="180px" />
  </Card.Content>
</Card>;
```




    


## Common Use Case Examples


### Form layouts
- description: <p>Use a card to group related form elements into a single layout.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Online Store' },
    { id: 1, value: 'Other' },
  ];
  return (
    <Card>
      <Card.Header
        title="Profile"
        subtitle="Your profile shows on search results, invoices, chat and more."
      />
      <Card.Divider />
      <Card.Content>
        <Box direction="vertical" gap="4">
          <Layout>
            <Cell span={6}>
              <FormField labelSize="small" label="Business name">
                <Input placeholder="" />
              </FormField>
            </Cell>
            <Cell span={6}>
              <FormField
                labelSize="small"
                label="Which category best matches your business?"
              >
                <Dropdown
                  size="medium"
                  placeholder="Category"
                  options={options}
                  selectedId={0}
                />
              </FormField>
            </Cell>
          </Layout>
          <Layout>
            <Cell span={6}>
              <Box direction="horizontal" gap="3" verticalAlign="middle">
                <FormField labelSize="small" label="Logo">
                  <AddItem theme="image" tooltipContent="Add Logo">
                    Add Item
                  </AddItem>
                </FormField>
                <Box direction="vertical" gap="1">
                  <Text size="small" secondary>
                    For best results, upload a high resolution image.
                  </Text>
                  <TextButton size="small">Add Logo</TextButton>
                </Box>
              </Box>
            </Cell>
            <Cell span={6}>
              <FormField labelSize="small" label="Short description">
                <InputArea
                  placeholder="Add more details about your business."
                  rows={3}
                  hasCounter
                  resizable
                />
              </FormField>
            </Cell>
          </Layout>
        </Box>
      </Card.Content>
    </Card>
  );
};
```

### Collapsable cards
- description: <p>Collapse and expand card content with the collapse mechanism.</p><p></p><p>The <code><ToggleSwitch/></code>, <code><IconButton/></code> and <code><TextButton/></code> components can trigger collapse and expand actions.</p>
- example: 
```jsx 
() => {
  const [open, setOpen] = React.useState(true);
  const [radio, setRadio] = React.useState(1);
  return (
    <Card>
      <Card.Header
        title="Set post limits"
        subtitle="You can limit the number of posts members can create in their first week."
        suffix={
          <ToggleSwitch
            onChange={() => setOpen(!open)}
            size="medium"
            checked={open}
          />
        }
      />
      <Collapse open={open}>
        <Card.Divider />
        <Card.Content>
          <RadioGroup value={radio} onChange={setRadio}>
            <RadioGroup.Radio value={1}>20</RadioGroup.Radio>
            <RadioGroup.Radio value={2}>15</RadioGroup.Radio>
            <RadioGroup.Radio value={3}>10</RadioGroup.Radio>
          </RadioGroup>
        </Card.Content>
      </Collapse>
    </Card>
  );
};
```

### Widgets
- description: <p>Cards can be used as widgets within grids or custom layouts. To highlight one card, use the <code>showShadow</code> property.</p><p></p><p>These cards usually don't include headers or section headers. </p>
- example: 
```jsx 
() => {
  const CustomCard = ({ title, suggested = false }) => {
    const [hovered, setHovered] = React.useState(false);
    return (
      <div
        onMouseEnter={() => setHovered(true)}
        onMouseLeave={() => setHovered(false)}
      >
        <Card showShadow={hovered}>
          <Layout gap={0}>
            <Cell span={12}>
              <Box height="18px" marginTop={2} marginLeft={-1}>
                {suggested && (
                  <Badge size="small" skin="standard">
                    SUGGESTED FOR YOU
                  </Badge>
                )}
              </Box>
            </Cell>
            <Cell>
              <Box height="72px" padding="12px 24px 0 24px">
                <Heading size="small">{title}</Heading>
              </Box>
            </Cell>
            <Cell>
              <Box padding="24px">
                <Button priority="secondary" size="small">
                  Set Up Automation
                </Button>
              </Box>
            </Cell>
          </Layout>
        </Card>
      </div>
    );
  };
  return (
    <Layout>
      <Cell span={4}>
        <CustomCard
          suggested
          title="Email customers when a product is back in stock "
        />
      </Cell>
      <Cell span={4}>
        <CustomCard title="Send a coupon to visitors who abandon a cart" />
      </Cell>
      <Cell span={4}>
        <CustomCard title="Ask customers for feedback via email" />
      </Cell>
    </Layout>
  );
};
```

### Marketing layouts
- description: <p><code><MarketingLayout/></code> should always be wrapped inside a card. </p>
- example: 
```jsx 

<Card>
  <MarketingLayout
    title="Get found on Google"
    description="Boost your site's SEO with the SEO Wiz. Follow your step-by-step plan."
    actions={<Button size="small">Start Now</Button>}
    size="tiny"
    badge={<Badge size="small">Essential</Badge>}
    image={
      <Box width="100%" align="right">
        <Image
          width="120px"
          src="PromotionalPromoteMarketingHomeSEO.svg"
          transparent
        />
      </Box>
    }
  />
</Card>;

```

### Empty states
- description: <p>If there's no content to display, add an <code><EmptyState/></code> component to guide users forward.</p>
- example: 
```jsx 
<Card>
  <Card.Header
    title="New Arrivals collection"
    suffix={
      <Button size="small" prefixIcon={<Icons.Add />}>
        Add Product
      </Button>
    }
  />
  <Card.Divider />
  <Card.Content>
    <EmptyState
      title="Add your first product"
      subtitle="Bring more attention to new products."
      theme="section"
    >
      <TextButton size="small" prefixIcon={<Icons.Add />}>
        Add Product
      </TextButton>
    </EmptyState>
  </Card.Content>
</Card>;
```


