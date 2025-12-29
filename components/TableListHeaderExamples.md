
## Feature Examples


### Structure
- description: <p>Table list headers can have any number of columns. The default column value is text, but it can be replaced with other component.</p><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListHeader
    options={[
      { value: <StorybookComponents.Placeholder height="30px"/>},
      { value: <StorybookComponents.Placeholder height="30px"/> },
      { value: <StorybookComponents.Placeholder height="30px"/> },
      { value: <StorybookComponents.Placeholder height="30px"/> },
    ]}
  />
  <TableListHeader
    options={[
      { value: 'Name'},
      { value: 'Email' },
      { value: 'Phone' },
      { value: 'Company' },
    ]}
  />
</StorybookComponents.Stack>;
```

### Number of columns
- description: <p>To define the required number of columns in a table, use the <code>options</code> array.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListHeader options={[{ value: 'Name', width: '1fr' }]} />
  <TableListHeader
    options={[
      { value: 'Name', width: '1fr' },
      { value: 'Email', width: '3fr' },
    ]}
  />
  <TableListHeader
    options={[
      { value: 'Name', width: '1fr' },
      { value: 'Email', width: '1fr' },
      { value: 'Phone', width: '2fr' },
    ]}
  />
  <TableListHeader
    options={[
      { value: 'Name', width: '1fr' },
      { value: 'Email', width: '1fr' },
      { value: 'Phone', width: '1fr' },
      { value: 'Company', width: '1fr' },
    ]}
  />
</StorybookComponents.Stack>;
```

### Column width
- description: <p>Specify the width of each column in pixels, percentages or frames with the <code>width</code> prop. If not specified, columns will be sized equally.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListHeader
    options={[
      { value: 'Name', width: '25%' },
      { value: 'Email', width: '25%' },
    ]}
  />
  <TableListHeader
    options={[
      { value: 'Name', width: '1fr' },
      { value: 'Email', width: '1fr' },
    ]}
  />
</StorybookComponents.Stack>;
```

### Column alignment
- description: <p>Control content alignment in a column with the <code>align</code> prop. It supports 3 options:</p><li><code>left</code> (default)</li><li><code>center</code></li><li><code>right</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListHeader
    options={[{ value: 'Align:' }, { value: 'Left', align: 'left' }]}
  />
  <TableListHeader
    options={[{ value: 'Align:' }, { value: 'Center', align: 'center' }]}
  />
  <TableListHeader
    options={[{ value: 'Align:' }, { value: 'Right', align: 'right' }]}
  />
</StorybookComponents.Stack>;
```

### Column info
- description: <p>Include additional info to explain data in a specific column by adding an info icon next to titles. Use <code>infoTooltipProps</code> to show a message that will be displayed in a tooltip on hover.</p>
- example: 
```jsx 
<TableListHeader
  options={[
    {
      value: 'Name',
      infoTooltipProps: {
        content: 'Add additional info to explain this column value here',
      },
    },
    {
      value: 'Email',
      infoTooltipProps: {
        content: 'Add additional info to explain this column value here',
      },
    },
    { value: 'Phone' },
    {
      value: 'Company',
      infoTooltipProps: {
        content: 'Add additional info to explain this column value here',
      },
    },
  ]}
/>;
```

### Selectable
- description: <p>Add a checkbox that allows users to select all the items below the header with the <code>checkboxState</code> prop. It supports 6 values:</p><p></p><li><code>hidden</code> (default)</li><li><code>normal</code></li><li><code>checked</code></li><li><code>indeterminate</code></li><li><code>hasError</code></li><li><code>disabled</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListHeader
    options={[{ value: 'Hidden (default)' }]}
    checkboxState="hidden"
  />
  <TableListHeader
    options={[{ value: 'Normal' }]}
    checkboxState="normal"
    onCheckboxChange={() => {}}
  />
  <TableListHeader
    options={[{ value: 'Checked' }]}
    checkboxState="checked"
    onCheckboxChange={() => {}}
  />
  <TableListHeader
    options={[{ value: 'Indeterminate' }]}
    checkboxState="indeterminate"
    onCheckboxChange={() => {}}
  />
  <TableListHeader
    options={[{ value: 'Has error' }]}
    checkboxState="hasError"
    onCheckboxChange={() => {}}
  />
  <TableListHeader options={[{ value: 'Disabled' }]} checkboxState="disabled" />
</StorybookComponents.Stack>;
```

### Sortable
- description: <p>Allow users to sort data displayed below the header by clicking on column titles with the <code>sortable</code> prop. </p><p></p><li><code>sortDescending</code>for setting which arrow displays next to a column title.</li><li><code>onSortChange</code> is for defining behavior each time a user clicks on a title.</li>
- example: 
```jsx 
<TableListHeader
  onSortChange={() => {}}
  options={[
    { value: 'Name', sortable: true, sortDescending: true },
    { value: 'Email', sortable: true },
    { value: 'Phone', sortable: true },
    { value: 'Company', sortable: true },
  ]}
