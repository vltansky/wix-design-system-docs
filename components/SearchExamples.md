
## Feature Examples


### Size
- description: <p>Adjust the component's size using the <code>size</code>  prop. It supports 3 sizes:</p><li><code>large</code> is for onboarding flows, where the input needs more emphasis.</li><li><code>medium</code> is the default used in all common cases.</li><li><code>small</code> should only be used in dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Search size="large" placeholder="Large" />
  <Search size="medium" placeholder="Medium" />
  <Search size="small" placeholder="Small" />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Style the component using the <code>border</code> prop. It supports 4 styles:</p><li><code>round</code> is the default used in all common cases.</li><li><code>standard</code> is for when search is part of a form.</li><li><code>bottomLine</code> is for titles that can be edited on selection.</li><li><code>none</code> should be used in the Content Manager's spreadsheet cell.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Search border="round" placeholder="Search..." />
  <Search border="standard" placeholder="Search..." />
  <Search border="bottomLine" placeholder="Search..." />
  <Search border="none" placeholder="Search..." />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control a component's status using the <code>status</code> prop. It supports 3 states:</p><li><code>loading</code> is to show that a value is being uploaded to the server or that results are loading.</li><li><code>error</code> is inherited from input, but there's no use case at the moment.</li><li><code>warning</code> is inherited from input, but there's no use case at the moment.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Search status="loading" placeholder="Search..." />
  <Search status="error" placeholder="Search..." />
  <Search status="warning" placeholder="Search..." />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FormField status="loading" statusMessage="This is a loading message.">
    <Search placeholder="See message below" />
  </FormField>
  <Search
    status="loading"
    placeholder="Hover on the loader"
    statusMessage="This is a loading message."
  />
</StorybookComponents.Stack>;
```

### Read-only and disabled
- description: <p>The component can be set to read-only or <code>disabled</code>. To disable users from typing into the input, but allow them to copy or remove an entered value, use the <code>readOnly</code> prop.  </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Search readOnly value="Read only" />
  <Search disabled value="Disabled" />
</StorybookComponents.Stack>;
```

### Clear button
- description: <p>Remove entered keywords quickly with a clear button. The button is enabled by default for all search fields. Avoid removing it if possible.</p>
- example: 
```jsx 
() => {
  const [inputText, setInputText] = React.useState(
    'Click clear button to erase this value',
  );

  return (
    <Search
      value={inputText}
      clearButton
      onChange={e => setInputText(e.target.value)}
      onClear={() => setInputText('')}
    />
  );
};
```

### Options
- description: <p>Provide common suggestions by passing an array of <code>options</code> to a component. A <code>predicate</code> function can be used to filter these options.</p><p></p><p>In this example, <code>predicate</code> makes the search input case sensitive.</p>
- example: 
```jsx 
() => {
  const [text, setText] = React.useState('');
  const options = [
    { value: 'Option 1', id: 0 },
    { value: 'Option 2', id: 1 },
    { value: 'Option 3', id: 2 },
    { value: 'Option 4', id: 3 },
    { value: 'Option 5', id: 4 },
  ];

  return (
    <Search
      value={text}
      onChange={e => setText(e.target.value)}
      onClear={() => setText('')}
      options={options}
      predicate={option => option.value.indexOf(text) !== -1}
    />
  );
};
```

### Options container dimensions
- description: <p>Control container size with three properties.</p><li><code>maxHeightPixels</code> specifies the maximum height for longer lists.</li><li><code>dropdownWidth</code> sets the width to "auto" or "max-content" to match the content width or specify it in pixels.</li><li><code>minWidthPixels</code> increases the width of the dropdown popover manually.</li>
- example: 
```jsx 
() => {
  const [text, setText] = React.useState('');
  const options = [
    { value: 'Option 1', id: 0 },
    { value: 'Option 2', id: 1 },
    { value: 'Option 3', id: 2 },
    { value: 'Option 4', id: 3 },
    { value: 'Option 5', id: 4 },
  ];

  return (
    <StorybookComponents.Stack>
      <Search
        value={text}
        clearButton={true}
        onChange={e => setText(e.target.value)}
        onClear={() => setText('')}
        options={options}
        maxHeightPixels="160px"
        minWidthPixels="300px"
        dropdownWidth="auto"
        popoverProps={{
          placement: 'bottom-start',
        }}
      />
    </StorybookComponents.Stack>
  );
};
```

### Expandable
- description: <p>Collapse the search input into an icon button and only expand it intentionally on click with the <code>expandable</code> prop. Control the width of expanded input with <code>expandWidth</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Search expandable />
  <Search expandable expandWidth="400px" />
