
## Feature Examples


### Structure
- description: <p>Table structures can vary, but they can include up to four elements:</p><li><code><TableToolbar/></code> that displays table titles, filters and actions. </li><li><code><Table.SubToolbar/></code> that displays content related to toolbar actions (optional).</li><li><code><Table.Titlebar/></code> that displays titles in data columns (optional).</li><li><code><Table.Content/></code> that shows rows of data.</li>
- example: 
```jsx 
() => {
  const data = Array(5).fill({
    item: 'Data',
  });

  const columns = Array(1).fill({
    title: 'Titlebar',
    render: row => row.item,
  });

  return (
    <Card hideOverflow>
      <Table data={data} columns={columns}>
        <TableToolbar>
          <TableToolbar.Title>Toolbar</TableToolbar.Title>
        </TableToolbar>
        <Table.SubToolbar>
          <TableToolbar.Label>Subtoolbar</TableToolbar.Label>
        </Table.SubToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Skin
- description: <p>Choose between two colors for column title bars by using the <code>skin</code> prop. </p><li><code>standard</code> is used for common cases (default). </li><li><code>neutral</code> is used to minimize the emphasis on column titles. It's also common for tables that don't support sorting.</li>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];
  const columns = [
    {
      title: 'Name',
      render: row => row.name,
    },
    {
      title: 'SKU',
      render: row => row.SKU,
    },
    {
      title: 'Inventory',
      render: row => row.inventory,
    },
    {
      title: 'Price',
      render: row => row.price,
    },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Table skin="standard" data={records} columns={columns}>
        <Table.Content />
      </Table>
      <Table skin="neutral" data={records} columns={columns}>
        <Table.Content />
      </Table>
    </StorybookComponents.Stack>
  );
};
```

### Row vertical padding
- description: <p>Use <code>rowVerticalPadding</code> to control the whitespace above and below row data. Choose one of the following options: </p><li><code>xxTiny</code> - Adds 3px padding. Use it to create very compact tables that contain text only. </li><li><code>xTiny</code> - Adds 6px padding. Use it to create dense tables with short content.</li><li><code>tiny</code> - Adds 12px padding. Use it to create dense tables or for rows that contain media elements, such as images or avatars.</li><li><code>small</code> (default) - Adds 15px padding. Use this for common cases.</li><li><code>medium</code> - Adds 18px padding. Use this for short data lists.</li><li><code>large</code> - Adds 24px padding. Use sparingly for short data lists with a few items only.</li>
- example: 
```jsx 
() => {
  const generateRecords = (item) => [
    { item: item },
    { item: item },
    { item: item },
  ];
  const columns = [{ title: 'Vertical padding', render: (row) => row.item }];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Table
        rowVerticalPadding="xxTiny"
        data={generateRecords('xxTiny')}
        columns={columns}
      >
        <Table.Content />
      </Table>   
   <Table
        rowVerticalPadding="xTiny"
        data={generateRecords('xTiny')}
        columns={columns}
      >
        <Table.Content />
      </Table>
      <Table
        rowVerticalPadding="tiny"
        data={generateRecords('Tiny')}
        columns={columns}
      >
        <Table.Content />
      </Table>
      <Table
        rowVerticalPadding="small"
        data={generateRecords('Small (default)')}
        columns={columns}
      >
        <Table.Content />
      </Table>
      <Table
        rowVerticalPadding="medium"
        data={generateRecords('Medium')}
        columns={columns}
      >
        <Table.Content />
      </Table>
      <Table
        rowVerticalPadding="large"
        data={generateRecords('Large')}
        columns={columns}
      >
        <Table.Content />
      </Table>
    </StorybookComponents.Stack>
  );
};
```

### Width
- description: <p>Specify table width in pixels or percentage with the <code>width</code> property. If not set, table will have the same width as its parent container.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];
  const columns = [
    {
      title: 'Name',
      render: row => row.name,
    },
    {
      title: 'SKU',
      render: row => row.SKU,
    },
    {
      title: 'Inventory',
      render: row => row.inventory,
    },
    {
      title: 'Price',
      render: row => row.price,
    },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Table data={records} columns={columns} width="100%">
        <Table.Content />
      </Table>
      <Table data={records} columns={columns} width="80%">
        <Table.Content />
      </Table>
    </StorybookComponents.Stack>
  );
};
```

### Number of columns
- description: <p>Define data columns via the <code>columns</code> array.  Table can have any number of columns.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const twocolumns = [
    {
      title: 'Name',
      render: row => row.name,
    },
    {
      title: 'Price',
      render: row => row.price,
    },
  ];

  const fourcolumns = [
    {
      title: 'Name',
      render: row => row.name,
    },
    {
      title: 'SKU',
      render: row => row.SKU,
    },
    {
      title: 'Inventory',
      render: row => row.inventory,
    },
    {
      title: 'Price',
      render: row => row.price,
    },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Table data={records} columns={twocolumns}>
        <Table.Content />
      </Table>
      <Table data={records} columns={fourcolumns}>
        <Table.Content />
      </Table>
    </StorybookComponents.Stack>
  );
};
```