/>;
```




    


## Common Use Case Examples


### Table with sections
- description: <p>Table list headers can be used to build custom table layouts, for example, a table that's divided into sections but still allows sorting and filter data.  </p>
- example: 
```jsx 
() => {
  const indexToColumn = {
    0: 'fieldName',
    1: 'type',
    2: 'appliesTo',
  };

  const [headerOptions, setHeaderOptions] = React.useState([
    {
      value: 'Field name',
      width: '3fr',
      sortable: true,
      sortDescending: true,
    },
    {
      value: 'Type',
      width: '3fr',
      sortable: true,
      sortDescending: true,
    },
    {
      value: 'Applies to',
      width: '2fr',
      sortable: true,
      sortDescending: true,
    },
  ]);

  const [items, setItems] = React.useState([
    { id: 0, text: 'Display info', isHeading: true },
    {
      id: 1,
      fieldName: 'Title',
      type: 'Public',
      appliesTo: 'All members',
    },
    {
      id: 2,
      text: 'Account',
      isHeading: true,
    },
    {
      id: 3,
      fieldName: 'First name',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 4,
      fieldName: 'Last name',
      type: 'Public',
      appliesTo: 'All members',
    },
    {
      id: 5,
      fieldName: 'Email',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 6,
      fieldName: 'Phone',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 7,
      fieldName: 'Company',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 8,
      text: 'Address',
      isHeading: true,
    },
    {
      id: 9,
      fieldName: 'Street',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 10,
      fieldName: 'City',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 11,
      fieldName: 'Zip code',
      type: 'Private',
      appliesTo: 'All members',
    },
    {
      id: 12,
      fieldName: 'Country',
      type: 'Private',
      appliesTo: 'All members',
    },
  ]);

  const itemStyleProps = {
    common: {
      boxSizing: 'border-box',
      width: '100%',
      height: '50px',
      backgroundColor: 'WHITE',
      borderWidth: '1px',
      borderStyle: 'solid',
      borderColor: 'B20',
      borderRadius: '6px',
      verticalAlign: 'middle',
      paddingLeft: '12px',
      marginBottom: '0px',
    },
    placeholder: {
      borderStyle: 'none',
      backgroundColor: 'B50',
    },
  };

  const handleDrop = ({ removedIndex, addedIndex }) => {
    const nextItems = [...items];
    nextItems.splice(addedIndex, 0, ...nextItems.splice(removedIndex, 1));
    setItems(nextItems);
  };

  const renderItem = ({ isPlaceholder, isPreview, item }) => {
    return (
      <div>
        {item.isHeading && (
          <Card.Subheader
            title=<Text size="small">{item.text}</Text>
            skin="neutral"
          />
        )}
        {!item.isHeading && isPlaceholder && (
          <Box {...itemStyleProps.common} {...itemStyleProps.placeholder}></Box>
        )}
        {!item.isHeading && !isPlaceholder && (
          <TableListItem
            draggable
            showDivider
            onClick={() => {}}
            options={[
              { value: <Text>{item.fieldName}</Text>, width: '3fr' },
              {
                value: (
                  <Box gap="SP1" color="D30">
                    <Icons.LockLockedSmall />
                    <Text secondary size="small">
                      {item.type}
                    </Text>
                  </Box>
                ),
                width: '3fr',
              },
              {
                value: (
                  <Text secondary skin="primary" size="small">
                    {item.appliesTo}
                  </Text>
                ),
                width: '2fr',
              },
            ]}
          />
        )}
      </div>
    );
  };

  const canDrag = ({ item }) => {
    return !item.isHeading;
  };

  const sortItems = (index, sortDescending) => {
    const sortedItems = items
      .reduce((array, currentItem) => {
        if (currentItem.isHeading || array[array.length - 1][0].isHeading) {
          array.push([currentItem]);
        } else {
          array[array.length - 1].push(currentItem);
        }

        return array;
      }, [])
      .map(itemsArray => {
        const returnValueWhenPreviousBigger = sortDescending ? 1 : -1;
        return itemsArray.sort((a, b) => {
          if (a[indexToColumn[index]] < b[indexToColumn[index]]) {
            return -returnValueWhenPreviousBigger;
          }

          if (a[indexToColumn[index]] > b[indexToColumn[index]]) {
            return returnValueWhenPreviousBigger;
          }

          return 0;
        });
      })
      .flat();

    setItems(sortedItems);
  };

  const handleSort = index => {
    const sortDescending = headerOptions[index].sortDescending;
    const nextHeaderOptions = [...headerOptions];
    nextHeaderOptions[index].sortDescending = !sortDescending;
    setHeaderOptions(nextHeaderOptions);

    sortItems(index, !sortDescending);
  };

  return (
    <Card hideOverflow>
      <Card.Header
        title="Customize form"
        subtitle="Set up fields and decide what info appears on public profile pages"
      />
      <Box direction="vertical">
        <TableListHeader onSortChange={handleSort} options={headerOptions} />
        <SortableListBase
          items={items}
          renderItem={renderItem}
          onDrop={handleDrop}
          canDrag={canDrag}
        />
      </Box>
    </Card>
  );
};
```


