
## Feature Examples


### Size
- description: <p>Adjust the component size using the <code>size</code> prop. It supports 3 sizes.</p><li>Give the dropdown more emphasis with the <code>large</code> size. </li><li><code>medium</code> is the default size and should be used in most cases.</li><li>In layouts with a lot of dense content use <code>small</code>.</li>
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
      <AutoComplete placeholder="Large" size="large" options={options} />
      <AutoComplete placeholder="Medium" size="medium" options={options} />
      <AutoComplete placeholder="Small" size="small" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Border
- description: <p>Style the component using the <code>border</code> prop, which supports 4 styles.</p><li>For forms, use <code>standard</code>.</li><li>When the component is used to filter, use <code>round</code>.</li><li>For titles that can be edited on click, use <code>bottomLine</code>.</li><li>In the Content Manager’s spreadsheet, use <code>none</code>.</li>
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
      <AutoComplete
        placeholder="Standard"
        border="standard"
        options={options}
      />
      <AutoComplete placeholder="Round" border="round" options={options} />
      <AutoComplete
        placeholder="Bottom line"
        border="bottomLine"
        options={options}
      />
      <AutoComplete placeholder="None" border="none" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Status
- description: <p>Control the component's state using the <code>status</code> prop. There are 3 states:</p><li><code>error</code> highlights an invalid selection.</li><li><code>warning</code> highlights a value that can't be validated or impacts the user's business.</li><li><code>loading</code> shows that the server is loading the value.</li><p></p><p>Hide the status suffix and indicate the state with a border color by setting <code>hideStatusSuffix</code> to true.</p>
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
      <AutoComplete placeholder="Error" status="error" options={options} />
      <AutoComplete placeholder="Warning" status="warning" options={options} />
      <AutoComplete placeholder="Loading" status="loading" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
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
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For all default cases:</Text>
        <FormField status="error" statusMessage="This is an error message.">
          <AutoComplete
            placeholder="See message below"
            tooltipPlacement="top-end"
            options={options}
          />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For narrow layouts only:</Text>
        <AutoComplete
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
- description: <p>Disable all input interactions with the <code>disabled</code> prop. Use it to highlight unavailable functions.</p>
- example: 
```jsx 
<AutoComplete placeholder="Disabled" disabled />;
```

### Affix
- description: <p>Explain field value with additional information added to <code>prefix</code> and <code>suffix</code>. Props can contain text, icons and even buttons.</p>
- example: 
```jsx 
() => {
  const languageOptions = [
    { id: 0, value: 'English' },
    { id: 1, value: 'French' },
    { id: 2, value: 'Spanish' },
  ];

  const nameOptions = [
    { id: 0, value: 'Jason Sudeikis' },
    { id: 1, value: 'John Krasinski' },
    { id: 2, value: 'Emma Stone' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <AutoComplete
        placeholder="Select language"
        prefix={
          <Input.IconAffix>
            <Icons.Languages />
          </Input.IconAffix>
        }
        options={languageOptions}
      />
      <AutoComplete
        placeholder="Assign a person"
        defaultValue="Emma Stone"
        prefix={
          <Input.Affix>
            <Avatar size="size18"></Avatar>
          </Input.Affix>
        }
        suffix={<Input.Affix>12 April 2015</Input.Affix>}
        options={nameOptions}
      />
    </StorybookComponents.Stack>
  );
};
```

### Clear button
- description: <p>Enable a button that clears the selected value with the <code>clearButton</code> prop. Show it when the field value is optional or often has to be cleared.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Click clear button to remove selection' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ];

  const [value, setValue] = React.useState(options[0].value);

  return (
    <AutoComplete
      placeholder="Select"
      clearButton
      options={options}
      value={value}
      onClear={() => setValue('')}
    />
  );
};
```

### Fixed header and footer
- description: <p>Add a list of related actions to a fixed footer or header area. These areas keep their positions on scroll. </p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ];

  return (
    <AutoComplete
      placeholder="Click to see fixed areas"
      fixedHeader={<ListItemAction title="Fixed Header" />}
      fixedFooter={<ListItemAction title="Fixed Footer" />}
      options={options}
    />
  );
};
```