### Column alignment
- description: <p>Control content alignment in a column with the <code>align</code> prop. It supports 3 options:</p><li><code>start</code> (default)</li><li><code>center</code> </li><li><code>end</code> </li>
- example: 
```jsx 
() => {
  const data = [
    {
      column1: 'Start aligned column',
      column2: 'Center',
      column3: 'End',
    },
    {
      column1: 'Start',
      column2: 'Center aligned column',
      column3: 'End',
    },
    {
      column1: 'Start',
      column2: 'Center',
      column3: 'End aligned column',
    },
  ];

  const columns = [
    { title: 'Align', align: 'start', render: row => row.column1 },
    { title: 'Align', align: 'center', render: row => row.column2 },
    { title: 'Align', align: 'end', render: row => row.column3 },
  ];

  return (
    <Card>
      <Table data={data} columns={columns} rowVerticalPadding="medium">
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Column width
- description: <p>Specify width of each column with <code>width</code> prop. If not specified, columns will be sized equally.</p>
- example: 
```jsx 
() => {
  const data = [
    {
      column1: '60%',
      column2: '25%',
      column3: '15%',
    },
    {
      column1: '60%',
      column2: '25%',
      column3: '15%',
    },
    {
      column1: '60%',
      column2: '25%',
      column3: '15%',
    },
  ];

  const columns = [
    { title: 'Column width', width: '60%', render: row => row.column1 },
    { title: 'Column width', width: '25%', render: row => row.column2 },
    { title: 'Column width', width: '15%', render: row => row.column3 },
  ];

  return (
    <Card>
      <Table data={data} columns={columns} rowVerticalPadding="medium">
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Column info
- description: <p>Add a tooltip to give additional information about a specific column using <code>infoTooltipProps</code>. Style the tooltip message with all common <code><Tooltip/></code> properties.</p>
- example: 
```jsx 
() => {
  const data = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    {
      title: 'Name',
      infoTooltipProps: {
        content: 'Info explaining what this column data is about',
      },
      render: row => row.name,
    },
    {
      title: 'SKU',
      infoTooltipProps: {
        content: 'Info explaining what this column data is about',
      },
      render: row => row.SKU,
    },
    {
      title: 'Inventory',
      infoTooltipProps: {
        content: 'Info explaining what this column data is about',
      },
      render: row => row.inventory,
    },
    {
      title: 'Price',
      render: row => row.price,
    },
  ];

  return (
    <Table data={data} columns={columns} rowVerticalPadding="medium">
      <Table.Content />
    </Table>
  );
};
```

### Row content
- description: <p>Add any required content to the table cells. It accepts any component or a composition of multiple elements.</p>
- example: 
```jsx 
() => {
  const recordsExample1 = [
    {
      name: <StorybookComponents.Placeholder height="36px" />,
      SKU: <StorybookComponents.Placeholder height="36px" />,
      price: <StorybookComponents.Placeholder height="36px" />,
      inventory: <StorybookComponents.Placeholder height="36px" />,
    },
    {
      name: <StorybookComponents.Placeholder height="36px" />,
      SKU: <StorybookComponents.Placeholder height="36px" />,
      price: <StorybookComponents.Placeholder height="36px" />,
      inventory: <StorybookComponents.Placeholder height="36px" />,
    },
    {
      name: <StorybookComponents.Placeholder height="36px" />,
      SKU: <StorybookComponents.Placeholder height="36px" />,
      price: <StorybookComponents.Placeholder height="36px" />,
      inventory: <StorybookComponents.Placeholder height="36px" />,
    },
    {
      name: <StorybookComponents.Placeholder height="36px" />,
      SKU: <StorybookComponents.Placeholder height="36px" />,
      price: <StorybookComponents.Placeholder height="36px" />,
      inventory: <StorybookComponents.Placeholder height="36px" />,
    },
  ];

  const recordsExample2 = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const recordsExample3 = [
    {
      image: <Image src="ProductExample1.jpg" />,
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      visible: (
        <Box verticalAlign="middle" gap="SP2">
          <ToggleSwitch checked />
          <Text size="small" secondary>
            Visible
          </Text>
        </Box>
      ),
    },
    {
      image: <Image src="ProductExample2.jpg" />,
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      visible: (
        <Box verticalAlign="middle" gap="SP2">
          <ToggleSwitch checked />
          <Text size="small" secondary>
            Visible
          </Text>
        </Box>
      ),
    },
    {
      image: <Image src="ProductExample3.jpg" />,
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      visible: (
        <Box verticalAlign="middle" gap="SP2">
          <ToggleSwitch />
          <Text size="small" secondary>
            Hidden
          </Text>
        </Box>
      ),
    },
    {
      image: <Image src="ProductExample4.jpg" />,
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      visible: (
        <Box verticalAlign="middle" gap="SP2">
          <ToggleSwitch checked />
          <Text size="small" secondary>
            Visible
          </Text>
        </Box>
      ),
    },
  ];

  const recordsExample4 = [
    {
      role: (
        <Box direction="vertical" gap="3px">
          <Text weight="normal">Account owner</Text>
          <Text size="small" secondary>
            Has full administrative access to the account and can manage all
            sites.
          </Text>
        </Box>
      ),
      members: (
        <AvatarGroup type="condensed" items={[{ name: 'Matt Thompson' }]} />
      ),
    },
    {
      role: (
        <Box direction="vertical" gap="3px">
          <Text weight="normal">Site admin</Text>
          <Text size="small" secondary>
            Has full access to the site but cannot edit the payment info, delete
            or duplicate the site.
          </Text>
        </Box>
      ),
      members: (
        <AvatarGroup
          type="condensed"
          items={[{ name: 'Matt Thompson' }, { name: 'Luke Wheeler' }]}
        />
      ),
    },
    {
      role: (
        <Box direction="vertical" gap="3px">
          <Text weight="normal">Website manager</Text>
          <Text size="small" secondary>
            Can edit the site, manage settings and apps but cannot access Inbox,
            contacts and other sensitive info.
          </Text>
        </Box>
      ),
      members: (
        <AvatarGroup
          type="condensed"
          items={[
            { name: 'Matt Thompson' },
            { name: 'Emma Pike' },
            { name: 'Julia Maria Rogers' },
            { name: 'Margareth Simmons' },
          ]}
        />
      ),
    },
    {
      role: (
        <Box direction="vertical" gap="3px">
          <Text weight="normal">Back-office manager</Text>
          <Text size="small" secondary>
            Can access the Wix Dashboard to manage site settings and apps but
            cannot edit the site.
          </Text>
        </Box>
      ),
      members: <AvatarGroup type="condensed" items={[{ name: 'Emma Pike' }]} />,
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const columns2 = [
    { title: '', render: row => row.image, width: '60px' },
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Visibility', render: row => row.visible },
    { title: 'Price', render: row => row.price },
  ];

  const columns3 = [
    { title: 'Role', render: row => row.role, width: '65%' },
    { title: 'Members', render: row => row.members },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Table skin="standard" data={recordsExample1} columns={columns}>
        <Table.Content />
      </Table>
      <Table
        skin="standard"
        data={recordsExample2}
        columns={columns}
        rowVerticalPadding="medium"
      >
        <Table.Content />
      </Table>
      <Table skin="standard" data={recordsExample3} columns={columns2}>
        <Table.Content />
      </Table>
      <Table
        skin="standard"
        data={recordsExample4}
        columns={columns3}
        rowVerticalPadding="medium"
      >
        <Table.Content />
      </Table>
    </StorybookComponents.Stack>
  );
};
```

### Row highlight
- description: <p>Emphasize specific rows that require user attention by highlighting them. Define a condition which must be matched via <code>isRowHighlight</code> function.</p><p>Highlight affects row background color and a font weight. </p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
      highlight: true,
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
      highlight: true,
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
      highlight: false,
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
      highlight: false,
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  return (
    <Table
      isRowHighlight={rowData => rowData.highlight}
      data={records}
      columns={columns}
    >
      <Table.Content />
    </Table>
  );
};

```

### Sorting
- description: <p>Allow users to find relevant data quicker by enabling column sorting.</p><p>Specify which column is sortable in columns array using the <code>sortable</code> prop.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name, sortable: true },
    { title: 'SKU', render: row => row.SKU, sortable: true },
    {
      title: 'Inventory',
      render: row => row.inventory,
      sortable: true,
      sortDescending: false,
    },
    { title: 'Price', render: row => row.price, sortable: true },
  ];

  return (
    <Table data={records} columns={columns} rowVerticalPadding="medium">
      <Table.Content />
    </Table>
  );
};

```

### Expand rows
- description: <p>Reveal more details about each row by allowing rows to expand. Define whether a specific row can be expanded or not with the <code>expandable</code> prop in <code>data</code> array. </p><p>By default one row can be expanded at a time only. Allow users to expand multiple rows simultaneously with the <code>allowMultiDetailsExpansion</code> prop. </p><p>Use the <code>rowDetails</code> prop to pass content to display once row is expanded. Control whether content has paddings or not with the <code>removeRowDetailsPadding</code> prop. Remove paddings when you want to display another table inside row details.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: 'Light grey hoodie',
      expandable: true,
      expanded: true,
    },
    {
      name: 'Black watch',
      expandable: true,
      expanded: true,
    },
    {
      name: 'Reading glasses',
      expandable: true,
      expanded: true,
    },
    {
      name: 'Leather shoes',
      expandable: true,
      expanded: true,
    },
  ];

  const renderRowDetails = row => {
    if (row.expandable) {
      return <StorybookComponents.Placeholder height="120px" />;
    }
  };

  const columns = [
    { title: 'Name', render: row => row.name },
    {
      render: row =>
        row.expandable ? (
          <TableActionCell
            size="small"
            primaryAction={{
              text: !row.expanded ? 'Expand' : 'Collapse',
              onClick: (row.expanded = !row.expanded),
            }}
          />
        ) : (
          ''
        ),
    },
  ];

  return (
    <StorybookComponents.Stack>
      <Table
        rowDetails={row => renderRowDetails(row)}
        data={records}
        columns={columns}
      >
        <Table.Content />
      </Table>
      <Table
        rowDetails={row => renderRowDetails(row)}
        removeRowDetailsPadding={true}
        allowMultiDetailsExpansion={true}
        data={records}
        columns={columns}
      >
        <Table.Content />
      </Table>
    </StorybookComponents.Stack>
  );
};
```

### Column title visibility
- description: <p>Specify whether column titles are visible with the <code>titleBarDisplay</code> prop.</p><p>Hide the titlebar only when column values are self explanatory.</p><p><em>Note: </em>Column titles should be announced for assistive technology users even when titlebar is visually hidden.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Card hideOverflow>
        <Table data={records} columns={columns} rowVerticalPadding="medium">
          <TableToolbar>
            <TableToolbar.ItemGroup position="start">
              <TableToolbar.Item>
                <TableToolbar.Title>Products</TableToolbar.Title>
              </TableToolbar.Item>
            </TableToolbar.ItemGroup>
          </TableToolbar>
          <Table.Content titleBarVisible={true} />
        </Table>
      </Card>
      <Card hideOverflow>
        <Table data={records} columns={columns} rowVerticalPadding="medium">
          <TableToolbar>
            <TableToolbar.ItemGroup position="start">
              <TableToolbar.Item>
                <TableToolbar.Title>Products</TableToolbar.Title>
              </TableToolbar.Item>
            </TableToolbar.ItemGroup>
          </TableToolbar>
          <Table.Content titleBarVisible={false} />
        </Table>
      </Card>
    </StorybookComponents.Stack>
  );
};
```

