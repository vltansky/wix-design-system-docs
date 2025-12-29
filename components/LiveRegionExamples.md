
## Feature Examples


### Broadcast
- description: <p>Specify a message to announce for screen reader users with <code>broadcast</code> prop.</p>
- example: 
```jsx 
() => {
  const ref = React.useRef();

  const onButtonClick = () => {
    ref.current.broadcast({message: 'This is a message'})
  };

  return (
    <StorybookComponents.Stack >
      <LiveRegion ref={ref} />
      <Button onClick={onButtonClick}>Broadcast</Button>
    </StorybookComponents.Stack >
  );
};
```

### Role
- description: <p>Specify how urgently a message should be broadcasted with <code>role</code> prop.</p><p></p><p>There are 2 roles types:</p><li><code>status</code> (default) - use it when it’s important that user receives updates about changes in the region, but not so rapidly that natural flow would be interrupted. Screen reader will announce a message after the current message is delivered.</li><li><code>alert</code> - use for time sensitive and critical notifications that require immediate users attention. Message will be announced right away, even if screen reader is currently in the middle of a sentence. As such, it can be disruptive and should be <strong>used sparingly</strong>.</li>
- example: 
```jsx 
() => {
  const ref = React.useRef();

  const onButtonClick = role => {
    const message =
      role === 'alert'
        ? 'This is an alert message'
        : 'This is a status message';

    ref.current.broadcast({message, role})
  };

  return (
    <StorybookComponents.Stack>
      <LiveRegion ref={ref} />
      <Button onClick={() => onButtonClick('alert')}>
        Broadcast alert message
      </Button>
      <Button onClick={() => onButtonClick('status')}>
        Broadcast status message
      </Button>
    </StorybookComponents.Stack>
  );
}
```




    


## Common Use Case Examples


### Remove item
- description: <p>Use <code>live region</code> to inform screen reader users about items removed from the page.</p>
- example: 
```jsx 
() => {
  const liveRef = React.useRef();
  const addBtnRef = React.useRef();
  const inputRef = React.useRef([]);
  const [rows, setRows] = React.useState([
    { id: 1, value: '' },
    { id: 2, value: '' },
  ]);
  const [mounted, setMounted] = React.useState(false);
  const [itemAdded, setItemAdded] = React.useState(false);

  const removeItem = (idToRemove, index) => {
    if (rows.length === 1) {
      addBtnRef.current.focus();
    } else {
      const indexToFocus = index === 0 ? 1 : index-1;
      inputRef.current[indexToFocus].focus();
    }
    setRows(rows.filter(({ id }) => id !== idToRemove));
    liveRef.current.broadcast({ message: 'Item deleted' });
  };

  const addItem = () => {
    setRows([...rows, { id: new Date().getTime(), value: '' }]);
    liveRef.current.broadcast({ message: 'Item Added' });
    setItemAdded(true);
  };
  
  React.useEffect(() => {
    if(itemAdded) {
      inputRef.current[inputRef.current.length-1].focus();
      setItemAdded(false);
    }
  }, [itemAdded]);

  React.useEffect(() => {  
    inputRef.current = inputRef.current.slice(0, rows.length);
  }, [inputRef.current]);

  return (
    <Box direction="vertical" gap="SP3">
      <LiveRegion ref={liveRef} />
      {rows.map( (row, index) => (
        <Box key={row.id} gap="SP2">
          <Box width="100%" direction="vertical">
            <Input ref={el => {inputRef.current[index] = el}} value={row.value} placeholder="e.g., Unlimited yoga classes" />
          </Box>
          <IconButton skin="inverted" onClick={() => removeItem(row.id, index)}>
            <Icons.Delete />
          </IconButton>
        </Box>
      ))}

      <TextButton ref={addBtnRef} onClick={addItem} prefixIcon={<Icons.Add />}>
        Add Item
      </TextButton>
    </Box>
  );
};

```

### Duplicate item
- description: <p>Use <code>live region</code> to inform screen reader users about duplicated items added to the page.</p>
- example: 
```jsx 
() => {
  const ref = React.useRef();
  const inputRef = React.useRef([]);
  const [rows, setRows] = React.useState([
    { id: 1, value: '' },
    { id: 2, value: '' },
  ]);
  const [mounted, setMounted] = React.useState(false);

  const duplicateItem = index => {
    setRows([...rows, { id: new Date().getTime(), value: rows[index].value }]);
    inputRef.current = inputRef.current.slice(0, rows.length);
    ref.current.broadcast({ message: 'Item duplicated', role: 'status' });
  };

  const handleOnChange = (index, value) => {
    const updatedRows = rows.map((row, i) => (index === i ? { ...row, value } : row));
    setRows(updatedRows);
  };

  React.useEffect(() => {
    if (!mounted) {
      setMounted(true);
      return;
    }

    inputRef.current[rows.length - 1].focus();
  }, [inputRef.current]);

  return (
    <Box direction="vertical" gap="SP3">
      <LiveRegion ref={ref} />
      {rows.map((row, index) => (
        <Box gap="SP2">
          <Box width="100%" direction="vertical">
            <Input
              value={row.value}
              ref={el => {
                inputRef.current[index] = el;
              }}
              placeholder="e.g., Unlimited yoga classes"
              onChange={e => {
                handleOnChange(index, e.target.value);
              }}
            />
          </Box>
          <IconButton skin="inverted" onClick={() => duplicateItem(index)}>
            <Icons.Duplicate />
          </IconButton>
        </Box>
      ))}
    </Box>
  );
};
```

### Filter Table
- description: <p>Use <code>live region</code> to inform users about the number of items that match their filter criteria.</p>
- example: 
```jsx 
() => {
  const liveRef = React.useRef();

  const [selectedOption, setSelectedOption] = React.useState(0);

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

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Collection', render: row => row.collection },
    { title: 'Price', render: row => row.price },
  ];

  const handleSelection = option => {
    setSelectedOption(option.id);
    const filteredData =
      option.value === 'All Collections'
        ? data
        : data.filter(item => item.collection === option.value);
    setRecords(filteredData);

    const numOfItemsFound = filteredData.length;
    liveRef.current.broadcast({
      message: `${numOfItemsFound} ${
        numOfItemsFound > 1 ? 'items' : 'item'
      } found`,
      role: 'status',
    });
  };

  return (
    <Card hideOverflow>
      <LiveRegion ref={liveRef} />
      <Table data={records} columns={columns} rowVerticalPadding="medium">
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <FormField label="Filter by">
                <Dropdown
                  options={[
                    { id: 0, value: 'All Collections' },
                    { id: 1, value: '2021 Winter' },
                    { id: 2, value: '2021 Autumn' },
                    { id: 3, value: '2021 Summer' },
                    { id: 4, value: '2021 Spring' },
                  ]}
                  selectedId={selectedOption}
                  border="round"
                  size="small"
                  popoverProps={{ appendTo: 'window' }}
                  onSelect={handleSelection}
                  valueParser={({ value }) => value}
                />
              </FormField>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};

```


