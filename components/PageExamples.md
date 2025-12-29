
## Feature Examples


### Structure
- description: <p>This component consists of <code><Page.Header/></code> and <code><Page.Content/></code> areas. Both are mandatory in the Business Manager page layout.</p>
- example: 
```jsx 
<Page>
  <Page.Header title="Page Title" />
  <Page.Content>
    <StorybookComponents.Placeholder>
      Page content
    </StorybookComponents.Placeholder>
  </Page.Content>
</Page>;
```

### Height
- description: <p>Set page height using viewport height unit (<code>vh</code>). By default, page height should equal <code>100vh</code> (full screen size). If the page has a Business Manager top bar navigation, set the page height to <code>calc(100vh-48px).</code></p>
- example: 
```jsx 
<Page height="50vh">
  <Page.Header title="Page Title" />
  <Page.Content>
    <StorybookComponents.Placeholder>
      Page content
    </StorybookComponents.Placeholder>
  </Page.Content>
</Page>;
```

### Width
- description: <p>Add constraints to content width with the following props:</p><li> <code>minWidth</code> specifies the minimum content width.</li><li> <code>maxWidth</code> specifies the maximum content width. When the limit is reached, the side margins stretch and the content aligns to the center of the page.</li><p></p><p>By default, the page minimum width is 864px and the maximum width is 1248px (plus 48px padding on the sides). These values should be used across all Business Manager pages but can be changed for other use cases.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Page minWidth={864} maxWidth={1248}>
    <Page.Header
      title="Maximum width"
      subtitle="The maximum width for Business Manager Apps is 1248 pixels."
    />
    <Page.Content>
      <StorybookComponents.Placeholder height="180px" />
    </Page.Content>
  </Page>
  <Page minWidth={864} maxWidth={864}>
    <Page.Header
      title="Minimum width"
      subtitle="Minimum width for Business Manager Apps  is 864 pixels"
    />
    <Page.Content>
      <StorybookComponents.Placeholder height="180px" />
    </Page.Content>
  </Page>
</StorybookComponents.Stack>;
```

### Side padding
- description: <p>Control left and right content padding with the <code>sidePadding</code> prop. The default value is 48px and should be used across all Business Manager pages. The default padding can be changed for other use cases.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Page sidePadding={48}>
    <Page.Header
      title="Default padding"
      subtitle="The side padding for Business Manager Apps is 48 pixels."
    />
    <Page.Content>
      <StorybookComponents.Placeholder height="180px" />
    </Page.Content>
  </Page>
  <Page sidePadding={240}>
    <Page.Header title="Custom padding" />
    <Page.Content>
      <StorybookComponents.Placeholder height="180px" />
    </Page.Content>
  </Page>
</StorybookComponents.Stack>;
```

### Background image
- description: <p>Add a background image to the page header with <code>backgroundImageUrl</code> prop. Use it to showcase things like services, products or other items you want to feature.</p>
- example: 
```jsx 

<Page backgroundImageUrl="TravelExample1.jpg">
  <Page.Header title="Page with a background image" />
  <Page.Content>
    <Card>
      <Card.Content>
        <StorybookComponents.Placeholder height="180px" />
      </Card.Content>
    </Card>
  </Page.Content>
</Page>;

```

### Sticky header
- description: <p>The <code><Page.Header/></code> sticks to the top of the page and minimizes when visitors scroll down. This default behavior can't be changed.</p>
- example: 
```jsx 
<Page height='40vh'>
  <Page.Header title="Scroll to minimize page header" />
  <Page.Content>
    <StorybookComponents.Placeholder height="600px" />
  </Page.Content>
</Page>;
```

### Horizontal scroll
- description: <p>Enable horizontal scroll with the <code>horizontalScroll</code> prop. </p><p></p><p>When visitors scroll, the <code><Page.Header/></code> stays fixed. Use it when the width of content exceeds the maximum page width. For example, when displaying wide tables or lists.</p>
- example: 
```jsx 

<Page height="40vh" horizontalScroll>
  <Page.Header
    title="Scroll horizontally to view overflow content"
    actionsBar={<Button>Action</Button>}
  />
  <Page.Content>
    <StorybookComponents.Placeholder width="1800px" height="248px">
      Overflow content
    </StorybookComponents.Placeholder>
  </Page.Content>
</Page>;

```

