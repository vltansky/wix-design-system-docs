
## Feature Examples


### Structure
- description: <p>A tag list consists of any number of tags followed by 2 action buttons:</p><p></p><li>Use <code>toggleMoreButton</code> to expand/collapse the list.</li><li> Use <code>actionButton</code> to control bulk list actions (e.g., Clear All).</li><p></p><p>Both buttons are optional. The order of the tags and buttons is fixed.</p>
- example: 
```jsx 
<TagList
  tags={[
    { id: '1', children: 'Tag 1' },
    { id: '2', children: 'Tag 2' },
    { id: '3', children: 'Tag 3' },
    { id: '4', children: 'Tag 4' },
    { id: '5', children: 'Tag 5' },
  ]}
  toggleMoreButton={(amountOfHiddenTags, isExpanded) => ({
    label: isExpanded ? 'Show Less' : `+${amountOfHiddenTags} More`,
    tooltipContent: !isExpanded && 'Show More',
  })}
  actionButton={{ label: 'Action Button' }}
  onTagRemove={() => {}}
/>;
```

### Size
- description: <p>Control the size of entire tag lists with <code>size</code> prop:</p><p></p><li> Use <code>small</code> (default) in all default cases.</li><li>Use <code>medium</code> in bigger layouts.</li><li>Use <code>large</code> when tag lists need to be emphasized.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack>
    <TagList
      tags={[{ id: '1', children: 'Small' }]}
      actionButton={{ label: 'Small' }}
      onTagRemove={() => {}}
    />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <TagList
      size="medium"
      tags={[{ id: '1', children: 'Medium' }]}
      actionButton={{ label: 'Medium' }}
      onTagRemove={() => {}}
    />
  </StorybookComponents.Stack>

  <StorybookComponents.Stack>
    <TagList
      size="large"
      tags={[{ id: '1', children: 'Large' }]}
      actionButton={{ label: 'Large' }}
      onTagRemove={() => {}}
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Tag props
- description: <p>Customize individual tags with <code><Tag/></code> component props:</p><p></p><li>Set the color of a tag using <code>theme</code>.</li><li>Display a thumbnail inside a tag using <code>thumb.</code></li><li>Switch tag to a disabled state using <code>disabled</code>.</li><li>Show or hide a close button on the right side of a tag using <code>removable</code> .</li><li>Set a max tag width in px using <code>maxWidth</code>. If a label is longer, text gets truncated with ellipses.</li><p></p><p>See <code><Tag/></code> for a full prop description.</p>
- example: 
```jsx 
<TagList
  tags={[
    {
      id: '1',
      theme: 'success',
      children: 'theme',
    },
    {
      id: '2',
      children: 'thumb',
      thumb: (
        <Avatar
          imgProps={{
            src: 'AvatarExample1.jpg',
          }}
          size="size18"
        />
      ),
    },
    {
      id: '3',
      disabled: true,
      children: 'disabled',
    },
    {
      id: '4',
      removable: false,
      children: 'removable',
    },
    {
      id: '5',
      maxWidth: 100,
      children: 'maxWidth',
    },
  ]}
  maxVisibleTags="5"
  onTagRemove={() => {}}
/>;
```

### Toggle more button props
- description: <p>Control the appearance of <code>toggleMoreButton</code> with <code>skin</code> and <code>priority</code> props.</p><p></p><p>Set its skin as <code>standard</code> and priority as <code>secondary</code> to emphasize the component <code>actionButton</code> on the left.</p>
- example: 
```jsx 
<TagList
  tags={[
    { id: '1', children: 'Tag 1' },
    { id: '2', children: 'Tag 2' },
    { id: '3', children: 'Tag 3' },
    { id: '4', children: 'Tag 4' },
    { id: '5', children: 'Tag 5' },
  ]}
  maxVisibleTags={3}
  actionButton={{ label: 'Action Button' }}
  toggleMoreButton={(amountOfHiddenTags, isExpanded) => ({
    label: isExpanded ? 'Show Less' : `+${amountOfHiddenTags} More`,
    tooltipContent: !isExpanded && 'Show More',
    skin: 'standard',
    priority: 'secondary',
  })}
  onTagRemove={() => {}}
/>;
```

