
## Feature Examples


### Structure
- description: <p>This component consists of <code>title</code>, <code>description</code>, <code>actions</code> and <code>image</code> container areas. </p><li>These areas accept any component as a child element.</li><li>Each area is optional, so the component can be customized according to your needs.</li><p></p><p>Marketing layout should be wrapped inside a <code><Card/></code>, which provides a white background.</p>
- example: 
```jsx 
<MarketingLayout
  title="Title"
  description="Description"
  actions={<Button size="small">Button</Button>}
  image={<Image width="180px" height="120px" />}
/>;
```

### Size
- description: <p>Adjust the component's size using the <code>size</code> property. It supports three values:</p><li><code>tiny</code> is used for promoting optional or ancillary features, or when multiple layouts are displayed in the same row.</li><li><code>small</code> is the default, and is used in all common cases.</li><li><code>medium</code> is for promoting core or mandatory releases. Use it in spacious layouts only.</li>
- example: 
```jsx 
() => {
  const MarketingLayoutImage = ({ width, height, title }) => (
    <StorybookComponents.Stack width="100%" justifyContent="flex-end">
      <StorybookComponents.Placeholder width={width} height={height}>
        <StorybookComponents.Stack
          justifyContent="center"
          height="100%"
          alignItems="center"
        >
          <Heading>{title}</Heading>
        </StorybookComponents.Stack>
      </StorybookComponents.Placeholder>
    </StorybookComponents.Stack>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Card>
        <MarketingLayout
          size="tiny"
          title="Tiny"
          description="Description"
          actions={<Button size="small">Small Button</Button>}
          image={<MarketingLayoutImage width="96px" height="96px" title="S2" />}
        />
      </Card>
      <Card>
        <MarketingLayout
          size="small"
          title="Small"
          description="Description"
          actions={<Button size="small">Small Button</Button>}
          image={
            <MarketingLayoutImage width="180px" height="120px" title="M2" />
          }
        />
      </Card>
      <Card>
        <MarketingLayout
          size="medium"
          title="Medium"
          description="Description"
          actions={<Button>Medium Button</Button>}
          image={
            <MarketingLayoutImage width="240px" height="156px" title="L1" />
          }
        />
      </Card>
    </StorybookComponents.Stack>
  );
};
```

### Image position
- description: <p>Change the image's position from right to left with the <code>inverted</code>  property.</p>
- example: 
```jsx 
() => {
  const MarketingLayoutImage = () => (
    <StorybookComponents.Stack>
      <StorybookComponents.Placeholder>
        <StorybookComponents.Stack
          width="180px"
          height="120px"
          justifyContent="center"
          alignItems="center"
        >
          <Heading>M2</Heading>
        </StorybookComponents.Stack>
      </StorybookComponents.Placeholder>
    </StorybookComponents.Stack>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Card>
        <MarketingLayout
          title="Default layout"
          description="This layout has an image on the right side."
          actions={<Button size="small">Button</Button>}
          image={<MarketingLayoutImage />}
        />
      </Card>
      <Card>
        <MarketingLayout
          inverted
          title="Inverted layout"
          description="This layout has an image on the left side."
          actions={<Button size="small">Button</Button>}
          image={<MarketingLayoutImage />}
        />
      </Card>
    </StorybookComponents.Stack>
  );
};
```

### Image background color
- description: <p>Add a background color to an image with <code>imageBackgroundColor</code>.</p>
- example: 
```jsx 
<Card hideOverflow>
  <MarketingLayout
    title="Title"
    description="Description"
    actions={<Button size="small">Action</Button>}
    imageBackgroundColor="B40"
    image={
      <StorybookComponents.Stack>
        <StorybookComponents.Placeholder>
          <StorybookComponents.Stack
            width="180px"
            height="120px"
            justifyContent="center"
            alignItems="center"
          >
            <Heading>M2</Heading>
          </StorybookComponents.Stack>
        </StorybookComponents.Placeholder>
      </StorybookComponents.Stack>
    }
  />
</Card>;
```

