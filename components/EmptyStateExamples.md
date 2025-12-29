
## Feature Examples


### Structure
- description: <p>An empty state has 4 optional elements:</p><li><code>image</code></li><li><code>title</code></li><li><code>subtitle</code></li><li><code>child container,</code> which can hold any component but is primarily reserved for CTA buttons.</li><p></p>
- example: 
```jsx 
<EmptyState
  image={<Image width="120px" height="120px" />}
  title="Title"
  subtitle="Subtitle"
>
  <StorybookComponents.Placeholder>Child container</StorybookComponents.Placeholder>
</EmptyState>;
```

### Skin
- description: <p>Control an empty state's appearance with the <code>skin</code> property. There are 3 types:</p><li><code>page</code> is for full-page empty states where data is displayed in a full-width table or a card.</li><li><code>page-no-border</code> is for full-page empty states where data is displayed in an unknown layout.</li><li><code>section</code> is the default theme for layout elements such as cards, tables or modals.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="48px">
  <EmptyState
    image={<Image width="120px" height="120px" />}
    skin="page"
    title="Page theme"
    subtitle="A subtitle guides users to their next step."
  />
  <EmptyState
    image={<Image width="120px" height="120px" />}
    skin="page-no-border"
    title="Page-no-border theme"
    subtitle="A subtitle guides users to their next step."
  />
  <EmptyState
    image={<Image width="120px" height="120px" />}
    skin="section"
    title="Section theme"
    subtitle="A subtitle guides users to their next step."
  />
</StorybookComponents.Stack>;
```

### Children
- description: <p>Add 1 or more CTA buttons below the subtitle as child elements of the empty state.</p><p></p><p>Be sure to give the user clear next actions.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <EmptyState
    skin="page-no-border"
    title="Add your first product"
    subtitle="Start adding products so customers can shop your online store."
  >
    <StorybookComponents.Placeholder height="36px">
      Child elements
    </StorybookComponents.Placeholder>
  </EmptyState>
  <EmptyState
    skin="page-no-border"
    title="Add your first product"
    subtitle="Start adding products so customers can shop your online store."
  >
    <TextButton prefixIcon={<Icons.Add />}>Add Product</TextButton>
  </EmptyState>
  <EmptyState
    skin="page-no-border"
    title="Add your first product"
    subtitle="Start adding products so customers can shop your online store."
  >
    <StorybookComponents.Stack gap="16px">
      <TextButton prefixIcon={<Icons.Add />}>Add New Product</TextButton>
      <TextButton prefixIcon={<Icons.DownloadImport />}>
        Import Products
      </TextButton>
    </StorybookComponents.Stack>
  </EmptyState>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### No data on a page
- description: <p>Use the <code>page</code> or  <code>page-no-border</code> skin  to tell users what will appear on the page once there’s data to display, and if relevant, what they can do to get started.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="Tasks and Reminders"
    actionsBar={<Button prefixIcon={<Icons.Add />}>Add Task</Button>}
  />
  <Page.Content>
    <EmptyState
      skin="page"
      image={
        <Image
          width="120px"
          height="120px"
          src="no_categories.png"
          transparent
        />
      }
      title="Add your first task"
      subtitle="Manage tasks and reminders for your site to get more done."
    >
      {<TextButton prefixIcon={<Icons.Add />}>Add Task</TextButton>}
    </EmptyState>
  </Page.Content>
</Page>;
```

### No data in a card
- description: <p>Use the <code>section</code> skin empty state to tell users what will appear on the card once there’s data to display and, if relevant, what they can do to get started.</p><p></p><p>Keep the design minimal and avoid using illustrations.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="New Category"
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
          { id: '1', value: 'Categories' },
          { id: '2', value: 'New Category' },
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
          <Card.Header title="Category details" />
          <Card.Divider />
          <Card.Content>
            <Layout>
              <Cell span={4}>
                <FormField label="Category name" required>
                  <Input placeholder="e.g., Fitness Classes" />
                </FormField>
              </Cell>
            </Layout>
          </Card.Content>
        </Card>
      </Cell>
      <Cell>
        <Card>
          <Card.Header title="Services" />
          <Card.Divider />
          <Card.Content>
            <EmptyState
              title="Add services to this category"
              subtitle="Choose the services you want included in this category or create new ones."
            >
              <TextButton prefixIcon={<Icons.Add />}>Add Services</TextButton>
            </EmptyState>
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