### Horizontal scroll
- description: <p>Allow table content to exceed the width of a table itself by enabling <code>horizontalScroll</code>. Use it to support any number of data columns.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
      items: 24,
      collection: '2021 Winter',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
      items: 190,
      collection: '2021 Winter',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
      items: 12,
      collection: '2021 Winter',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
      items: 0,
      collection: '2021 Winter',
    },
  ];

  const columnWidth = 240;

  const primaryAction = { text: 'Edit', onClick: () => {} };

  const secondaryActions = [
    {
      icon: <Icons.FavoriteSmall />,
      text: 'Mark as favourite',
      onClick: () => {},
    },
  ];

  const columns = [
    {
      title: 'Name',
      render: row => row.name,
      width: columnWidth,
    },
    {
      title: 'SKU',
      render: row => row.SKU,
      width: columnWidth,
    },
    {
      title: 'Inventory',
      render: row => row.inventory,
      width: columnWidth,
    },
    {
      title: 'Items left',
      render: row => row.items,
      width: columnWidth,
    },
    {
      title: 'Collection',
      render: row => row.collection,
      width: columnWidth,
    },
    {
      title: 'Price',
      render: row => row.price,
      width: columnWidth,
    },
    {
      render: () => (
        <TableActionCell
          size="small"
          primaryAction={primaryAction}
          secondaryActions={secondaryActions}
          moreActionsTooltipText="More actions"
        />
      ),
      stickyActionCell: true,
      width: 30,
    },
  ];

  return (
    <Card hideOverflow>
      <Table
        horizontalScroll
        stickyColumns={1}
        data={records}
        columns={columns}
      >
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <Text size="small">4 products</Text>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Bulk actions
- description: <p>Allow users to act upon multiple items at once by enabling row selection with the <code>showSelection</code> prop.</p><p>Control ‘Select all’ checkbox visibility with the <code>hideBulkSelectionCheckbox</code> prop.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const MainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Label>4 products</TableToolbar.Label>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const ActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <TableToolbar.Label>{`${selectedCount} selected`}</TableToolbar.Label>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Card>
        <Table data={records} columns={columns} showSelection>
          <Table.ToolbarContainer>
            {selectionContext =>
              selectionContext.selectedCount === 0
                ? MainToolbar()
                : ActionsToolbar({ ...selectionContext })
            }
          </Table.ToolbarContainer>
          <Table.Content />
        </Table>
      </Card>
      <Card>
        <Table
          data={records}
          columns={columns}
          showSelection
          hideBulkSelectionCheckbox
        >
          <Table.ToolbarContainer>
            {selectionContext =>
              selectionContext.selectedCount === 0
                ? MainToolbar()
                : ActionsToolbar({ ...selectionContext })
            }
          </Table.ToolbarContainer>
          <Table.Content />
        </Table>
      </Card>
    </StorybookComponents.Stack>
  );
};
```

### Multiple bulk actions
- description: <p>Display available bulk actions in the toolbar with following components:</p><li> <code><Button/></code> for main actions </li><li> <code><PopoverMenu/></code> for secondary actions</li><p></p><p><em>Note:</em> There should be no more than 3 actions visible in the toolbar at once.</p><p></p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const MainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Label>4 products</TableToolbar.Label>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const ActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <TableToolbar.Label>{`${selectedCount} selected`}</TableToolbar.Label>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.DuplicateSmall />}
          >
            Duplicate
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <PopoverMenu
            textSize="small"
            triggerElement={
              <Button
                skin="inverted"
                size="small"
                suffixIcon={<Icons.ChevronDownSmall />}
              >
                More Actions
              </Button>
            }
          >
            <PopoverMenu.MenuItem
              text="Archive"
              prefixIcon={<Icons.ArchiveSmall />}
            />
            <PopoverMenu.MenuItem
              text="Delete"
              prefixIcon={<Icons.DeleteSmall />}
              skin="destructive"
            />
          </PopoverMenu>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <Card hideOverflow>
      <Table data={records} columns={columns} showSelection>
        <Table.ToolbarContainer>
          {selectionContext =>
            selectionContext.selectedCount === 0
              ? MainToolbar()
              : ActionsToolbar({ ...selectionContext })
          }
        </Table.ToolbarContainer>
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Select all checkbox behaviour
- description: <p>Control what happens when user clicks on ‘Select all’ checkbox when one or few items are already selected.</p><p>By default, the first click on indeterminate state selects all remaining items in the list. Change it to deselecting all items first with the <code>deselectRowsByDefault</code> prop.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const MainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Label>4 products</TableToolbar.Label>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const ActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <TableToolbar.Label>{`${selectedCount} selected`}</TableToolbar.Label>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Card>
        <Table
          showSelection
          data={records}
          columns={columns}
          deselectRowsByDefault={false}
          selectedIds={[0, 1]}
        >
          <Table.ToolbarContainer>
            {selectionContext =>
              selectionContext.selectedCount === 0
                ? MainToolbar()
                : ActionsToolbar({ ...selectionContext })
            }
          </Table.ToolbarContainer>
          <Table.Content />
        </Table>
      </Card>
      <Card>
        <Table
          showSelection
          data={records}
          columns={columns}
          deselectRowsByDefault={true}
          selectedIds={[0, 1]}
        >
          <Table.ToolbarContainer>
            {selectionContext =>
              selectionContext.selectedCount === 0
                ? MainToolbar()
                : ActionsToolbar({ ...selectionContext })
            }
          </Table.ToolbarContainer>
          <Table.Content />
        </Table>
      </Card>
    </StorybookComponents.Stack>
  );
};
```