</StorybookComponents.Stack>;
```

### Debounce
- description: <p>Control the delay of a search in milliseconds with the <code>debounceMs</code> prop. Use it to prevent sending a query to the server before the user finishes typing.</p>
- example: 
```jsx 
() => {
  const [textInstant, setTextInstant] = React.useState('');
  const [textDelayed, setTextDelayed] = React.useState('');

  return (
    <StorybookComponents.Stack flexDirection="column">
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Search
          placeholder="Search for instant results..."
          value={textInstant}
          onChange={e => setTextInstant(e.target.value)}
          onClear={() => setTextInstant('')}
        />
        <StorybookComponents.Stack>
          <Text size="tiny">Results for:</Text>
          <Text size="tiny" weight="bold" skin="primary">
            {textInstant}
          </Text>
        </StorybookComponents.Stack>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Search
          placeholder="Search for delayed results..."
          debounceMs={250}
          value={textDelayed}
          onChange={e => setTextDelayed(e.target.value)}
          onClear={() => setTextDelayed('')}
        />
        <StorybookComponents.Stack>
          <Text size="tiny">Results for:</Text>
          <Text size="tiny" weight="bold" skin="primary">
            {textDelayed}
          </Text>
        </StorybookComponents.Stack>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Filtering the list
- description: Use search as an action inside tables or cards to filter large data sets.
- example: 
```jsx 
() => {
  const [filterBy, setFilterBy] = React.useState('');
  const [activeSearch, setActiveSearch] = React.useState('');

  const records = [
    {
      name: 'Red slippers',
      sku: 25232564,
      status: 'In stock',
      price: '$14.00',
    },
    { name: 'Velvet hat', sku: 35246432, status: 'In stock', price: '$29.00' },
    {
      name: 'Silver jeans',
      sku: 4864310,
      status: 'Out of stock',
      price: '$69.00',
    },
    {
      name: 'Orange socks',
      sku: 125156422,
      status: 'In stock',
      price: '$7.00',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.sku },
    { title: 'Status', render: row => row.status },
    { title: 'Price', render: row => row.price },
  ];

  const filterOptions = [
    { id: '', value: 'All statuses' },
    { id: 'In stock', value: 'In stock' },
    { id: 'Out of stock', value: 'Out of stock' },
  ];

  const getFilteredData = () =>
    records.filter(({ name, sku, status, price }) => {
      if (filterBy && status !== filterBy) {
        return false;
      }

      const searchData = [name, sku, status, price].join(' ').toLowerCase();
      const searchQuery = activeSearch.trim().toLowerCase();
      if (searchQuery && searchData.indexOf(searchQuery) === -1) {
        return false;
      }

      return true;
    });

  const MainToolbar = () => {
    return (
      <TableToolbar>
        <TableToolbar.ItemGroup position="start">
          <TableToolbar.Item>
            <TableToolbar.Title>Products</TableToolbar.Title>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
        <TableToolbar.ItemGroup position="end">
          <TableToolbar.Item>
            <TableToolbar.Label>
              Filter by
              <Box width="175">
                <Dropdown
                  size="small"
                  options={filterOptions}
                  selectedId={filterBy}
                  border="round"
                  onSelect={({ id }) => setFilterBy(id)}
                />
              </Box>
            </TableToolbar.Label>
          </TableToolbar.Item>
          <TableToolbar.Item>
            <Box width="200">
              <Search
                size="small"
                value={activeSearch}
                onChange={e => setActiveSearch(e.target.value)}
                onClear={() => setActiveSearch('')}
              />
            </Box>
          </TableToolbar.Item>
        </TableToolbar.ItemGroup>
      </TableToolbar>
    );
  };

  const ActionsToolbar = ({ selectedCount, getSelectedIds }) => (
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <TableToolbar.SelectedCount>{`${selectedCount} Selected`}</TableToolbar.SelectedCount>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup position="end">
        <TableToolbar.Item layout="button">
          <Button skin="light" prefixIcon={<Icons.Upload />}>
            Export
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button skin="light" prefixIcon={<Icons.Duplicate />}>
            Duplicate
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button skin="light" prefixIcon={<Icons.Edit />}>
            Edit
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Divider />
        <TableToolbar.Item>
          <Search
            expandable
            value={activeSearch}
            onChange={e => setActiveSearch(e.target.value)}
          />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  );

  return (
    <Card>
      <Table showSelection data={getFilteredData()} columns={columns}>
        <Table.ToolbarContainer>
          {selectionContext =>
            selectionContext.selectedCount === 0
              ? MainToolbar()
              : ActionsToolbar({ ...selectionContext })
          }
        </Table.ToolbarContainer>
        <Table.Content />
        {!records.length && (
          <Table.EmptyState
            subtitle={
              <Text>
                {'There are no search results matching '}
                <Text weight="normal">{`"${activeSearch}"`}</Text>
              </Text>
            }
          />
        )}
      </Table>
    </Card>
  );
};
```