### Header tail
- description: <p>Pin content below the header by wrapping it into a <code><Page.Tail/></code> container. Use it for content that needs to be visible at all times, for example a table header in an infinite scroll table.</p>
- example: 
```jsx 
<Page height="40vh">
  <Page.Header title="Scroll to view how the tail sticks" />
  <Page.Tail>
    <StorybookComponents.Placeholder>Tail that sticks to page header on scroll</StorybookComponents.Placeholder>
  </Page.Tail>
  <Page.Content>
    <StorybookComponents.Placeholder height="1800px" />
  </Page.Content>
</Page>;
```

### Sticky areas
- description: <p>Wrap page sections into <code><Page.Sticky/></code> containers to keep a section fixed in position while visitors scroll.</p>
- example: 
```jsx 
<Page height="40vh">
  <Page.Header title="Scroll down to preview sticky area behavior" />
  <Page.Content>
    <Layout>
      <Cell span={8}>
        <StorybookComponents.Placeholder height="3600px" />
      </Cell>
      <Cell span={4}>
        <Page.Sticky>
          <StorybookComponents.Placeholder height="240px">
            Sticky area
          </StorybookComponents.Placeholder>
        </Page.Sticky>
      </Cell>
    </Layout>
  </Page.Content>
</Page>;
```

### Anchor links
- description: <p>Create anchor links that direct visitors to a place inside the page using references (<code>ref</code>) and <code>onClick</code> events. </p>
- example: 
```jsx 
() => {
  const ref = React.createRef(null);
  const [downDisabled, setDownDisabled] = React.useState(false);
  const [upDisabled, setUpDisabled] = React.useState(true);

  const onClick = top => ref.current.scrollTo({ top, behavior: 'smooth' });
  const onScroll = props => {
    if (props.area.y === 'top') {
      return setDownDisabled(false) & setUpDisabled(true);
    }
    if (props.area.y === 'bottom') {
      return setDownDisabled(true) & setUpDisabled(false);
    }
  };

  return (
    <Page
      ref={ref}
      height="50vh"
      scrollProps={{ onScrollAreaChanged: onScroll }}
    >
      <Page.Header
        title="Page with anchor links"
        actionsBar={
          <Button onClick={() => onClick(10000)} disabled={downDisabled}>
            Click to Scroll Down
          </Button>
        }
      />
      <Page.Content>
        <StorybookComponents.Placeholder height="10000px" />
      </Page.Content>
      <Page.FixedFooter>
        <Page.Footer divider>
          <Page.Footer.End>
            <Button
              size="medium"
              onClick={() => onClick(0)}
              disabled={upDisabled}
            >
              Click to Scroll Up
            </Button>
          </Page.Footer.End>
        </Page.Footer>
      </Page.FixedFooter>
    </Page>
  );
};
```




    


## Common Use Case Examples


### Empty state
- description: <p>When there's no data to display on a page, use an <code><EmptyState/></code> with a clear call to action that tells visitors what they should do next.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="Categories"
    subtitle="Create and manage categories for your events."
    actionsBar={<Button prefixIcon={<Icons.Add />}>Add Category</Button>}
  />
  <Page.Content>
    <EmptyState
      image={<Image width="120px" src="no_categories.png" transparent />}
      title="Add your first category"
      subtitle="Organize your events with categories. You can connect any event with up to 10 categories."
      theme="page"
    >
      <TextButton prefixIcon={<Icons.Add />}>Add Category</TextButton>
    </EmptyState>
  </Page.Content>