### No search results
- description: <p>Use an empty state when a search doesn’t return any results. Explain what happened and what users can do next to adjust their search.</p>
- example: 
```jsx 
() => {
  const [searchTerm, setSearchTerm] = React.useState('');
  const [display, setDisplay] = React.useState('none');
  const [records, setRecords] = React.useState([
    {
      name: `Ballet shoes`,
      SKU: 'BP063001',
      price: '$78',
      inventory: 16,
    },
    {
      name: `Chelsea boots`,
      SKU: 'BP063001',
      price: '$112',
      inventory: 32,
    },
    {
      name: `Desert boots`,
      SKU: 'BP063001',
      price: '$89',
      inventory: 23,
    },
    {
      name: `Platform shoes`,
      SKU: 'BP063001',
      price: '$45',
      inventory: 102,
    },
    {
      name: `Espadrilles`,
      SKU: 'BP063001',
      price: '$96',
      inventory: 4,
    },
    {
      name: `Moccasins`,
      SKU: 'BP063001',
      price: '$104',
      inventory: 45,
    },
  ]);

  const columns = [
    {
      title: 'Name',
      render: row => row.name,
      width: '30%',
    },
    {
      title: 'SKU',
      render: row => row.SKU,
      width: '20%',
    },
    {
      title: 'Price',
      render: row => row.price,
      width: '20%',
    },
    {
      title: 'Inventory',
      render: row => row.inventory,
      width: '20%',
    },
  ];

  const clearSearch = () => {
    setSearchTerm('');
  };

  const renderSearch = expandable => {
    return (
      <Search
        size="small"
        expandable={expandable}
        placeholder="Search..."
        onChange={e => {
          setSearchTerm(e.target.value);
        }}
        value={searchTerm}
        onClear={clearSearch}
      />
    );
  };

  const getFilteredData = () => {
    let data = records;

    if (searchTerm !== '') {
      data = data.filter(row =>
        row.name.toUpperCase().includes(searchTerm.toUpperCase()),
      );
    }

    return data;
  };

  const filteredData = getFilteredData();

  const renderEmptyState = () => (
    <Table.EmptyState
      title="No results found"
      subtitle="No items matched your search. Try searching for something else."
      image={
        <Image
          width="120px"
          height="120px"
          transparent={true}
          src="EmptyState_Generic1.svg"
        />
      }
    >
      <TextButton onClick={clearSearch}>Clear Search</TextButton>
    </Table.EmptyState>
  );

  return (
    <Card>
      <Table data={filteredData} columns={columns} rowVerticalPadding="medium">
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <Text size="small" weight="normal">
                6 products
              </Text>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
          <TableToolbar.ItemGroup position="end">
            <TableToolbar.Item>{renderSearch(false)}</TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        {filteredData.length ? <Table.Titlebar /> : renderEmptyState()}
        <Table.Content titleBarVisible={false} />
      </Table>
    </Card>
  );
};
```

### Failed to load
- description: <p>Let users know that their data failed to load. If possible, provide a next action.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="Website Widgets"
    subtitle="Widgets let you add features and functionality to your site."
  />
  <Page.Content>
    <EmptyState
      skin="page-no-border"
      image={
        <Image width="120px" src="EmptyState_ServerError.svg" transparent />
      }
      title="We couldn't load this page"
      subtitle="Looks like there was a technical issue on our end. Wait a few minutes and try again."
    >
      <TextButton prefixIcon={<Icons.Refresh />}>Try Again</TextButton>
    </EmptyState>
  </Page.Content>
</Page>;
```

### App introduction
- description: <p>Use an empty state in the main tab of the app settings panel to give a brief introduction to the app. </p><p></p><p>Place the app icon and a short description at the top, and provide main actions to help users get started using the app.</p>
- example: 
```jsx 
<SidePanel skin="floating" width="420px" onCloseButtonClick onHelpButtonClick>
  <SidePanel.Header title="Blog" />
  <Box height="480px">
    <VerticalTabs size="small" activeTabId={0} onChange={() => {}}>
      <VerticalTabs.TabItem id={0}>Main</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={1}>Display</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={2}>Layout</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={3}>Design</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={4}>Support</VerticalTabs.TabItem>
    </VerticalTabs>
    <Divider direction="vertical" />
    <SidePanel.Content>
      <EmptyState
        theme="section"
        skin={
          <Image
            width="120px"
            height="120px"
            src="onboarding_community.svg"
            transparent
          />
        }
        title="Blog feed"
        subtitle="Customize the layout and design of your blog feed, or create a post."
      >
        <Box gap="SP2" direction="vertical">
          <Button size="small">Create Post</Button>
          <Button size="small" priority="secondary">
            Manage Posts
          </Button>
        </Box>
      </EmptyState>
    </SidePanel.Content>
  </Box>
</SidePanel>;
```