### Disable selection
- description: <p>Restrict users from selecting a specific row by:</p><li>Hiding a checkbox for a row when row cannot be selected in any case with the <code>unselectable</code> prop.</li><li>Disabling a checkbox for a row on a certain condition. Define this condition using the <code>selectionDisabled</code> function. Use the <code>checkboxTooltipContent</code> prop to pass a tooltip message that explains why the row is disabled .</li><p></p><p><em>Note: </em>Tooltip message will not be reachable by assistive technologies and should be used as an additional explanation only. Make sure you explain the reason why item selection is not available in alternative ways, for example by using a subtitle or a different item status. </p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
      unselectable: true,
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
      unselectable: true,
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: (
        <Box direction="vertical">
          <Text size="small">Leather shoes</Text>
          <Text size="tiny" secondary light>
            This item is out of stock
          </Text>
        </Box>
      ),
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
      checkboxTooltipContent: 'This item is out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const MainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Label>4 products</TableToolbar.Label>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const ActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <TableToolbar.Label>{`${selectedCount} selected`}</TableToolbar.Label>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <Card hideOverflow>
      <Table
        showSelection
        data={records}
        columns={columns}
        selectionDisabled={rowData => rowData.inventory === 'Out of stock'}
        rowVerticalPadding="medium"
      >
        <Table.ToolbarContainer>
          {selectionContext =>
            selectionContext.selectedCount === 0
              ? MainToolbar()
              : ActionsToolbar({ ...selectionContext })
          }
        </Table.ToolbarContainer>
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Infinite scroll
- description: <p>Load data to the table progressively with <code>infiniteScroll</code>.</p><p>Specify a number of items to load at once with the <code>itemsPerPage</code> prop. The rest will load on demand when the user scrolls down the list.</p><p></p><p>Define how many items will be selected in infinite scroll table when user clicks on ‘Select All’ checkbox with the <code>totalSelectableCount</code> prop. Newly loaded items that fall into a specified range will be selected automatically once loaded.</p>
- example: 
```jsx 
() => {
  const totalProductCount = 50;
  const firstContainerRef = React.useRef(null);
  const [firstContainer, setFirstContainer] = React.useState(null);
  const secondContainerRef = React.useRef(null);
  const [secondContainer, setSecondContainer] = React.useState(null);
  const data = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
    {
      name: `Ceramic plant pots`,
      SKU: '00224239',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: `Black table lamp`,
      SKU: '00352464',
      price: '$119.00',
      inventory: 'In stock',
    },
    {
      name: 'Knitted scarf',
      SKU: '00486430',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: 'Home fragrance',
      SKU: '00515642',
      price: '$89.00',
      inventory: 'In stock',
    },
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black table lamp`,
      SKU: '00352464',
      price: '$119.00',
      inventory: 'In stock',
    },
  ];

  const [firstExampleRecords, setFirstExampleRecords] = React.useState(data);
  const [secondExampleRecords, setSecondExampleRecords] = React.useState(data);

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const fetchMoreFirstTableData = () =>
    new Promise(resolve => {
      setTimeout(
        () => setFirstExampleRecords([...firstExampleRecords, ...data]),
        2000,
      );
    });

  const fetchMoreSecondTableData = () =>
    new Promise(resolve => {
      setTimeout(
        () => setSecondExampleRecords([...secondExampleRecords, ...data]),
        2000,
      );
    });

  React.useEffect(() => {
    setFirstContainer(firstContainerRef);
    setSecondContainer(secondContainerRef);
  }, []);

  const MainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Label>
              {totalProductCount} products
            </TableToolbar.Label>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const ActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <TableToolbar.Label>{`${selectedCount} selected`}</TableToolbar.Label>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <div
        style={{ maxHeight: '360px', overflowY: 'scroll' }}
        ref={firstContainer}
      >
        <Card stretchVertically={true} hideOverflow>
          <Table
            data={firstExampleRecords}
            columns={columns}
            rowVerticalPadding="medium"
            loadMore={fetchMoreFirstTableData}
            infiniteScroll
            hasMore={firstExampleRecords.length < totalProductCount}
            itemsPerPage={10}
            scrollElement={firstContainer && firstContainer.current}
            loader={
              <Box align="center" padding="24px 0px">
                <Loader size="small" />
              </Box>
            }
          >
            <TableToolbar>
              <TableToolbar.ItemGroup position="start">
                <TableToolbar.Item>
                  <Text size="small">{totalProductCount} products</Text>
                </TableToolbar.Item>
              </TableToolbar.ItemGroup>
            </TableToolbar>
            <Table.Content />
          </Table>
        </Card>
      </div>
      <div
        style={{ maxHeight: '360px', overflowY: 'scroll' }}
        ref={secondContainer}
      >
        <Card stretchVertically={true}>
          <Table
            showSelection
            data={secondExampleRecords}
            columns={columns}
            loadMore={fetchMoreSecondTableData}
            infiniteScroll
            hasMore={secondExampleRecords.length < totalProductCount}
            itemsPerPage={10}
            totalSelectableCount={totalProductCount}
            scrollElement={secondContainer && secondContainer.current}
            loader={
              <Box align="center" padding="24px 0px">
                <Loader size="small" />
              </Box>
            }
          >
            <Table.ToolbarContainer>
              {selectionContext =>
                selectionContext.selectedCount === 0
                  ? MainToolbar()
                  : ActionsToolbar({ ...selectionContext })
              }
            </Table.ToolbarContainer>
            <Table.Content />
          </Table>
        </Card>
      </div>
    </StorybookComponents.Stack>
  );
};

