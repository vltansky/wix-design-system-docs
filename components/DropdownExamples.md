
## Feature Examples


### Size
- description: <p>Adjust the component size using the size prop.</p><li><code>large</code> emphasize fields in onboarding flows.</li><li><code>medium</code> is the default size used in most cases.</li><li><code>small</code> should be used in dense layouts.</li>
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
      <Dropdown size="large" placeholder="Large" options={options} />
      <Dropdown size="medium" placeholder="Medium" options={options} />
      <Dropdown size="small" placeholder="Small" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Border
- description: <p>Style the component using the border prop which supports four styles:</p><li>For forms, use <code>standard</code>.</li><li>When the component is used to filter, use <code>round</code>.</li><li>For titles that can be edited on click, use <code>bottomLine</code>.</li><li>In the Content Manager’s spreadsheet, use <code>none</code>.</li>
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
      <Dropdown border="standard" placeholder="Standard" options={options} />
      <Dropdown border="round" placeholder="Round" options={options} />
      <Dropdown
        border="bottomLine"
        placeholder="Bottom Line"
        options={options}
      />
      <Dropdown border="none" placeholder="None" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Status
- description: <p>Use the <code>status</code> prop to control component status. </p><li><code>error</code> highlights an invalid selection.</li><li><code>warning</code> highlights a value that can’t be validated or impacts a user’s business.</li><li><code>loading</code> shows that the value is loading.</li><p></p><p>Hide the status suffix and indicate the state with a border color by setting <code>hideStatusSuffix</code>to true. </p>
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
      <Dropdown status="error" placeholder="Error" options={options} />
      <Dropdown status="warning" placeholder="Warning" options={options} />
      <Dropdown status="loading" placeholder="Loading" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the dropdown is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
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
          <Dropdown
            placeholder="See message below"
            tooltipPlacement="top-end"
            options={options}
          />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For narrow layouts only:</Text>
        <Dropdown
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
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ];
  return <Dropdown disabled placeholder="Disabled" options={options} />;
};
```

### Affix
- description: <p>Add additional information to <code>prefix</code> and <code>suffix</code> props (e.g. text, icons, buttons) to support the dropdown value.</p>
- example: 
```jsx 
() => {
  const discountSuffixOptions = [
    { id: 0, value: '5' },
    { id: 1, value: '10' },
    { id: 2, value: '15' },
  ];
  const discountAffixOptions = [
    { id: 0, value: '10' },
    { id: 1, value: '20' },
    { id: 2, value: '30' },
  ];
  const languageOptions = [
    { id: 0, value: 'English' },
    { id: 1, value: 'French' },
    { id: 2, value: 'Spanish' },
  ];
  const employeeOptions = [
    { id: 0, value: 'Employee 1' },
    { id: 1, value: 'Employee 2' },
    { id: 2, value: 'Employee 3' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Dropdown
        placeholder="Select discount size"
        suffix={<Input.Affix>%</Input.Affix>}
        options={discountSuffixOptions}
      />
      <Dropdown
        placeholder="Select discount size"
        prefix={<Input.Affix>$</Input.Affix>}
        options={discountAffixOptions}
      />
      <Dropdown
        placeholder="Select language"
        prefix={
          <Input.IconAffix>
            <Icons.Languages />
          </Input.IconAffix>
        }
        options={languageOptions}
      />
      <Dropdown
        placeholder="Select employee"
        prefix={
          <Input.Affix>
            <Avatar size="size18" />
          </Input.Affix>
        }
        options={employeeOptions}
      />
    </StorybookComponents.Stack>
  );
};
```

### Clear button
- description: <p>Enable a button that clears the dropdown value by using the <code>clearButton</code> prop. Show it when the field value is optional or has to be cleared often.</p>
- example: 
```jsx 
() => {
  const [selectedOption, setSelectedOption] = React.useState(0);
  const options = [
    { id: 0, value: 'Click clear button to remove selection' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ];

  return (
    <Dropdown
      placeholder="Select"
      clearButton
      onClear={() => setSelectedOption(null)}
      onSelect={option => setSelectedOption(option.id)}
      selectedId={selectedOption}
      options={options}
    />
  );
};
```

### Fixed header and footer
- description: <p>Add related actions to <code>fixedFooter</code> or <code>fixedHeader</code> areas. These headers and footers keep their position on scroll.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 1, value: 'Option 1' },
    { id: 2, value: 'Option 2' },
    { id: 3, value: 'Option 3' },
    { id: 4, value: 'Option 4' },
    { id: 5, value: 'Option 5' },
    { id: 6, value: 'Option 6' },
    { id: 7, value: 'Option 7' },
    { id: 8, value: 'Option 8' },
    { id: 9, value: 'Option 9' },
  ];
  return (
    <Dropdown
      placeholder="Select"
      fixedHeader={<ListItemAction title="Fixed Header" />}
      fixedFooter={<ListItemAction title="Fixed Footer" />}
      options={options}
    />
  );
};
```

### List item builders
- description: <p>Use three props to build custom layouts:</p><li><code>listItemSectionBuilder</code> groups items into sections by type.  <a href="https://www.wix-style-react.com/storybook/?path=/story/components-form-dropdownlistitems--listitemsection"></a></li><li><code>listItemActionBuilder</code> adds a text button for related list actions.  <a href="https://www.wix-style-react.com/storybook/?path=/story/components-form-dropdownlistitems--listitemaction"></a></li><li><code>listItemSelectBuilder</code> builds custom list designs. <a href="https://www.wix-style-react.com/storybook/?path=/story/components-form-dropdownlistitems--listitemselect"></a></li>
- example: 
```jsx 
() => {
  const listItemSectionOptions = [
    listItemSectionBuilder({
      id: 0,
      type: 'title',
      title: 'Group Title',
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

  const listItemActionOptions = [
    listItemActionBuilder({
      id: 0,
      title: 'Action',
    }),
    { id: 1, value: 'Option 1' },
    { id: 2, value: 'Option 2' },
    { id: 3, value: 'Option 3' },
  ];

  const listItemSelectOptions = [
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
      <Dropdown
        placeholder="List Item Section"
        options={listItemSectionOptions}
      />
      <Dropdown
        placeholder="List Item Action"
        options={listItemActionOptions}
      />
      <Dropdown
        placeholder="List Item Select"
        options={listItemSelectOptions}
      />
    </StorybookComponents.Stack>
  );
};
```

### List container dimensions
- description: <p>Control the container size for the list of options with these props:</p><li><code>maxHeightPixels</code> specifies the maximum height for longer lists.</li><li><code>dropdownWidth</code> matches content width or specifies pixels. Set width to ‘auto’ or ‘max-content.’</li><li><code>minWidthPixels</code> manually increases dropdown popover width.</li><p></p><p>By default, the dropdown matches the input field width.</p>
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
      <Dropdown
        placeholder="Look at proportions"
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
- description: <p>Once the dropdown is opened, use the <code>markedOption</code> to highlight the option.</p>
- example: 
```jsx 
<Dropdown
  placeholder="Select an option"
  markedOption={1}
  options={[
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
  ]}
/>;
```

### Native support
- description: <p>Switch to <code>native</code> support for mobile usage. Avoid using it for desktop applications.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
  ];
  return <Dropdown options={options} placeholder="Select as native" native />;
};
```

### Text overflow
- description: <p>Control text overflow in the field with the <code>textOverflow</code>. Apply <code>clip</code> or <code>ellipsis</code>.</p><p></p><p>Dropdown list options wrap by default. To apply ellipsis, select the items to be displayed with the <code>listItemSelectBuilder</code>. This isn't recommended.</p>
- example: 
```jsx 
() => {
  const options = [
    { id: 0, value: 'Option 1' },
    { id: 1, value: 'Option 2' },
    { id: 2, value: 'Option 3' },
    { id: 3, value: 'Option 4' },
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
        <FormField label="Input value with ellipsis::">
          <Dropdown
            options={options}
            placeholder="This field is showing ellipsis at the end of this line"
            textOverflow="ellipsis"
          />
        </FormField>
        <FormField label="Input value clipped:">
          <Dropdown
            options={options}
            placeholder="This field is clipping content at the end of this line"
            textOverflow="clip"
          />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack>
        <FormField label="Options wrapped:">
          <Dropdown
            options={longOptions}
            placeholder="Select wrapped option"
          />
        </FormField>
        <FormField label="Options with ellipsis:">
          <Dropdown
            options={longOptionsWithEllipsis}
            placeholder="Select clipped option"
          />
        </FormField>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```




## Developer Examples


### Lazy loading
- description: <p>Gradually load items with <code>infiniteScroll</code>, <code>loadMore</code> and <code>hasMore</code> props.</p>
- example: 
```jsx 
() => {
  const [data, setData] = React.useState([]);
  const fetchMoreData = () =>
    Promise.resolve(
      fetch(`/api/dropdown?limit=${5}&offset=${data.length}`),
    ).then(results => setData([...data, ...results]));

  React.useEffect(() => {
    fetchMoreData();
  }, []);

  return (
    <Dropdown
      placeholder="Select"
      options={data}
      infiniteScroll
      hasMore={true}
      loadMore={fetchMoreData}
    />
  );
};
```

### Controlled
- description: <p>Component can be used in controlled mode by passing <code>selectedId</code> and <code>onSelect</code> props.</p>
- example: 
```jsx 
() => {
  const [selectedId, setSelected] = React.useState(0);

  const options = [
    listItemSelectBuilder({
      id: 0,
      prefix: (
        <Box>
          <Icons.Home />
        </Box>
      ),
      title: 'Home address',
      label: 'Home address',
    }),
    listItemSelectBuilder({
      id: 1,
      title: 'Work address',
      label: 'Work address',
      prefix: (
        <Box>
          <Icons.Toolbox />
        </Box>
      ),
    }),
    listItemSelectBuilder({
      id: 2,
      title: 'Mailing address',
      label: 'Mailing address',
      prefix: (
        <Box>
          <Icons.Email />
        </Box>
      ),
    }),
    listItemSelectBuilder({
      id: 3,
      title: 'Shipping address',
      label: 'Shipping address',
      prefix: (
        <Box>
          <Icons.Archive />
        </Box>
      ),
    }),
    listItemSelectBuilder({
      id: 4,
      title: 'Other',
      label: 'Other',
      prefix: (
        <Box>
          <Icons.Category />
        </Box>
      ),
    }),
  ];

  return (
    <Dropdown
      placeholder="Select"
      selectedId={selectedId}
      valueParser={(option) => option.label}
      onSelect={(e) => setSelected(e.id)}
      options={options}
    />
  );
};
```


    


## Common Use Case Examples


### Settings panel
- description: <p>Use dropdown to let users select a single item from a predefined list of options in a settings panel.</p>
- example: 
```jsx 
() => {
  const [selectedOption, setSelectedOption] = React.useState(0);
  const [value, setValue] = React.useState(2);

  const options = [
    { id: 0, value: 'Image' },
    { id: 1, value: 'Video' },
    { id: 2, value: 'Image and video' },
    { id: 3, value: 'Document' },
    { id: 4, value: 'Audio' },
  ];
  return (
    <SidePanel maxHeight="576px" width="288px" skin="floating">
      <SidePanel.Header title="Upload Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Supported file type">
            <Dropdown
              placeholder="Select"
              size="small"
              options={options}
              onSelect={(option) => setSelectedOption(option.id)}
              selectedId={selectedOption}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            gap="small"
            legend="Max number of files"
            columns="auto 60px"
          >
            <Slider
              onChange={setValue}
              min={0}
              max={10}
              value={value}
              displayMarks={false}
            />
            <Input
              size="small"
              value={value}
              onChange={(e) => setValue(e.target.value)}
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="This field is">
            <Checkbox size="small" checked>
              Required
            </Checkbox>
          </FormField>
        </SidePanel.Field>
        <SidePanel.Section title="Display settings">
          <SidePanel.Field>
            <FormField label="Field title">
              <Input size="small" placeholder="Enter field title"/>
            </FormField>
          </SidePanel.Field>
          <SidePanel.Field>
            <FormField label="Button text">
              <Input size="small" value="Choose file"/>
            </FormField>
          </SidePanel.Field>
        </SidePanel.Section>
      </SidePanel.Content>
    </SidePanel>
  );
};
```

### Prefix icon
- description: <p>Use <code>listItemSelectBuilder</code> to create custom layouts for options in the dropdown. For example, use  avatars, icons or images as prefix icons.</p>
- example: 
```jsx 
() => {
  const options = [
    listItemSelectBuilder({
      id: 0,
      prefix: (
        <Box>
          <Icons.Home />
        </Box>
      ),
      title: 'Home address',
      label: 'Home address',
    }),
    listItemSelectBuilder({
      id: 1,
      title: 'Work address',
      label: 'Work address',
      prefix: (
        <Box>
          <Icons.Toolbox />
        </Box>
      ),
    }),
    listItemSelectBuilder({
      id: 2,
      title: 'Mailing address',
      label: 'Mailing address',
      prefix: (
        <Box>
          <Icons.Email />
        </Box>
      ),
    }),
    listItemSelectBuilder({
      id: 3,
      title: 'Shipping address',
      label: 'Shipping address',
      prefix: (
        <Box>
          <Icons.Archive />
        </Box>
      ),
    }),
    listItemSelectBuilder({
      id: 4,
      title: 'Other',
      label: 'Other',
      prefix: (
        <Box>
          <Icons.Category />
        </Box>
      ),
    }),
  ];

  return (
    <FormField label="Address type">
      <Dropdown
        placeholder="Select"
        valueParser={option => option.label}
        options={options}
      />
    </FormField>
  );
};
```

### Grouping
- description: <p>Use <code>listItemSectionBuilder</code> within the drop down to group options into categories.</p>
- example: 
```jsx 
<Layout>
  <Cell span={12}>
    <FormField label="Product">
      <Dropdown
        placeholder="Select"
        options={[
          listItemSectionBuilder({
            title: 'Most popular',
          }),
          { id: 1, value: 'Wix Stores' },
          { id: 2, value: 'Wix Bookings' },
          { id: 3, value: 'Wix Blog' },
          listItemSectionBuilder({
            title: 'Other',
          }),
          { id: 4, value: 'Wix Events' },
          { id: 5, value: 'Wix Forum' },
          { id: 6, value: 'Wix Restaurants' },
        ]}
      />
    </FormField>
  </Cell>
  <Cell span={12}>
    <FormField label="Role">
      <Dropdown
        placeholder="Select"
        options={[
          listItemSectionBuilder({
            title: 'General',
            type: 'subheader',
            suffix: 'Edit',
          }),
          { id: 0, value: 'Website manager' },
          { id: 1, value: 'Website designer' },
          { id: 2, value: 'Back office manager' },
          listItemSectionBuilder({
            title: 'Content manager roles',
            type: 'subheader',
            suffix: 'Edit',
          }),
          { id: 3, value: 'Content collection manager' },
          listItemSectionBuilder({
            title: 'Blog roles',
            type: 'subheader',
            suffix: 'Edit',
          }),
          { id: 4, value: 'Blog editor' },
          { id: 5, value: 'Blog writer' },
          { id: 6, value: 'Guest writer' },
          listItemSectionBuilder({
            title: 'Booking roles',
            type: 'subheader',
            suffix: 'Edit',
          }),
          { id: 7, value: 'Bookings admin' },
          { id: 8, value: 'Bookings staff member' },
        ]}
      />
    </FormField>
  </Cell>
</Layout>;
```


