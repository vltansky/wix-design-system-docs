
## Feature Examples


### Size
- description: <p>Adjust the component <code>size</code> using the size prop. It supports 3 sizes:</p><li><code>large</code> - use it in onboarding flows, where the field needs emphasis.</li><li><code>medium</code> (default) - use in all common cases.</li><li><code>small</code> - use in more dense and narrow layouts.</li>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelectCheckbox size="large" placeholder="Large" options={options} />
      <MultiSelectCheckbox
        size="medium"
        placeholder="Medium"
        options={options}
      />
      <MultiSelectCheckbox size="small" placeholder="Small" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Border
- description: <p>Style the component using the <code>border</code> prop. It supports 4 styles:</p><li><code>standard</code> (default) - use in forms.</li><li><code>round</code> - use when the component is used as a filter.</li><li><code>bottomLine</code> - use as a title which can be edited on the click.</li><li><code>none</code> - use in Content Manager's spreadsheet cell.</li>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelectCheckbox
        border="standard"
        placeholder="Standard"
        options={options}
      />
      <MultiSelectCheckbox
        border="round"
        placeholder="Round"
        options={options}
      />
      <MultiSelectCheckbox
        border="bottomLine"
        placeholder="Bottom line"
        options={options}
      />
      <MultiSelectCheckbox border="none" placeholder="None" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Status
- description: <p>Control the component status using a <code>status</code> prop. It supports 3 states:</p><li><code>error</code> - use to highlight an invalid selection.</li><li><code>warning</code> - use to highlight a value that impacts the user or that can’t be validated.</li><li><code>loading</code> - use to show that the value is being uploaded to the server.</li>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelectCheckbox
        status="error"
        placeholder="Error"
        options={options}
      />
      <MultiSelectCheckbox
        status="warning"
        placeholder="Warning"
        options={options}
      />
      <MultiSelectCheckbox
        status="loading"
        placeholder="Loading"
        options={options}
      />
    </StorybookComponents.Stack>
  );
};
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the component is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For all default cases:</Text>
        <FormField status="error" statusMessage="This is an error message.">
          <MultiSelectCheckbox
            placeholder="See message below"
            tooltipPlacement="top-end"
            options={options}
          />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For narrow layouts only:</Text>
        <MultiSelectCheckbox
          placeholder="Hover on status icon"
          status="error"
          statusMessage="This is an error message."
          tooltipPlacement="top-end"
          options={options}
        />
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```

### Disabled
- description: <p>Disable all input interactions with <code>disabled</code> prop. Use to highlight unavailable functions.</p>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <MultiSelectCheckbox placeholder="Disabled" disabled options={options} />
  );
};
```

### Affix
- description: <p>Support the input value with additional information added to the <code>prefix</code> and <code>suffix</code> props.</p><p></p><p>These areas can contain text, icons and even badges.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelectCheckbox
        placeholder="Select"
        prefix={<Input.Affix>Prefix</Input.Affix>}
        suffix={<Input.Affix>Suffix</Input.Affix>}
        options={options}
      />
      <MultiSelectCheckbox
        placeholder="Select"
        prefix={
          <Input.IconAffix>
            <Icons.Languages />
          </Input.IconAffix>
        }
        suffix={
          <Input.IconAffix>
            <Badge>Badge</Badge>
          </Input.IconAffix>
        }
        options={options}
      />
    </StorybookComponents.Stack>
  );
};
```

### Clear button
- description: <p>Enable a button that clears the dropdown value by using <code>clearButton</code> prop. Show it when the field value is optional or needs to be cleared.</p>
- example: 
```jsx 
() => {
  const [selectedOptions, setSelectedOptions] = React.useState([0]);
  const options = [{ id: 0, value: 'Click clear button to remove selection' }];

  return (
    <MultiSelectCheckbox
      placeholder="Select"
      clearButton
      onClear={() => setSelectedOptions([])}
      onSelect={(option) => setSelectedOptions([option])}
      selectedOptions={selectedOptions}
      options={options}
    />
  );
};
```

### Fixed header and footer
- description: <p>Add related actions to <code>fixedFooter</code> or <code>fixedHeader</code> areas. Areas keep their position on scroll.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 1, value: 'Option 1' },
    { id: 2, value: 'Option 2' },
    { id: 3, value: 'Option 3' },
    { id: 4, value: 'Option 4' },
    { id: 5, value: 'Option 5' },
  ];

  return (
    <MultiSelectCheckbox
      placeholder="Select"
      fixedHeader={<ListItemAction title="Fixed Header" />}
      fixedFooter={<ListItemAction title="Fixed Footer" />}
      options={options}
    />
  );
};
```