```

### Pagination
- description: <p>Split up large amounts of data across multiple pages using <code><Pagination/></code>. Use it to give users control to manually navigate between pages. It's beneficial when users operate with data chunks instead of a full list.</p><p></p><p>In tables that have selection enabled, make sure to provide an option to ‘Select All’ items in a toolbar container next to selected items count.</p>
- example: 
```jsx 
() => {
  const [selectedFirstTablePage, setSelectedFirstTablePage] = React.useState(1);
  const [selectedSecondTablePage, setSelectedSecondTablePage] = React.useState(
    1,
  );

  const [selected, setSelected] = React.useState({});

  const data = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
    {
      name: `Ceramic plant pots`,
      SKU: '00224239',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: `Black table lamp`,
      SKU: '00352464',
      price: '$119.00',
      inventory: 'In stock',
    },
    {
      name: 'Knitted scarf',
      SKU: '00486430',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: 'Home fragrance',
      SKU: '00515642',
      price: '$89.00',
      inventory: 'In stock',
    },
    {
      name: `Ceramic plant pots`,
      SKU: '00224239',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: `Black table lamp`,
      SKU: '00352464',
      price: '$119.00',
      inventory: 'In stock',
    },
    {
      name: 'Knitted scarf',
      SKU: '00486430',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: 'Home fragrance',
      SKU: '00515642',
      price: '$89.00',
      inventory: 'In stock',
    },
  ];

  const records = Array.from(Array(12).keys())
    .map(page => Array.from(Array(8).keys()).map(() => data[page]))
    .flat()
    .map((item, index) => ({
      ...item,
      id: `record-${index}`,
    }));

  const [firstTableRecords, setFirstTableRecords] = React.useState(
    records.slice(0, 8),
  );

  const [secondTableRecords, setSecondTableRecords] = React.useState(
    records.slice(0, 8),
  );

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const _handleFirstTablePageChange = ({ page, event }) => {
    event.preventDefault();
    setSelectedFirstTablePage(page);
    setFirstTableRecords(records.slice((page - 1) * 8, (page - 1) * 8 + 8));
  };

  const _handleSecondTablePageChange = ({ page, event }) => {
    event.preventDefault();
    setSelectedSecondTablePage(page);
    setSecondTableRecords(records.slice((page - 1) * 8, (page - 1) * 8 + 8));
  };

  const updateSelectedRecords = props =>
    setSelected({
      ...selected,
      [`${selectedSecondTablePage}`]: props.filter(p =>
        secondTableRecords.map(({ id }) => id).includes(p),
      ),
    });

  const _renderMainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <Text size="small">
              <b>
                {(selectedSecondTablePage - 1) * 8 + 1} -
                {(selectedSecondTablePage - 1) * 8 + 8}
              </b>{' '}
              out of {records.length} products
            </Text>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const _renderActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <Box gap="12px">
            <Box gap="3px">
              <Text size="small" weight="bold">{`${
                Object.values(selected).flat().length
              }`}</Text>
              <Text size="small">{`out of ${records.length} selected`}</Text>
            </Box>
            <TextButton size="small" weight="normal">
              Select All
            </TextButton>
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Layout justifyItems="center">
        <Cell>
          <Card hideOverflow>
            <Table
              data={firstTableRecords}
              columns={columns}
              rowVerticalPadding="medium"
            >
              <TableToolbar>
                <TableToolbar.ItemGroup position="start">
                  <TableToolbar.Item>
                    <Text size="small">
                      <b>
                        {(selectedFirstTablePage - 1) * 8 + 1} -
                        {(selectedFirstTablePage - 1) * 8 + 8}
                      </b>{' '}
                      out of {records.length} products
                    </Text>
                  </TableToolbar.Item>
                </TableToolbar.ItemGroup>
              </TableToolbar>
              <Table.Content />
            </Table>
          </Card>
        </Cell>
        <Cell>
          <Pagination
            currentPage={selectedFirstTablePage}
            totalPages={12}
            onChange={_handleFirstTablePageChange}
          />
        </Cell>
      </Layout>
      <Layout justifyItems="center">
        <Cell>
          <Card hideOverflow>
            <Table
              data={secondTableRecords}
              columns={columns}
              showSelection
              infiniteScroll={false}
              onSelectionChanged={updateSelectedRecords}
              selectedIds={selected[selectedSecondTablePage]}
            >
              <Table.ToolbarContainer>
                {selectionContext =>
                  Object.values(selected).flat().length === 0
                    ? _renderMainToolbar()
                    : _renderActionsToolbar({ ...selectionContext })
                }
              </Table.ToolbarContainer>
              <Table.Content />
            </Table>
          </Card>
        </Cell>
        <Cell>
          <Pagination
            currentPage={selectedSecondTablePage}
            totalPages={12}
            onChange={_handleSecondTablePageChange}
          />
        </Cell>
      </Layout>
    </StorybookComponents.Stack>
  );
};
```

### No data empty state
- description: <p>Use <code><Table.EmptyState/></code> to indicate that there are no existing entries that could be shown in a table. Make sure the illustration you show reflects the type of items the table will contain.</p>
- example: 
```jsx 
() => {
  const renderTableToolbar = () => (
    <TableToolbar>
      <TableToolbar.Title>Products</TableToolbar.Title>
    </TableToolbar>
  );

  const renderEmptyState = () => (
    <Table.EmptyState
      title="Add your first product"
      subtitle="Once you add products, you'll be able to see and manage them here."
      image={
        <Image
          height={120}
          width={120}
          src="EmptyState_Generic1.svg"
          transparent
        />
      }
    >
      <TextButton prefixIcon={<Icons.Add />}>Add Product</TextButton>
    </Table.EmptyState>
  );

  return (
    <Card>
      <Table>
        {renderTableToolbar()}
        {renderEmptyState()}
      </Table>
    </Card>
  );
};
```

### No search results empty state
- description: <p>Make sure to provide an empty state when the user looks for content via search query or tries to narrow down the data list via filters and no items match the criterias.</p>
- example: 
```jsx 
() => {
  const [searchTerm, setSearchTerm] = React.useState('');
  const [right, setRight] = React.useState(-440);
  const [display, setDisplay] = React.useState('none');
  const [records, setRecords] = React.useState([
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ]);

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];

  const _clearSearch = () => {
    setSearchTerm('');
  };

  const _renderSearch = expandable => {
    return (
      <Search
        size="small"
        expandable={expandable}
        onChange={e => {
          setSearchTerm(e.target.value);
        }}
        value={searchTerm}
        onClear={_clearSearch}
      />
    );
  };

  const _getFilteredData = () => {
    let data = records;

    if (searchTerm !== '') {
      data = data.filter(row =>
        row.name.toUpperCase().includes(searchTerm.toUpperCase()),
      );
    }

    return data;
  };

  const filteredData = _getFilteredData();

  const _renderEmptyState = () => (
    <Table.EmptyState
      title="No results found"
      subtitle="No items match your search criteria. Try to search by another keyword."
      image={
        <Image
          width="120px"
          height="120px"
          transparent={true}
          src="https://api.lingoapp.com/v4/assets/6F4EC24D-ED41-4136-8050-837D05883F22/preview?size=480&asset_token=SIFGewyrciPVMNHqk6Nw3TI45qyWdJGJ2NOTGxR9FRA&hash=9d772b37ac8c805e780945a422a353b980b28e45&p=complete"
        />
      }
    >
      <TextButton>Clear Search</TextButton>
    </Table.EmptyState>
  );

  return (
    <Card hideOverflow>
      <Table data={filteredData} columns={columns} rowVerticalPadding="medium">
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <TableToolbar.Label>4 products</TableToolbar.Label>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
          <TableToolbar.ItemGroup position="end">
            <TableToolbar.Item>{_renderSearch(false)}</TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        {filteredData.length ? <Table.Titlebar /> : _renderEmptyState()}
        <Table.Content titleBarVisible={false} />
      </Table>
    </Card>
  );
};
```




    


## Common Use Case Examples


### Table in a modal
- description: <p>Render table without a toolbar when it is displayed in an overlay component, such as a <code><CustomModalLayout/></code> or a <code><SidePanel/></code>. Make sure content paddings in a selected layout is turned off.</p>
- example: 
```jsx 
() => {
  const data = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
    {
      name: `Ceramic plant pots`,
      SKU: '00224239',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: `Black table lamp`,
      SKU: '00352464',
      price: '$119.00',
      inventory: 'In stock',
    },
    {
      name: 'Knitted scarf',
      SKU: '00486430',
      price: '$19.00',
      inventory: 'In stock',
    },
    {
      name: 'Home fragrance',
      SKU: '00515642',
      price: '$89.00',
      inventory: 'In stock',
    },
  ];
  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
  ];
  return (
    <Box maxHeight={480}>
      <CustomModalLayout
        removeContentPadding
        primaryButtonText="Add"
        secondaryButtonText="Cancel"
        onCloseButtonClick={() => {}}
        title="Add products"
        showFooterDivider
      >
        <Table
          data={data}
          columns={columns}
          showSelection
          rowVerticalPadding="medium"
        >
          <Table.Content />
        </Table>
      </CustomModalLayout>
    </Box>
  );
};