</Page>;
```

### Tabs
- description: <p><code><Tabs/></code> can be used to show more content with the same hierarchy level on the same page. Use <code><Page.Tail/></code> to fix tabs below the page header so visitors can navigate between content.</p>
- example: 
```jsx 
() => {
  const [activeTabId, setActiveTabId] = React.useState(1);

  return (
    <Page height="60vh">
      <Page.Header
        title="Pricing Plans"
        subtitle="Set up subscriptions, memberships or package plans to sell on your site."
      />
      <Page.Tail>
        <Tabs
          items={[
            { id: 1, title: 'Active plans' },
            { id: 2, title: 'Archived plans' },
          ]}
          type="compactSide"
          activeId={activeTabId}
          onClick={tab => setActiveTabId(tab.id)}
        />
      </Page.Tail>
      <Page.Content>
        <Layout>
          {new Array(8).fill().map(() => (
            <Cell span={6}>
              <Card>
                <Box height="180px" />
              </Card>
            </Cell>
          ))}
        </Layout>
      </Page.Content>
    </Page>
  );
};
```

### Form layout: full width
- description: <p>Make sure the form page has "Save" and "Cancel" both at the top and the bottom of the page. Use <code><Page.Footer/></code> container to store actions at the end of a form.</p>
- example: 
```jsx 
<Page height="60vh">
  <Page.Header
    title="Basic Info"
    actionsBar={
      <Box gap="SP2">
        <Button skin="inverted">Cancel</Button>
        <Button>Save</Button>
      </Box>
    }
    breadcrumbs={
      <Breadcrumbs
        activeId="3"
        items={[
          { id: '1', value: 'Programs' },
          { id: '2', value: 'Healthy Diet' },
          { id: '3', value: 'Basic Info' },
        ]}
      />
    }
    showBackButton
    onBackClicked={() => {}}
  />
  <Page.Content>
    <Layout>
      <Cell>
        <Card>
          <Card.Header title="Program details" />
          <Card.Divider />
          <Card.Content>
            <Box height="420px" />
          </Card.Content>
        </Card>
      </Cell>
      <Cell>
        <Page.Footer divider>
          <Page.Footer.End>
            <Box gap="SP2">
              <Button priority="secondary">Cancel</Button>
              <Button>Save</Button>
            </Box>
          </Page.Footer.End>
        </Page.Footer>
      </Cell>
    </Layout>
  </Page.Content>