### List item builders
- description: <p>Build custom options layouts with:</p><li><code>listItemSectionBuilder</code> - use to group items into sections by type. See <code><ListItemSection/></code> for more details.</li><li><code>listItemActionBuilder</code> - use to add text button for related list actions, i.e. ‘Manage categories’. See <code><ListItemAction/></code> for more details.</li><li><code>listItemSelectBuilder</code> - use to build custom list designs. See <code><ListItemSelect/></code> for more details.</li>
- example: 
```jsx 
() => {
  const listItemSectionOptions = [
    listItemSectionBuilder({
      type: 'title',
      title: 'Section 1',
    }),
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    listItemSectionBuilder({
      type: 'divider',
    }),

    listItemSectionBuilder({
      type: 'title',
      title: 'Section 2',
    }),
    { id: 3, value: 'Option 4' },
    { id: 4, value: 'Option 4' },
  ];

  const listItemActionOptions = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
    listItemActionBuilder({
      title: 'Action',
    }),
  ];

  const listItemSelectOptions = [
    listItemSelectBuilder({
      id: 0,
      prefix: <Avatar size="size30" />,
      title: 'Title',
      subtitle: 'Subtitle',
      suffix: 'Suffix',
      checkbox: true,
    }),
    listItemSelectBuilder({
      id: 1,
      prefix: <Avatar size="size30" />,
      title: 'Title',
      subtitle: 'Subtitle',
      suffix: 'Suffix',
      checkbox: true,
    }),
    listItemSelectBuilder({
      id: 2,
      prefix: <Avatar size="size30" />,
      title: 'Title',
      subtitle: 'Subtitle',
      suffix: 'Suffix',
      checkbox: true,
    }),
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelectCheckbox
        placeholder="List Item Section"
        options={listItemSectionOptions}
      />
      <MultiSelectCheckbox
        placeholder="List Item Action"
        options={listItemActionOptions}
      />
      <MultiSelectCheckbox
        placeholder="List Item Select"
        options={listItemSelectOptions}
      />
    </StorybookComponents.Stack>
  );
};
```

### List container dimensions
- description: <p>Control the container size for options with:</p><li><code>maxHeightPixels</code> - use to specify maximum height for longer lists.</li><li><code>dropdownWidth</code> - set width to 'auto' or 'max-content' to match content width or specify it in pixels.</li><li><code>minWidthPixels</code> - use to increase dropdown popover width manually.</li><p></p><p>By default, the dropdown matches the input field width.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
    { id: 4, value: 'Option 5' },
    { id: 5, value: 'Option 6' },
    { id: 6, value: 'Option 7' },
    { id: 7, value: 'Option 8' },
  ];

  return (
    <StorybookComponents.Stack>
      <MultiSelectCheckbox
        placeholder="Select"
        maxHeightPixels="200px"
        dropdownWidth="auto"
        minWidthPixels="400px"
        options={options}
        popoverProps={{
          placement: 'bottom-start',
        }}
      />
    </StorybookComponents.Stack>
  );
};
```

### Marked option
- description: <p>Control what to highlight with a hover state once the dropdown is opened with the <code>markedOption</code> prop.</p>
- example: 
```jsx 
<MultiSelectCheckbox
  placeholder="Select"
  markedOption={1}
  options={[
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ]}
/>;
```

### Delimiter
- description: <p>Specify what character to use to separate selected options with the <code>delimiter</code> prop.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelectCheckbox
        placeholder="Select"
        selectedOptions={[0, 1, 2]}
        delimiter=", "
        options={options}
      />
      <MultiSelectCheckbox
        placeholder="Select"
        selectedOptions={[0, 1, 2]}
        delimiter=";  "
        options={options}
      />
    </StorybookComponents.Stack>
  );
};
```