```

### Filters
- description: <p>Enable users to find relevant data quicker by providing them with data filters and search.</p><p>We recommend to store up to 3 filters at once in a toolbar container. Check <code><Table.Toolbar/></code> page for all available toolbar arrangement options.</p>
- example: 
```jsx 
() => {
  const [filter, setFilter] = React.useState({
    collection: { id: '0', value: 'All Collections' },
    status: { id: '0', value: 'All Statuses' },
    name: '',
  });

  const data = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
      collection: '2021 Winter',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
      collection: '2021 Summer',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
      collection: '2021 Autumn',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
      collection: '2021 Winter',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
      collection: '2021 Spring',
    },
  ];

  const [records, setRecords] = React.useState(data);

  React.useEffect(() => {
    const dataFilteredByCollection =
      filter.collection.value === 'All Collections'
        ? data
        : data.filter(record => record.collection === filter.collection.value);

    const dataFilteredByCollectionAndStatus =
      filter.status.value === 'All Statuses'
        ? dataFilteredByCollection
        : dataFilteredByCollection.filter(
            record => record.inventory === filter.status.value,
          );

    setRecords(
      dataFilteredByCollectionAndStatus.filter(({ name }) =>
        name.includes(filter.name),
      ),
    );
  }, [filter]);

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Collection', render: row => row.collection },
    { title: 'Price', render: row => row.price },
  ];

  return (
    <Card hideOverflow>
      <Table data={records} columns={columns} rowVerticalPadding="medium">
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <Dropdown
                options={[
                  { id: '0', value: 'All Collections' },
                  { id: '1', value: '2021 Winter' },
                  { id: '2', value: '2021 Autumn' },
                  { id: '3', value: '2021 Summer' },
                  { id: '4', value: '2021 Spring' },
                ]}
                selectedId={filter.collection.id}
                border="round"
                size="small"
                popoverProps={{ appendTo: 'window' }}
                onSelect={collection => setFilter({ ...filter, collection })}
                valueParser={({ value }) => value}
              />
            </TableToolbar.Item>
            <TableToolbar.Item>
              <Dropdown
                options={[
                  { id: '0', value: 'All Statuses' },
                  { id: '1', value: 'In stock' },
                  { id: '2', value: 'Out of stock' },
                ]}
                selectedId={filter.status.id}
                border="round"
                size="small"
                onSelect={status => setFilter({ ...filter, status })}
                popoverProps={{ appendTo: 'window' }}
              />
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
          <TableToolbar.ItemGroup position="end">
            <TableToolbar.Item>
              <Search
                size="small"
                onChange={event =>
                  setFilter({ ...filter, name: event.target.value })
                }
                onClear={() => setFilter({ ...filter, name: '' })}
              />
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};