### Max visible tags
- description: <p>Limit the number of visible tags with <code>maxVisibleTags</code> prop (default is 3).</p><p></p><p>Use it to fit a tag list in one line and keep the layout compact.</p><p></p><p>If tags surpass the limit, give an option to expand the full list with <code>toggleMoreButton</code> prop.</p><p></p><p>Note that if the component width is larger than the parent container, it will display on multiple lines when expanded.</p>
- example: 
```jsx 
<TagList
  tags={[
    { id: '1', children: 'Tag 1' },
    { id: '2', children: 'Tag 2' },
    { id: '3', children: 'Tag 3' },
    { id: '4', children: 'Tag 4' },
    { id: '5', children: 'Tag 5' },
    { id: '6', children: 'Tag 6' },
    { id: '7', children: 'Tag 7' },
    { id: '8', children: 'Tag 8' },
    { id: '9', children: 'Tag 9' },
    { id: '10', children: 'Tag 10' },
    { id: '11', children: 'Tag 11' },
    { id: '12', children: 'Tag 12' },
  ]}
  maxVisibleTags={3}
  toggleMoreButton={(amountOfHiddenTags, isExpanded) => ({
    label: isExpanded ? 'Show Less' : `+${amountOfHiddenTags} More`,
    tooltipContent: !isExpanded && 'Show More',
  })}
  onTagRemove={() => {}}
/>;
```