### List item builders
- description: <p>There are a few props for building custom layouts:</p><li>Group list items into sections with titles using <code>listItemSectionBuilder</code>.</li><li>Add text buttons for related list actions with <code>listItemActionBuilder</code>.</li><li>Build custom options list designs with <code>listItemSelectBuilder</code>.</li>
- example: 
```jsx 
() => {
  const sectionOptions = [
    listItemSectionBuilder({
      id: 0,
      type: 'title',
      title: 'Group title',
    }),
    { id: 1, value: 'Option 1' },
    { id: 2, value: 'Option 2' },
    { id: 3, value: 'Option 3' },
    listItemSectionBuilder({
      id: 3,
      type: 'divider',
    }),
    { id: 4, value: 'Option 4' },
  ];

  const actionOptions = [
    listItemActionBuilder({
      id: 0,
      title: 'Action',
    }),
    { id: 1, value: 'Option 1' },
    { id: 2, value: 'Option 2' },
    { id: 3, value: 'Option 3' },
  ];

  const selectOptions = [
    listItemSelectBuilder({
      id: 0,
      prefix: <Avatar size="size30" />,
      title: 'Title',
      subtitle: 'Subtitle',
      suffix: 'Suffix',
    }),
    listItemSelectBuilder({
      id: 1,
      prefix: <Avatar size="size30" />,
      title: 'Title',
      subtitle: 'Subtitle',
      suffix: 'Suffix',
    }),
    listItemSelectBuilder({
      id: 2,
      prefix: <Avatar size="size30" />,
      title: 'Title',
      subtitle: 'Subtitle',
      suffix: 'Suffix',
    }),
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <AutoComplete placeholder="List item section" options={sectionOptions} />
      <AutoComplete placeholder="List item action" options={actionOptions} />
      <AutoComplete placeholder="List item select" options={selectOptions} />
    </StorybookComponents.Stack>
  );
};
```

### List container dimensions
- description: <p>There are a few ways to control the container size:</p><li>Specify the max height for longer lists with <code>maxHeightPixels</code> prop.</li><li>Set the width to 'auto' or 'max-content' to match the content width or specify it in pixels with <code>dropdownWidth</code> prop.</li><li>Increase the dropdown popover width manually using <code>minWidthPixels</code> prop.</li>
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
    <AutoComplete
      placeholder="Look at proportions"
      maxHeightPixels="200px"
      dropdownWidth="auto"
      minWidthPixels="400px"
      options={options}
      popoverProps={{
        placement: 'bottom-start',
      }}
    />
  );
};
```

### Marked option
- description: <p>Control what to highlight with a hover state when autocomplete dropdown is opened with the <code>markedOption</code> prop.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ];

  return (
    <AutoComplete
      placeholder="Select an option"
      markedOption={1}
      options={options}
    />
  );
};
```

### Infinite scroll
- description: <p>Load items gradually with <code>infiniteScroll</code>, <code>loadMore</code> and <code>hasMore</code> props.</p>
- example: 
```jsx 
() => {
  const [options, setOptions] = React.useState([]);

  const fetchMoreData = () =>
    Promise.resolve(
      fetch(`/api/dropdown?limit=${5}&offset=${options.length}`),
    ).then(results => setOptions([...options, ...results]));

  React.useEffect(() => {
    fetchMoreData();
  }, []);

  return (
    <AutoComplete
      infiniteScroll
      hasMore
      loadMore={fetchMoreData}
      options={options}
      placeholder={'Start typing'}
    />
  );
};
```