```

### Advanced filters
- description: <p>If there are more than 3 filters, transfer them outside of a table to a side panel. Add a button to a toolbar to call out this panel.</p><p><em>Note:</em> Make sure to inform users about currently active filters. Display them as a list of tags in a  <code><Table.Subtoolbar/></code> container.</p>
- example: 
```jsx 
() => {
  const price = {
    0: '0',
    1: '40',
    2: '80',
    3: '300',
  };

  const getPriceTagUserFriendlyValue = value =>
    value[0] === value[1]
      ? `$${price[value[0]]}`
      : `$${price[value[0]]} - $${price[value[1]]}`;
  
  const initialTags = [
    {
      type: 'collection',
      value: 'All Collections',
      id: Date.now() + Math.random(),
      children: 'All Collections',
    },
    {
      type: 'inventory',
      value: 'All Statuses',
      id: Date.now() + Math.random(),
      children: 'All Statuses',
      removable: false,
    },
    {
      type: 'price',
      value: [0, 3],
      id: Date.now() + Math.random(),
      children: getPriceTagUserFriendlyValue([0, 3]),
      removable: false,
    },
  ];

  const collections = [
    'All Collections',
    '2021 Winter',
    '2021 Spring',
    '2021 Summer',
    '2021 Fall',
  ];

  const data = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: 59.0,
      inventory: 'In Stock',
      items: 24,
      collection: '2021 Winter',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: 229.0,
      inventory: 'In Stock',
      items: 190,
      collection: '2021 Fall',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: 69.0,
      inventory: 'In Stock',
      items: 12,
      collection: '2021 Spring',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: 129.0,
      inventory: 'Out of Stock',
      items: 0,
      collection: '2021 Summer',
    },
    {
      name: `Ceramic plant pots`,
      SKU: '00224239',
      price: 19.0,
      inventory: 'In Stock',
      items: 34,
      collection: '2021 Winter',
    },
    {
      name: `Black table lamp`,
      SKU: '00352464',
      price: 119.0,
      inventory: 'Out of Stock',
      items: 0,
      collection: '2021 Winter',
    },
    {
      name: 'Knitted scarf',
      SKU: '00486430',
      price: 19.0,
      inventory: 'In Stock',
      items: 233,
      collection: '2021 Fall',
    },
    {
      name: 'Home fragrance',
      SKU: '00515642',
      price: 89.0,
      inventory: 'In Stock',
      items: 56,
      collection: '2021 Winter',
    },
  ];

  const [tags, setTags] = React.useState(initialTags);
  const [right, setRight] = React.useState(-440);
  const [display, setDisplay] = React.useState('none');
  const [records, setRecords] = React.useState(data);

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Items left', render: row => row.items },
    { title: 'Collection', render: row => row.collection },
    { title: 'Price', render: row => row.price },
  ];

  const tagExists = ({ type, value }) =>
    tags.some(tag => tag.type === type && tag.value === value);

  React.useEffect(() => {
    const recordsFilteredByCollection =
      tagExists({
        type: 'collection',
        value: 'All Collections',
      }) || tags.filter(({ type }) => type === 'collection').length === 0
        ? data
        : data.filter(({ collection }) =>
            tagExists({ type: 'collection', value: collection }),
          );

    const recordsFilteredByInventory = tagExists({
      type: 'inventory',
      value: 'All Statuses',
    })
      ? recordsFilteredByCollection
      : recordsFilteredByCollection.filter(({ inventory }) =>
          tagExists({ type: 'inventory', value: inventory }),
        );

    const priceTag = tags.find(({ type }) => type === 'price');

    const recordsFilteredByPrice = recordsFilteredByInventory.filter(
      tag =>
        tag.price >= price[priceTag.value[0]] &&
        tag.price <= price[priceTag.value[1]],
    );

    setRecords(recordsFilteredByPrice);
  }, [tags]);

  const removeTag = tagId => {
    const newTags = tags.filter(({ id }) => id !== tagId);

    setTags(newTags);
  };

  const toggleTag = ({ type, value }) => {
    if (tagExists({ type, value })) {
      setTags(tags.filter(tag => tag.type !== type || tag.value !== value));
    } else {
      setTags([...tags, { type, value, children: value, id: Date.now() }]);
    }
  };

  const handleInventoryTag = value => {
    const tagsWithNoInventory = tags.filter(({ type }) => type !== 'inventory');
    setTags([
      ...tagsWithNoInventory,
      {
        type: 'inventory',
        value,
        children: value,
        id: Date.now(),
        removable: false,
      },
    ]);
  };

  const openPanel = () => {
    setRight(0);
    setDisplay('block');
  };

  const closePanel = () => {
    setRight(-440);
    setDisplay('none');
  };

  const getInventoryTagValue = () =>
    tags.find(({ type }) => type === 'inventory').value;

  const handlePriceTag = value => {
    const tagsWithNoPrice = tags.filter(({ type }) => type !== 'price');
    setTags([
      ...tagsWithNoPrice,
      {
        type: 'price',
        value,
        children: getPriceTagUserFriendlyValue(value),
        id: Date.now(),
        removable: false,
      },
    ]);
  };

  const getPriceTagValue = () =>
    tags.find(({ type }) => type === 'price').value;

  return (
    <Page height="660px">
      <Page.Header title="Products" />
      <Page.Content>
        <Card hideOverflow>
          <Table data={records} columns={columns} rowVerticalPadding="medium">
            <TableToolbar>
              <TableToolbar.ItemGroup position="start">
                <TableToolbar.Item>
                  <TableToolbar.Label>8 products</TableToolbar.Label>
                </TableToolbar.Item>
              </TableToolbar.ItemGroup>
              <TableToolbar.ItemGroup position="end">
                <TableToolbar.Item>
                  <Button
                    size="small"
                    priority="secondary"
                    prefixIcon={<Icons.ContentFilterSmall />}
                    onClick={openPanel}
                  >
                    Filter (3)
                  </Button>
                </TableToolbar.Item>
                <TableToolbar.Item>
                  <Search size="small" />
                </TableToolbar.Item>
              </TableToolbar.ItemGroup>
            </TableToolbar>
            <Table.SubToolbar>
              <Box verticalAlign="middle" width="100%" align="space-between">
                <Box gap="12px" verticalAlign="middle">
                  <Text size="small">Filtered by:</Text>
                  <TagList
                    tags={tags}
                    actionButton={{ label: 'Clear All', onClick: () => setTags(initialTags) }}
                    onTagRemove={removeTag}
                  />
                </Box>
                <Button
                  skin="inverted"
                  size="tiny"
                  prefixIcon={<Icons.FavoriteSmall />}
                >
                  Save Filter
                </Button>
              </Box>
            </Table.SubToolbar>

            <Table.Content />
          </Table>
        </Card>
        <Box>
          <div
            style={{
              position: 'fixed',
              top: 0,
              right: `${right}px`,
              display: display,
              height: '100%',
              boxShadow:
                '0 3px 24px 0 rgba(22, 45, 61, 0.18), 0 8px 8px 0 rgba(22, 45, 61, 0.12)',
              zIndex: 9999,
              transition: 'right 0.4s ease 0s',
              overflow: 'hidden',
            }}
          >
            <SidePanel title="Filter" onCloseButtonClick={closePanel}>
              <SidePanel.Header title="Filter" />
              <Accordion
                skin="light"
                hideShadow
                size="small"
                items={[
                  accordionItemBuilder({
                    title: 'Collection',
                    children: (
                      <Box direction="vertical" gap="12px">
                        {collections.map(collection => (
                          <Checkbox
                            checked={tagExists({
                              type: 'collection',
                              value: collection,
                            })}
                            onChange={() =>
                              toggleTag({
                                type: 'collection',
                                value: collection,
                              })
                            }
                          >
                            {collection}
                          </Checkbox>
                        ))}
                      </Box>
                    ),
                  }),
                  accordionItemBuilder({
                    title: 'Inventory',
                    children: (
                      <RadioGroup
                        value={getInventoryTagValue()}
                        onChange={handleInventoryTag}
                      >
                        <RadioGroup.Radio value="All Statuses">
                          All Statuses
                        </RadioGroup.Radio>
                        <RadioGroup.Radio value="In Stock">
                          In Stock
                        </RadioGroup.Radio>
                        <RadioGroup.Radio value="Out of Stock">
                          Out of Stock
                        </RadioGroup.Radio>
                      </RadioGroup>
                    ),
                  }),
                  accordionItemBuilder({
                    title: 'Price',
                    children: (
                      <Slider
                        marks={{
                          0: `$${price[0]}`,
                          1: `$${price[1]}`,
                          2: `$${price[2]}`,
                          3: `$${price[3]}`,
                        }}
                        min={0}
                        max={3}
                        value={[0, 3]}
                        onChange={handlePriceTag}
                        value={getPriceTagValue()}
                      />
                    ),
                  }),
                ]}
              />
              <SidePanel.Footer>
                <Box gap="12px" paddingBottom="SP4">
                  <Text size="small">3 filters applied</Text>
                  <TextButton size="small">Clear</TextButton>
                </Box>
                <Button priority="secondary" onClick={closePanel} fullWidth>
                  Close
                </Button>
              </SidePanel.Footer>
            </SidePanel>
          </div>
        </Box>
      </Page.Content>
    </Page>
  );
};