### Lazy loading
- description: <p>Indicate that options are loading from a server or load a large list of items gradually with the <code>infiniteScroll</code>, <code>loadMore</code> and <code>hasMore</code> props.</p>
- example: 
```jsx 
() => {
  const [selectedOptions, setSelectedOptions] = React.useState([]);

  const [data, setData] = React.useState([]);
  const fetchMoreData = () =>
    Promise.resolve(
      fetch(`/api/dropdown?limit=${5}&offset=${data.length}`),
    ).then((results) => setData([...data, ...results]));

  React.useEffect(() => {
    fetchMoreData();
  }, []);

  return (
    <MultiSelectCheckbox
      placeholder="Select"
      options={data}
      infiniteScroll
      hasMore={true}
      loadMore={fetchMoreData}
      selectedOptions={selectedOptions}
      onSelect={(option) => setSelectedOptions([...selectedOptions, option])}
      onDeselect={(option) =>
        setSelectedOptions(selectedOptions.filter((item) => item !== option))
      }
    />
  );
};
```

### Text overflow
- description: <p>Control text overflow for:</p><li>The field itself: set the <code>textOverflow</code> prop either to clip or ellipsis.</li><li>The dropdown layout: it wraps longer values by default. In order to have ellipses, select the items that have to be rendered with the <code>listItemSelectBuilder</code>.</li>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
    { id: 4, value: 'Option 5' },
  ];
  const longOptions = [
    {
      id: 0,
      value: 'This is a long value that make dropdown layout grow',
    },
    {
      id: 1,
      value: 'This is a long value that make dropdown layout grow',
    },
    {
      id: 2,
      value: 'This is a long value that make dropdown layout grow',
    },
  ];
  const longOptionsWithEllipsis = [
    listItemSelectBuilder({
      id: 0,
      title: 'This is a long value that make dropdown layout grow',
      ellipsis: true,
      checkbox: true,
    }),
    listItemSelectBuilder({
      id: 1,
      title: 'This is a long value that make dropdown layout grow',
      ellipsis: true,
      checkbox: true,
    }),
    listItemSelectBuilder({
      id: 2,
      title: 'This is a long value that make dropdown layout grow',
      ellipsis: true,
      checkbox: true,
    }),
  ];
  return (
    <StorybookComponents.Stack flexDirection="column">
      <StorybookComponents.Stack>
        <FormField label="Input value - ellipsis">
          <MultiSelectCheckbox
            options={options}
            selectedOptions={[0, 1, 2, 3, 4]}
            placeholder="This field is showing ellipsis at the end of this line"
            textOverflow="ellipsis"
          />
        </FormField>
        <FormField label="Input value - clip">
          <MultiSelectCheckbox
            options={options}
            selectedOptions={[0, 1, 2, 3, 4]}
            placeholder="This field is clipping content at the end of this line"
            textOverflow="clip"
          />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack>
        <FormField label="Options - wrapping">
          <MultiSelectCheckbox options={longOptions} placeholder="Select" />
        </FormField>
        <FormField label="Options - with ellipsis">
          <MultiSelectCheckbox
            options={longOptionsWithEllipsis}
            placeholder="Select"
          />
        </FormField>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```

### Selected items value
- description: <p>Customize how the selected values are represented inside of an input.</p>
- example: 
```jsx 
() => {
  const [state, setState] = React.useState({
    selectedOptions: [0, 1, 2, 3, 4],
    inputValue: 'All items selected',
  });
  const getInputValue = (selectedOptions) => {
    if (selectedOptions.length === optionsList.length) {
      return 'All items selected';
    }
    return selectedOptions
      .map((id) => optionsList.find((option) => option.id === id).value)
      .join(', ');
  };
  const onSelect = (optionId) => {
    const selectedOptions = [...state.selectedOptions, optionId];
    setState({ selectedOptions, inputValue: getInputValue(selectedOptions) });
  };
  const onDeselect = (optionId) => {
    const selectedOptions = state.selectedOptions.filter(
      (item) => item !== optionId,
    );
    setState({ selectedOptions, inputValue: getInputValue(selectedOptions) });
  };
  const optionsList = [
    { value: 'Option 1', id: 0 },
    { value: 'Option 2', id: 1 },
    { value: 'Option 3', id: 2 },
    { value: 'Option 4', id: 3 },
    { value: 'Option 5', id: 4 },
  ];
  return (
    <MultiSelectCheckbox
      options={optionsList}
      selectedOptions={state.selectedOptions}
      onSelect={onSelect}
      onDeselect={onDeselect}
      value={state.inputValue}
    />
  );
};
```




    


## Common Use Case Examples


### Form element
- description: Use MultiSelectCheckbox in forms to apply multiple values.
- example: 
```jsx 

() => {
  const serviceOptions = [
    { id: 0, value: 'Web design' },
    { id: 1, value: 'Branding' },
    { id: 2, value: 'SEO' },
    { id: 3, value: 'Web development' },
    { id: 4, value: 'Marketing' },
  ];
  const businessOptions = [
    { id: 0, value: 'Agency' },
    { id: 1, value: 'Freelancer' },
    { id: 2, value: 'Other' },
  ];
  const renderServiceMultiSelect = () => {
    const [selectedOptions, setSelectedOptions] = React.useState([1, 2]);
    return (
      <FormField label="What services do you offer?">
        <MultiSelectCheckbox
          options={serviceOptions}
          selectedOptions={selectedOptions}
          onSelect={option => setSelectedOptions([...selectedOptions, option])}
          onDeselect={option =>
            setSelectedOptions(selectedOptions.filter(item => item !== option))
          }
        />
      </FormField>
    );
  };
  const renderBusinessDropdown = () => {
    const [selected, setSelected] = React.useState(1);
    return (
      <FormField label="What best describes your business?" required>
        <Dropdown
          placeholder="Select"
          selectedId={selected}
          options={businessOptions}
          onSelect={option => setSelected(option.id)}
        />
      </FormField>
    );
  };
  const renderBusinessLogoUpload = (
    <FormField label="Business Logo" infoContent="Minimum size 300 x 100 px">
      <FileUpload>
        {({ openFileUploadDialog }) => (
          <Box width="200px" height="132px">
            <AddItem
              theme="image"
              tooltipContent="Upload Logo"
              onClick={openFileUploadDialog}
            >
              Add Item
            </AddItem>
          </Box>
        )}
      </FileUpload>
    </FormField>
  );
  const renderMainBusinessInfoFields = (
    <Layout cols={1}>
      <FormField label="Business Name" required>
        <Input placeholder="Type your business name" />
      </FormField>
      <FormField label="Business Site URL">
        <Input placeholder="https://www.mybusinesswebsite.com" />
      </FormField>
    </Layout>
  );
  return (
    <Card>
      <Card.Header
        title="Business Details"
        subtitle="These details will be used for emailing, invoicing, and more."
      />
      <Card.Divider />
      <Card.Content>
        <Layout>
          <Cell span={8}>{renderMainBusinessInfoFields}</Cell>
          <Cell span={4}>{renderBusinessLogoUpload}</Cell>
          <Cell>
            <Divider />
          </Cell>
          <Cell>
            <Heading size="small">More Details</Heading>
          </Cell>
          <Cell>
            <Layout>
              <Cell span={6}>{renderBusinessDropdown()}</Cell>
              <Cell span={6}>{renderServiceMultiSelect()}</Cell>
            </Layout>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};

```

### List item builders
- description: Build custom layouts within a list item builder for advanced filters.
- example: 
```jsx 

() => {
  const [filterOptions, setFilterOptions] = React.useState({
    filterBy: [],
    selectedOptions: [],
  });

  const authorOptions = [
    listItemSectionBuilder({
      type: 'title',
      title: 'In-house',
    }),
    { id: 0, value: 'Christian Mills' },
    { id: 1, value: 'Etta Wheeler' },
    { id: 2, value: 'Paul Simons' },
    listItemSectionBuilder({
      type: 'divider',
    }),

    listItemSectionBuilder({
      type: 'title',
      title: 'Contributors',
    }),
    { id: 3, value: 'Robert Ortega' },
    { id: 4, value: 'Mary James' },
  ];

  const [items, setItems] = React.useState([
    {
      id: 0,
      title: 'Getting a grasp on adventure',
      author: 'Christian Mills',
      contributor: 'Robert Ortega',
      date: 'Jan 26, 2021',
      checked: false,
    },
    {
      id: 1,
      title: '10 tips for relaxation',
      author: 'Etta Wheeler',
      contributor: 'Mary James',
      date: 'Jun 9, 2020',
      checked: false,
    },
    {
      id: 2,
      title: 'Performance standards for digital trust and safety',
      author: 'Paul Simons',
      contributor: 'Mary James',
      date: 'Sep 12, 2020',
      checked: false,
    },
    {
      id: 3,
      title: 'Getting a grasp on adventure',
      author: 'Christian Mills',
      contributor: 'Robert Ortega',
      date: 'Jan 26, 2021',
      checked: false,
    },
  ]);

  const onAuthorFilterSelect = id => {
    setFilterOptions({
      selectedOptions: [...filterOptions.selectedOptions, id],
      filterBy: [
        ...filterOptions.filterBy,
        authorOptions.find(item => item.id === id).value,
      ],
    });
  };

  const onAuthorFilterDeselect = id => {
    const selectedOptions = filterOptions.selectedOptions.filter(
      item => item !== id,
    );

    setFilterOptions({
      filterBy: selectedOptions.map(
        id => authorOptions.find(author => author.id === id).value,
      ),
      selectedOptions,
    });
  };

  const renderAddToCategory = () => {
    const [shown, setShown] = React.useState(false);
    const [categories, setCategories] = React.useState([
      {
        id: 0,
        title: 'Getting started',
        checked: false,
      },
      {
        id: 1,
        title: 'Your Community',
        checked: false,
      },
    ]);

    return (
      !isAllUnchecked() && (
        <Popover
          showArrow
          shown={shown}
          appendTo="viewport"
          placement="bottom"
          width="250px"
          onClickOutside={() => setShown(false)}
        >
          <Popover.Element>
            <TextButton
              size="small"
              prefixIcon={<Icons.Tag />}
              onClick={() => setShown(!shown)}
            >
              Add to Category
            </TextButton>
          </Popover.Element>
          <Popover.Content>
            <Box
              backgroundColor="D80"
              direction="vertical"
              gap="SP2"
              padding="SP3"
            >
              <Text light secondary size="small">
                Categories
              </Text>
              {categories.map(category => (
                <Checkbox
                  checked={category.checked}
                  onChange={() =>
                    setCategories(
                      categories.map(item =>
                        item.id === category.id
                          ? { ...category, checked: !category.checked }
                          : item,
                      ),
                    )
                  }
                >
                  {category.title}
                </Checkbox>
              ))}
              <Divider />
              <Box align="space-between" paddingTop="SP2">
                <Button
                  skin="inverted"
                  size="small"
                  onClick={() => setShown(false)}
                >
                  Cancel
                </Button>
                <Button size="small" onClick={() => setShown(false)}>
                  Apply
                </Button>
              </Box>
            </Box>
          </Popover.Content>
        </Popover>
      )
    );
  };

  const renderAuthorsSelect = () =>
    isAllUnchecked() && (
      <MultiSelectCheckbox
        value="All authors"
        size="small"
        dropdownWidth="240px"
        maxHeightPixels="400px"
        border="round"
        options={authorOptions}
        popoverProps={{
          placement: 'bottom-start',
        }}
        selectedOptions={filterOptions.selectedOptions}
        onSelect={onAuthorFilterSelect}
        onDeselect={onAuthorFilterDeselect}
      />
    );

  const renderTableItem = item => {
    return (
      <TableListItem
        checkbox
        checked={item.checked}
        onCheckboxChange={() =>
          setItems(
            items.map(currentItem =>
              currentItem.id === item.id
                ? { ...item, checked: !item.checked }
                : currentItem,
            ),
          )
        }
        showDivider
        options={[
          { value: <Image />, width: '90px' },
          {
            value: (
              <Box direction="vertical" gap="3px">
                <Text>{item.title}</Text>
                <Text size="tiny" secondary>
                  {item.date} • {item.author}
                </Text>
              </Box>
            ),
          },
          {
            width: '20%',
            value: (
              <TableActionCell
                primaryAction={{
                  text: 'Edit',
                  skin: 'standard',
                }}
              />
            ),
          },
        ]}
      />
    );
  };

  const renderTableItems = () => {
    if (filterOptions.filterBy.length === 0) {
      return items.map(item => renderTableItem(item));
    }

    const filtered = items.filter(item =>
      filterOptions.filterBy.find(
        filter => filter === item.author || filter === item.contributor,
      ),
    );
    return filtered.map(item => renderTableItem(item));
  };

  const isAllChecked = () =>
    items.filter(item => item.checked).length === items.length;
  const isAllUnchecked = () => items.filter(item => item.checked).length === 0;

  const toggleAll = checked =>
    setItems(items.map(item => ({ ...item, checked })));

  return (
    <Card>
      <Card.Header
        title={
          <Checkbox
            onChange={() => {
              isAllChecked() ? toggleAll(false) : toggleAll(true);
            }}
            checked={isAllChecked()}
          >
            Select all
          </Checkbox>
        }
        suffix={
          <>
            {renderAuthorsSelect()}
            {renderAddToCategory()}
          </>
        }
      />
      <Card.Divider />
      {renderTableItems()}
    </Card>
  );
};

```