### Badge
- description: <p>Emphasize new or top items with a customizable label in the top left corner using the <code>badge</code> property. </p><p></p><p>Note that adding a badge increases the marketing layout's height. To keep layouts that are displayed in a row aligned, you can use the <code>hiddenBadge</code> property to add extra height to other layouts.</p>
- example: 
```jsx 
() => {
  const MarketingLayoutImage = () => (
    <StorybookComponents.Stack>
      <StorybookComponents.Placeholder>
        <StorybookComponents.Stack
          width="180px"
          height="120px"
          justifyContent="center"
          alignItems="center"
        >
          <Heading>M2</Heading>
        </StorybookComponents.Stack>
      </StorybookComponents.Placeholder>
    </StorybookComponents.Stack>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Card>
        <MarketingLayout
          badge={<Badge size="small">badge</Badge>}
          title="With badge"
          description="Description"
          actions={<Button size="small">Action</Button>}
          image={<MarketingLayoutImage />}
        />
      </Card>
      <Card>
        <MarketingLayout
          hiddenBadge
          title="Hidden badge"
          description="Description"
          actions={<Button size="small">Action</Button>}
          image={<MarketingLayoutImage />}
        />
      </Card>
    </StorybookComponents.Stack>
  );
};
```

### Vertical alignment
- description: <p>Control how content is vertically aligned with the <code>alignItems</code> property. It supports two values:</p><li><code>center</code> (default) centers the content vertically.</li><li><code>stretch</code> vertically stretches content to match the height of the image.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Card>
    <MarketingLayout
      title="Centered"
      description="This layout  centers its content vertically to the image on the right"
      actions={<Button size="small">Action</Button>}
      image={<Image height="180px" />}
    />
  </Card>
  <Card>
    <MarketingLayout
      alignItems="stretch"
      title="Stretched"
      description="This layout  stretches its content to fill the container instead of the default centered alignment."
      actions={<Button size="small">Action</Button>}
      image={<Image height="180px" />}
    />
  </Card>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Multi-column layout
- description: Display multiple marketing layouts in the same row to promote multiple features at the same time.
- example: 
```jsx 
<Page>
  <Page.Content>
    <Layout>
      <Cell>
        <PageSection title="Suggested for you" showDivider />
      </Cell>
      <Cell span={6}>
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
        </Card>
      </Cell>
      <Cell span={6}>
        <Card>
          <MarketingLayout
            title="Create an email campaign"
            description="Send updates, offers or newsletters & keep in touch."
            actions={<Button size="small">Send Campaign</Button>}
            size="tiny"
            hiddenBadge
            alignItems="stretch"
            image={
              <Box width="100%" align="right">
                <Image
                  width="120px"
                  src="PromotionalPromoteMarketingHomeEmail.svg"
                  transparent
                />
              </Box>
            }
          />
        </Card>
      </Cell>
    </Layout>
  </Page.Content>
</Page>;
```

### Footnote
- description: <p>Append a footnote containing notes or conditions by adding a divider and a box to the same card the <code><MarketingLayout/></code> is wrapped in.</p>
- example: 
```jsx 
<Card>
  <MarketingLayout
    title="Add sessions to get booked"
    description="Set when this service is offered and which staff member will provide it."
    actions={
      <Box gap="6px">
        <Button size="small">Add Sessions</Button>
        <Button size="small" skin="inverted">
          Learn More
        </Button>
      </Box>
    }
    size="small"
    image={
      <Box width="100%" align="right">
        <Image width="120px" src="PromotionalBookingsUpgrade.svg" transparent />
      </Box>
    }
  />
  <Divider />
  <Box align="left" padding="12px 30px">
    <Text size="tiny" secondary>
      You can also add sessions directly from your <a>Calendar</a>.
    </Text>
  </Box>
</Card>;
```