```

### Sticky table toolbar
- description: <p>Wrap table toolbar to  a<code><Page.Sticky/></code> element to keep it always visible to users. Use it for infinite scroll tables.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      image: <Image width="72px" height="48px" src="FoodExample1.jpg" />,
      title: 'Hot to make French toast',
      published: 'Sep 25, 2022',
      category: 'Food · ',
      length: '8 min',
      status: <Badge skin="neutralSuccess">Published</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample2.jpg" />,
      title: 'Homemade pasta',
      published: 'Sep 12, 2022',
      category: 'Food · ',
      length: '11 min',
      status: <Badge skin="neutralSuccess">Published</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample3.jpg" />,
      title: '56 last minute Christmas dinner ideas',
      published: '',
      category: 'Food · ',
      length: '5 min',
      status: <Badge skin="neutralLight">Draft</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample4.jpg" />,
      title: 'Breakfast in 5 minutes',
      published: '',
      category: 'Food · ',
      length: '5 min',
      status: <Badge skin="neutralLight">Draft</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample5.jpg" />,
      title: 'Homemade soup',
      published: '',
      category: 'Food · ',
      length: '2 min',
      status: <Badge skin="neutralLight">Draft</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample1.jpg" />,
      title: 'Hot to make French toast',
      published: 'Sep 25, 2022',
      category: 'Food · ',
      length: '8 min',
      status: <Badge skin="neutralLight">Draft</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample2.jpg" />,
      title: 'Homemade pasta',
      published: 'Sep 12, 2022',
      category: 'Food · ',
      length: '11 min',
      status: <Badge skin="neutralSuccess">Published</Badge>,
    },
    {
      image: <Image width="72px" height="48px" src="FoodExample3.jpg" />,
      title: '56 last minute Christmas dinner ideas',
      published: '',
      category: 'Food · ',
      length: '5 min',
      status: <Badge skin="neutralLight">Draft</Badge>,
    },
  ];

  const primaryAction = {
    text: 'Edit',
    skin: 'standard',
    onClick: () => {},
  };

  const secondaryActions = [
    {
      text: 'Share',
      icon: <Icons.ShareSmall />,
      onClick: () => {},
    },
    {
      text: 'Duplicate',
      icon: <Icons.DuplicateSmall />,
      onClick: () => {},
    },
    {
      text: 'Delete',
      icon: <Icons.DeleteSmall />,
      onClick: () => {},
    },
  ];

  const columns = [
    { title: '', width: '72px', render: row => row.image },
    {
      title: 'Title',
      render: row => (
        <Box direction="vertical" gap="3px">
          <Text size="medium" weight="normal">
            {row.title}
          </Text>
          <Text size="tiny" weight="thin" secondary>
            {row.category}
            {row.length}
          </Text>
        </Box>
      ),
      width: '40%',
    },
    { title: 'Publish Date', render: row => row.published, width: '15%' },
    { title: 'Status', render: row => row.status, width: '15%' },
    {
      render: rowData => (
        <TableActionCell
          size="small"
          primaryAction={primaryAction}
          secondaryActions={secondaryActions}
          numOfVisibleSecondaryActions={1}
          popoverMenuProps={{ appendTo: 'window' }}
          moreActionsTooltipText="More actions"
        />
      ),
    },
  ];

  return (
    <Page height="540px">
      <Page.Header title="Blog posts" />
      <Page.Content>
        <Table data={records} columns={columns}>
          <Page.Sticky>
            <Card>
              <TableToolbar>
                <TableToolbar.ItemGroup position="start">
                  <TableToolbar.Item>
                    <Text size="small">5 items</Text>
                  </TableToolbar.Item>
                </TableToolbar.ItemGroup>
              </TableToolbar>
              <Table.Titlebar />
            </Card>
          </Page.Sticky>
          <Card>
            <Table.Content titleBarVisible={false} />
          </Card>
        </Table>
      </Page.Content>
    </Page>
  );
};
```