</Page>;
```

### Form layout: two-thirds
- description: <p>For form page layouts, use an 8 column layout and keep 4 columns blank. This makes it easier to scan. </p>
- example: 
```jsx 
() => {
  const renderCard = ({ title, subtitle }) => (
    <Card>
      <Card.Header title={title} subtitle={subtitle} />
      <Card.Divider />
      <Card.Content>
        <Box height="360px" />
      </Card.Content>
    </Card>
  );

  return (
    <Page height="60vh">
      <Page.Header
        actionsBar={
          <Box gap="SP2">
            <Button skin="inverted">Cancel</Button>
            <Button>Save</Button>
          </Box>
        }
        breadcrumbs={
          <Breadcrumbs
            activeId="2"
            items={[
              { id: '1', value: 'Settings' },
              { id: '2', value: 'eCommerce Settings' },
            ]}
            onClick={() => {}}
          />
        }
        showBackButton
        onBackClicked={() => {}}
        title="eCommerce Settings"
      />

      <Page.Content>
        <Layout>
          <Cell span={8}>
            {renderCard({
              title: 'Orders',
            })}
          </Cell>
          <Cell span={8}>
            {renderCard({
              title: 'Checkout',
              subtitle: 'Add the checkout fields you need customers to fill out.',
            })}
          </Cell>
          <Cell span={8}>
            {renderCard({
              title: 'Returns',
              subtitle:
                'Include more info about your return policy.',
            })}
          </Cell>
          <Cell>
            <Page.Footer divider>
              <Page.Footer.End>
                <Box gap="SP2">
                  <Button priority="secondary">Cancel</Button>
                  <Button>Save</Button>
                </Box>
              </Page.Footer.End>
            </Page.Footer>
          </Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};
```

### Form layout: two-thirds with a sidebar column
- description: <p>Use a <code><Layout/></code> grid to construct a ⅔ form layout that exposes primary and secondary content at the same time. To fix the sidebar's position while scrolling through the main page content, use <code><Page.Sticky/></code>.</p>
- example: 
```jsx 
() => {
  const renderCard = ({ title, subtitle, height = '300px' }) => (
    <Card>
      <Card.Header title={title} subtitle={subtitle} />
      <Card.Divider />
      <Card.Content>
        <Box height={height} />
      </Card.Content>
    </Card>
  );

  return (
    <Page height="60vh">
      <Page.Header
        actionsBar={
          <Box gap="SP2">
            <Button skin="inverted">Cancel</Button>
            <Button>Save</Button>
          </Box>
        }
        breadcrumbs={
          <Breadcrumbs
            activeId="2"
            items={[
              { id: '1', value: 'Pricing Plans' },
              { id: '2', value: 'Basic Plan' },
            ]}
            onClick={() => {}}
          />
        }
        showBackButton
        onBackClicked={() => {}}
        title="Basic Plan"
      />
      <Page.Content>
        <Layout>
          <Cell span={8}>
            <Layout>
              <Cell>
                {renderCard({
                  title: 'Plan info',
                  subtitle:
                    'Give your plan a name and sum it up with a tagline.',
                })}
              </Cell>
              <Cell>
                {renderCard({
                  title: 'Connect and manage benefits',
                  subtitle: 'Set up how benefits work in this plan.',
                })}
              </Cell>
              <Cell>
                {renderCard({
                  title: 'Pricing',
                  subtitle: 'How much do you want to charge?',
                })}
              </Cell>
              <Cell>
                {renderCard({
                  title: 'Page permissions',
                  subtitle: 'Manage pages members can access.',
                })}
              </Cell>
              <Cell>
                {renderCard({
                  title: 'Advanced settings',
                })}
              </Cell>
            </Layout>
          </Cell>
          <Cell span={4}>
            <Page.Sticky>
              {renderCard({
                title: 'Plan preview',
                subtitle: 'Preview how your plan appears online.',
                height: '360px',
              })}
            </Page.Sticky>
          </Cell>
          <Cell>
            <Page.Footer divider>
              <Page.Footer.End>
                <Box gap="SP2">
                  <Button priority="secondary">Cancel</Button>
                  <Button>Save</Button>
                </Box>
              </Page.Footer.End>
            </Page.Footer>
          </Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};
```

### Table
- description: <p>Use <code><Page.Sticky/></code> to fix the position of the content to a specific part of the page. For example, fixing the column titles of a table so visitors can sort and filter easily.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: 'Light grey hoodie',
      sku: 25232564,
      inStock: true,
      price: '$14.00',
      image: <Image src="ProductExample1.jpg" />,
    },
    {
      name: 'Black watch',
      sku: 35246432,
      inStock: true,
      price: '$29.00',
      image: <Image src="ProductExample2.jpg" />,
    },
    {
      name: 'Reading glasses',
      sku: 4864310,
      inStock: false,
      price: '$69.00',
      image: <Image src="ProductExample3.jpg" />,
    },
    {
      name: 'Leather shoes',
      sku: 125156422,
      inStock: true,
      price: '$7.00',
      image: <Image src="ProductExample4.jpg" />,
    },
    {
      name: 'Light grey hoodie',
      sku: 25232564,
      inStock: true,
      price: '$14.00',
      image: <Image src="ProductExample1.jpg" />,
    },
    {
      name: 'Black watch',
      sku: 35246432,
      inStock: true,
      price: '$29.00',
      image: <Image src="ProductExample2.jpg" />,
    },
    {
      name: 'Reading glasses',
      sku: 4864310,
      inStock: false,
      price: '$69.00',
      image: <Image src="ProductExample3.jpg" />,
    },
    {
      name: 'Leather shoes',
      sku: 125156422,
      inStock: true,
      price: '$7.00',
      image: <Image src="ProductExample4.jpg" />,
    },
  ];

  const Status = ({ isInStock }) => (
    <Text size="small" secondary>
      {isInStock ? 'In stock' : 'Out of stock'}
    </Text>
  );

  const secondaryAction = [
    {
      icon: <Icons.Duplicate />,
      text: 'Duplicate',
      onClick: () => {},
    },
    {
      icon: <Icons.Delete />,
      text: 'Delete',
      onClick: () => {},
    },
  ];

  const columns = [
    {
      title: '',
      render: row => row.image,
      width: '60px',
    },
    {
      title: 'Name',
      render: row => row.name,
      width: '30%',
    },
    {
      title: 'SKU',
      render: row => row.sku,
      width: '20%',
      align: 'start',
    },
    {
      title: 'Stock',
      render: row => <Status isInStock={row.inStock} />,
      width: '20%',
      align: 'start',
    },
    {
      title: 'Price',
      render: row => row.price,
      width: '10%',
      align: 'start',
    },
    {
      title: '',
      render: row => <TableActionCell secondaryActions={secondaryAction} />,
      width: '10%',
    },
  ];

  return (
    <Page height="60vh">
      <Page.Header
        title="Products"
        actionsBar={<Button prefixIcon={<Icons.Add />}>Add Product</Button>}
      />
      <Page.Content>
        <Layout>
          <Cell>
            <Card>
              <Table data={records} columns={columns}>
                <Page.Sticky>
                  <Card>
                    <TableToolbar>
                      <TableToolbar.ItemGroup position="start">
                        <TableToolbar.Item>
                          <TableToolbar.Title>Products</TableToolbar.Title>
                        </TableToolbar.Item>
                      </TableToolbar.ItemGroup>
                    </TableToolbar>
                    <Table.Titlebar />
                  </Card>
                </Page.Sticky>
                <Table.Content titleBarVisible={false} />
              </Table>
            </Card>
          </Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};
```

### 2 column list
- description: <p>Use a 2-column page layout to list features, tools or products. This layout works well for items that have relatively long titles and descriptions.</p>
- example: 
```jsx 
() => {
  return (
    <Page height="60vh">
      <Page.Header
        title="SEO Tools"
        subtitle="Optimize your site for search engines so more people can find you online."
        actionsBar={
          <Button skin="inverted" prefixIcon={<Icons.Users />}>
            Hire an SEO Professional
          </Button>
        }
      />
      <Page.Content>
        <Layout>
          <Cell span={6} rows={2}>
            <Card stretchVertically>
              <Card.Content>
                <Box direction="vertical">
                  <Image height="60px" width="60px" />
                </Box>
              </Card.Content>
            </Card>
          </Cell>
          {new Array(8).fill().map(() => (
            <Cell span={6}>
              <Card>
                <Card.Content>
                  <Box verticalAlign="middle" gap="SP3">
                    <Image height="60px" width="60px" />
                  </Box>
                </Card.Content>
              </Card>
            </Cell>
          ))}
        </Layout>
      </Page.Content>
    </Page>
  );
};
```

### 4 column list
- description: <p>Use a grid page layout with 4 columns to display visual items like, menus, categories, collections and photo albums.</p>
- example: 
```jsx 
() => {
  const renderProductItem = ({ image, title }) => (
    <Proportion aspectRatio={1}>
      <MediaOverlay skin="gradient" media={image}>
        <MediaOverlay.Content placement="bottom-start" visible="always">
          <Text weight="normal" light>
            {title}
          </Text>
        </MediaOverlay.Content>
      </MediaOverlay>
    </Proportion>
  );

  return (
    <Page height="60vh">
      <Page.Header
        title="Collections"
        actionsBar={<Button prefixIcon={<Icons.Add />}>Add Collection</Button>}
      />
      <Page.Content>
        <Layout>
          <Cell>
            <Box gap="SP4">
              {renderProductItem({
                image: 'ProductExample1.jpg',
                title: 'Hoodies',
              })}
              {renderProductItem({
                image: 'ProductExample2.jpg',
                title: 'Jewelery and watches',
              })}
              {renderProductItem({
                image: 'ProductExample3.jpg',
                title: 'Accessories',
              })}
              {renderProductItem({
                image: 'ProductExample4.jpg',
                title: 'Shoes',
              })}
            </Box>
          </Cell>
          <Cell>
            <Box gap="SP4">
              {renderProductItem({
                image: 'ProductExample5.jpg',
                title: 'Flowers and plants',
              })}
              {renderProductItem({
                image: 'ProductExample6.jpg',
                title: 'Home',
              })}
              {renderProductItem({
                image: 'ProductExample7.jpg',
                title: 'Winter collection',
              })}
              {renderProductItem({
                image: 'ProductExample8.jpg',
                title: 'Fragrance',
              })}
            </Box>
          </Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
}; 
```

### Dashboard
- description: <p>Use a combination of different grids within the same page. This is a great way to display different types of content on one page. Use <code><Page.Section/></code> to divide content into groups.</p>
- example: 
```jsx 
() => {
  const renderCard = ({ title, height, stretchVertically = false }) => (
    <Card stretchVertically={stretchVertically}>
      <Card.Header title={title} />
      <Card.Divider />
      <Card.Content>
        <Box height={height} />
      </Card.Content>
    </Card>
  );

  const renderToolsCard = () => (
    <Card>
      <Card.Content>
        <Box height="90px" />
      </Card.Content>
    </Card>
  );

  return (
    <Page height="60vh">
      <Page.Header
        title="Facebook Ads"
        actionsBar={
          <PopoverMenu
            triggerElement={
              <Button skin="inverted" suffixIcon={<Icons.ChevronDown />}>
                More Actions
              </Button>
            }
          >
            <PopoverMenu.MenuItem
              text="Edit campaign"
              prefixIcon={<Icons.Edit />}
            />
            <PopoverMenu.MenuItem
              text="Change budget"
              prefixIcon={<Icons.Payment />}
            />
            <PopoverMenu.MenuItem
              text="End campaign"
              prefixIcon={<Icons.Dismiss />}
              skin="destructive"
            />
          </PopoverMenu>
        }
      />
      <Page.Content>
        <Layout>
          <Cell>
            <Card>
              <Box height="120px" />
            </Card>
          </Cell>
          <Cell>
            <Page.Section
              title="Overview"
              showDivider
              actionsBar={
                <Box gap="SP2">
                  <Text>Time Period:</Text>
                  <DropdownBase
                    selectedId={4}
                    options={[
                      { id: 0, value: 'Last hour' },
                      { id: 1, value: 'Last 24 hours' },
                      { id: 2, value: 'Last 7 days' },
                      { id: 3, value: 'Last 30 days' },
                      { id: 4, value: 'Lifetime' },
                    ]}
                  >
                    {({ toggle, selectedOption = {} }) => (
                      <TextButton
                        onClick={toggle}
                        suffixIcon={<Icons.ChevronDown />}
                      >
                        {selectedOption.value}
                      </TextButton>
                    )}
                  </DropdownBase>
                </Box>
              }
            />
          </Cell>
          <Cell span={6}>
            {renderCard({
              title: 'Ad engagement',
              height: '240px',
              stretchVertically: true,
            })}
          </Cell>
          <Cell span={6}>
            {renderCard({
              title: 'Ad impact',
              height: '240px',
            })}
          </Cell>
          <Cell>
            {renderCard({
              title: 'Statistics',
              height: '180px',
            })}
          </Cell>
          <Cell span={4}>
            {renderCard({
              title: 'Audience',
              height: '240px',
            })}
          </Cell>
          <Cell span={4}>
            {renderCard({
              title: 'Performance over time',
              height: '240px',
            })}
          </Cell>
          <Cell span={4}>
            {renderCard({
              title: 'Customer funnel',
              height: '240px',
            })}
          </Cell>
          <Cell>
            <Page.Section
              title="Tools"
              showDivider
              actionsBar={
                <TextButton suffixIcon={<Icons.ChevronRight />}>
                  View All
                </TextButton>
              }
            />
          </Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
          <Cell span={3}>{renderToolsCard()}</Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};
```