### Initially expanded
- description: <p>Define whether the list is expanded initially with an <code>initiallyExpanded</code> prop.</p>
- example: 
```jsx 
() => {
  const tags = [
    { id: '1', children: 'Tag 1' },
    { id: '2', children: 'Tag 2' },
    { id: '3', children: 'Tag 3' },
    { id: '4', children: 'Tag 4' },
    { id: '5', children: 'Tag 5' },
  ];

  const toggleMore = (amountOfHiddenTags, isExpanded) => ({
    label: isExpanded ? 'Show Less' : `+${amountOfHiddenTags} More`,
    tooltipContent: !isExpanded && 'Show More',
  });

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Text size="small">Not Initially Expanded</Text>
      <TagList
        tags={tags}
        initiallyExpanded={false}
        toggleMoreButton={toggleMore}
        onTagRemove={() => {}}
      />
      <Text size="small">Initially Expanded</Text>
      <TagList
        tags={tags}
        initiallyExpanded
        toggleMoreButton={toggleMore}
        onTagRemove={() => {}}
      />
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Applied filters list
- description: <p>Use a tag list to show which filters are applied in a <code><Table/></code>.</p>
- example: 
```jsx 
() => {
  const tags = [
    { id: 1, children: 'In Stock' },
    { id: 2, children: 'Accessories' },
  ];

  const initialState = {
    tableData: [],
    selectedInventoryStatusId: 0,
    selectedProductTypeId: 0,
    tags,
    activeSearch: '',
  };
  const [state, setState] = React.useReducer(
    (currentState, newState) => ({ ...currentState, ...newState }),
    initialState,
  );

  const getProductTypeFilterById = id =>
    productTypeFilter.find(type => type.id === id);

  const getInventoryStatusFilterById = id =>
    inventoryStatusFilter.find(inventory => inventory.id === id);

  const filterRecords = ({ inventoryStatusId, productTypeId }) => {
    const inventoryStatus = getInventoryStatusFilterById(inventoryStatusId);
    const productType = getProductTypeFilterById(productTypeId);

    return records.filter(record => {
      const inventoryStatusFilter =
        !inventoryStatus || record.inventory === inventoryStatus.value;
      const productTypeFilter =
        !productType || record.type === productType.value;

      return inventoryStatusFilter && productTypeFilter;
    });
  };

  React.useEffect(() => {
    setState({
      tableData: filterRecords({ inventoryStatusId: 1, productTypeId: 1 }),
      selectedInventoryStatusId: 1,
      selectedProductTypeId: 1,
    });
  }, []);

  const records = [
    {
      name: `Red Slippers`,
      SKU: '0231664667',
      price: '$14.00',
      inventory: 'In Stock',
      type: 'Accessories',
    },
    {
      name: `Velvet Hat`,
      SKU: '0231664669',
      price: '$23.00',
      inventory: 'In Stock',
      type: 'Accessories',
    },
    {
      name: `Silver Bag`,
      SKU: '0231664667',
      price: '$69.00',
      inventory: 'In Stock',
      type: 'Accessories',
    },
    {
      name: `Orange Socks`,
      SKU: '0231662525',
      price: '$9.00',
      inventory: 'Out of Stock',
      type: 'Accessories',
    },
    {
      name: `Red Socks`,
      SKU: '0231664671',
      price: '$19.00',
      inventory: 'In Stock',
      type: 'Accessories',
    },
    {
      name: `Gold Earrings`,
      SKU: '0231666090',
      price: '$22.00',
      inventory: 'Out of Stock',
      type: 'Accessories',
    },
    {
      name: `Blue Jeans`,
      SKU: '0231664525',
      price: '$59.00',
      inventory: 'In Stock',
      type: 'Clothing',
    },
    {
      name: `Black Jacket`,
      SKU: '0231664000',
      price: '$89.00',
      inventory: 'In Stock',
      type: 'Clothing',
    },
    {
      name: `Black Belt`,
      SKU: '0231664672',
      price: '$19.00',
      inventory: 'In Stock',
      type: 'Accessories',
    },
  ];

  const columns = [
    {
      title: 'Name',
      render: row => row.name,
      width: '25%',
    },
    {
      title: 'SKU',
      render: row => row.SKU,
      width: '25%',
    },
    {
      title: 'Price',
      render: row => row.price,
      width: '25%',
    },
    {
      title: 'Inventory',
      render: row => row.inventory,
      width: '25%',
    },
  ];
  const inventoryStatusFilter = [
    { id: 1, value: 'In Stock' },
    { id: 2, value: 'Out of Stock' },
  ];
  const productTypeFilter = [
    { id: 1, value: 'Accessories' },
    { id: 2, value: 'Clothing' },
  ];

  const clearAll = () =>
    setState({
      tags: [],
      selectedInventoryStatusId: 0,
      selectedProductTypeId: 0,
      tableData: records,
    });

  const removeTag = tagId => {
    const tags = state.tags.filter(({ id }) => id !== tagId);

    const inventoryStatusId = tags.find(tag => tag.id === 1)
      ? state.selectedInventoryStatusId
      : 0;
    const productTypeId = tags.find(tag => tag.id === 2)
      ? state.selectedProductTypeId
      : 0;

    setState({
      tags,
      tableData: filterRecords({
        inventoryStatusId,
        productTypeId,
      }),
      selectedInventoryStatusId: inventoryStatusId,
      selectedProductTypeId: productTypeId,
    });
  };

  const onOptionChange = ({
    inventoryStatusId = state.selectedInventoryStatusId,
    productTypeId = state.selectedProductTypeId,
  }) => {
    setState({
      selectedProductTypeId: productTypeId,
      selectedInventoryStatusId: inventoryStatusId,
      tableData: filterRecords({
        inventoryStatusId,
        productTypeId,
      }),
      tags: filterTags({ inventoryStatusId, productTypeId }),
    });
  };

  const filterTags = ({ inventoryStatusId, productTypeId }) => {
    const inventoryStatus = getInventoryStatusFilterById(inventoryStatusId);
    const productType = getProductTypeFilterById(productTypeId);
    const tags = [];

    inventoryStatus && tags.push({ id: 1, children: inventoryStatus.value });
    productType && tags.push({ id: 2, children: productType.value });

    return tags;
  };

  const getFilteredData = () => {
    if (!state.activeSearch) {
      return state.tableData;
    }

    return state.tableData.filter(({ name, sku, price, inventory, type }) => {
      const searchData = [name, sku, price, inventory, type]
        .join(' ')
        .toLowerCase();
      const searchQuery = state.activeSearch.trim().toLowerCase();
      return !searchQuery || searchData.indexOf(searchQuery) !== -1;
    });
  };

  return (
    <Card>
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Title>Products</TableToolbar.Title>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
        <TableToolbar.ItemGroup position="end">
          <TableToolbar.Item>
            <Box gap={2} verticalAlign="middle">
              <Text>Filter by</Text>
              <Dropdown
                size="small"
                placeholder="Inventory status"
                border="round"
                options={inventoryStatusFilter}
                selectedId={state.selectedInventoryStatusId}
                onSelect={option =>
                  onOptionChange({ inventoryStatusId: option.id })
                }
              />
              <Dropdown
                size="small"
                placeholder="Type"
                border="round"
                options={productTypeFilter}
                selectedId={state.selectedProductTypeId}
                onSelect={option =>
                  onOptionChange({ productTypeId: option.id })
                }
              />
            </Box>
          </TableToolbar.Item>
          <TableToolbar.Item>
            <Box width="200">
              <Search
                value={state.activeSearch}
                onChange={e => setState({ activeSearch: e.target.value })}
                onClear={() => setState({ activeSearch: '' })}
              />
            </Box>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
      {state.tags.length ? (
        <Table.SubToolbar>
          <Box align="space-between" verticalAlign="middle">
            <Cell>
              <FormField label="Filtered by:" labelPlacement="left">
                <TagList
                  tags={state.tags}
                  actionButton={{ label: 'Clear All', onClick: clearAll }}
                  onTagRemove={removeTag}
                />
              </FormField>
            </Cell>
            <Cell>
              <Button
                size="tiny"
                skin="inverted"
                prefixIcon={<Icons.FavoriteSmall />}
              >
                Save Filter
              </Button>
            </Cell>
          </Box>
        </Table.SubToolbar>
      ) : null}
      <Table data={getFilteredData()} columns={columns}>
        <Table.Content />
      </Table>
    </Card>
  );
};
```