### Text overflow
- description: <p>Control text overflow in the input field itself with<code>textOverflow</code>. This allows you to clip the content or add ellipsis.</p><p></p><p>For the dropdown items, the text wraps by default. To add ellipsis, use the <code>listItemSelectBuilder</code> prop.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
  ];

  const optionsLongValue = [
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

  const optionsListBuilder = [
    listItemSelectBuilder({
      id: 0,
      title: 'This is a long value that make dropdown layout grow',
      ellipsis: true,
    }),
    listItemSelectBuilder({
      id: 0,
      title: 'This is a long value that make dropdown layout grow',
      ellipsis: true,
    }),
    listItemSelectBuilder({
      id: 0,
      title: 'This is a long value that make dropdown layout grow',
      ellipsis: true,
    }),
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <StorybookComponents.Stack>
        <FormField label="Input value - ellipsis">
          <AutoComplete
            options={options}
            placeholder="This field is showing ellipsis at the end of this line"
            textOverflow="ellipsis"
          />
        </FormField>
        <FormField label="Input value - clip">
          <AutoComplete
            options={options}
            placeholder="This field is clipping content at the end of this line"
            textOverflow="clip"
          />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack>
        <FormField label="Options - wrapping">
          <AutoComplete
            options={optionsLongValue}
            placeholder="Select option that wraps"
          />
        </FormField>
        <FormField label="Options - with ellipsis">
          <AutoComplete
            options={optionsListBuilder}
            placeholder="Select option that clips"
          />
        </FormField>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Custom lists
- description: <p>To create a custom options layout with avatars, icons, images and more, use the <code>listItemSelectBuilder</code>.</p>
- example: 
```jsx 
() => {
  const [searchValue, setSearchValue] = React.useState('')
  const [selectedId, setSelectedId] = React.useState()

  const options = [
    listItemSectionBuilder({
      title: 'General roles',
    }),
    listItemSelectBuilder({
      id: 0,
      title: 'Website manager',
      label: 'Website manager',
      subtitle:
        'Has access to manage, edit & publish site, but cannot manage billing, delete, duplicate or transfer site.',
    }),
    listItemSelectBuilder({
      id: 1,
      title: 'Website designer',
      label: 'Website designer',
      subtitle:
        'Can edit the site, manage settings and apps but cannot access Inbox, contacts and other sensitive info.',
    }),
    listItemSelectBuilder({
      id: 2,
      title: 'Back office manager',
      label: 'Back office manager',
      subtitle:
        'Can access the Dashboard to manage site settings and apps but cannot edit the site.',
    }),
    listItemSectionBuilder({
      type: 'divider',
    }),
    listItemSectionBuilder({
      title: 'Content manager roles',
    }),
    listItemSelectBuilder({
      id: 3,
      title: 'Content collection manager',
      label: 'Content collection manager',
      subtitle:
        'Can add and modify content for all collections, but cannot edit other areas of your site.',
    }),
    listItemSectionBuilder({
      type: 'divider',
    }),
    listItemSectionBuilder({
      title: 'Blog roles',
    }),
    listItemSelectBuilder({
      id: 4,
      title: 'Blog editor',
      label: 'Blog editor',
      subtitle: 'Can fully manage the blog but not other areas of your site.',
    }),
    listItemSelectBuilder({
      id: 5,
      title: 'Blog writer',
      label: 'Blog writer',
      subtitle:
        'Can write and publish posts. Cannot create or manage categories.',
    }),
    listItemSelectBuilder({
      id: 6,
      title: 'Guest writer',
      label: 'Guest writer',
      subtitle:
        'Can write posts but cannot publish them. Posts must be approved and published by a Blog Editor or site owner.',
    }),
    listItemSectionBuilder({
      type: 'divider',
    }),
    listItemSectionBuilder({
      title: 'Events roles',
    }),
    listItemSelectBuilder({
      id: 7,
      title: 'Events check-in assistant',
      label: 'Events check-in assistant',
      subtitle:
        'Can see the guest list, check-in guests and scan tickets on the Wix Owner App.',
    }),
  ]

  function includesCaseInsensitive(a = '', b = '') {
    return !b || a.toLowerCase().indexOf(b.toLowerCase()) !== -1
  }

  return (
    <FormField label="Role">
      <AutoComplete
        placeholder="Select"
        maxHeightPixels="300px"
        options={options}
        selectedId={selectedId}
        value={searchValue}
        onSelect={(option) => {
          setSelectedId(option.id)
          setSearchValue(option.label)
        }}
        onChange={(event) => setSearchValue(event.target.value)}
        predicate={(option) =>
          includesCaseInsensitive(option.label, searchValue.trim())
        }
      />
    </FormField>
  )
}

```


