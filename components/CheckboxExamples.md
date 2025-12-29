
## Feature Examples


### Size
- description: <p>Adjust the component size using the <code>size</code> prop. It supports 2 sizes:</p><li><code>medium</code> (default) - use in all common cases</li><li><code>small</code> - use in more dense layouts</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Checkbox size="medium">Medium</Checkbox>
  <Checkbox size="small">Small</Checkbox>
</StorybookComponents.Stack>;
```

### State
- description: <p>A checkbox can exist in multiple states:</p><li>In the <code>default</code> state, the checkbox is empty and the user is able to select it.</li><li><code>checked</code> - the selected item is marked.</li><li><code>indeterminate</code> - represent a mixed value for bulk selection checkbox (both selected and not selected values included).</li><li><code>disabled</code> - highlight that a selection exists but it’s not available at that time.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Checkbox>Default</Checkbox>
  <Checkbox checked>Checked</Checkbox>
  <Checkbox indeterminate>Indeterminate</Checkbox>
  <Checkbox disabled>Disabled</Checkbox>
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the checkboxes by wrapping them in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<FormField status="error" statusMessage="This is an error message.">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Checkbox>Option 1</Checkbox>
    <Checkbox>Option 2</Checkbox>
  </StorybookComponents.Stack>
</FormField>;
```

### Vertical alignment
- description: <p>Control checkbox alignment with a label using the <code>vAlign</code> prop. It supports 2 values:</p><li><code>center</code> (default) - use it in all common cases</li><li><code>top</code> - use it to align the checkbox to the top to handle text overflow</li>
- example: 
```jsx 
<StorybookComponents.Stack width="300px" flexDirection="column" >
  <Checkbox vAlign="center">Checkbox label that wraps to multiple lines (center)</Checkbox>
  <Checkbox vAlign="top">Checkbox label that wraps to multiple lines (top)</Checkbox>
</StorybookComponents.Stack>;
```

### Selection area
- description: <p>Emphasize the clickable space with a selection area. Control the style with:</p><li><code>selectionArea</code> - to specify whether to display an area on hover, always or not display it at all</li><li><code>selectionAreaSkin</code> - to specify which design to use: filled or outline</li><li><code>selectionAreaPadding</code> - to define white space around the checkbox in pixels</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" width="50%">
    <Checkbox
      selectionArea="always"
      selectionAreaSkin="outlined"
      selectionAreaPadding="12px 18px"
      checked
    >
      Option 1
    </Checkbox>
    <Checkbox
      selectionArea="always"
      selectionAreaSkin="outlined"
      selectionAreaPadding="12px 18px"
    >
      Option 2
    </Checkbox>
    <Checkbox
      selectionArea="always"
      selectionAreaSkin="outlined"
      selectionAreaPadding="12px 18px"
    >
      Option 3
    </Checkbox>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" width="50%">
    <Checkbox
      selectionArea="hover"
      selectionAreaSkin="filled"
      selectionAreaPadding="12px 18px"
      checked
    >
      Option 1
    </Checkbox>
    <Checkbox
      selectionArea="hover"
      selectionAreaSkin="filled"
      selectionAreaPadding="12px 18px"
    >
      Option 2
    </Checkbox>
    <Checkbox
      selectionArea="hover"
      selectionAreaSkin="filled"
      selectionAreaPadding="12px 18px"
    >
      Option 3
    </Checkbox>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Max lines
- description: <p>Use <code>maxLines</code> prop to limit the amount of lines and show ellipsis.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="300px" flexDirection="column">
  <Checkbox>
    Checkbox label that wraps to multiple lines
  </Checkbox>
  <Checkbox ellipsis={true} maxLines="1">
    Checkbox label that has max lines applied
  </Checkbox>
</StorybookComponents.Stack>;
```

### Tooltip
- description: <p>Use a tooltip to give added explanation for the checkbox. Use the <code>tooltipContent</code> prop, and control the design with <code>tooltipProps</code> (it accepts all standard <code><Tooltip/></code> properties).</p>
- example: 
```jsx 
<Checkbox
  tooltipContent="Message explaining the select option"
  tooltipProps={{
    placement: 'top-start',
    textAlign: 'start',
  }}
>
  Hover the mouse on a checkbox to see a tooltip
</Checkbox>;
```




    


## Common Use Case Examples


### Forms
- description: <p>Use checkboxes in a form to display all available options.</p>
- example: 
```jsx 
() => {
  const checkboxes = [
    {
      id: 'newArrivals',
      label: 'New Arrivals',
      initialState: true,
    },
    {
      id: 'womensClothing',
      label: "Women's clothing",
      initialState: true,
    },
    {
      id: 'mensClothing',
      label: "Men's clothing",
      initialState: false,
    },
    {
      id: 'kids',
      label: 'Kids',
      initialState: false,
    },
    {
      id: 'home',
      label: 'Home',
      initialState: false,
    },
  ];

  const [checkboxesList, setCheckboxesList] = React.useState(checkboxes);

  const isAllSelected = !checkboxesList
    .map(item => item.isChecked)
    .includes(false);

  const isAllDeselected = !checkboxesList
    .map(item => item.isChecked)
    .includes(true);

  const toggleCheckedAll = checked => {
    setCheckboxesList(
      checkboxesList.map(item => ({ ...item, isChecked: checked })),
    );
  };

  const renderCheckboxes = () =>
    checkboxesList.map(item => {
      const [checked, setChecked] = React.useState(item.initialState);
      return (
        <Checkbox
          id={item.id}
          checked={item.isChecked}
          onChange={() => setChecked(!checked)}
        >
          {item.label}
        </Checkbox>
      );
    });

  return (
    <Layout>
      <Cell span={6}>
        <Card>
          <Card.Header
            title="Collections"
            subtitle="Assign products to a collection"
          />
          <Card.Divider />
          <Card.Content>
            <Box direction="vertical" gap="12px">
              <Checkbox
                checked={isAllSelected || (!isAllSelected && !isAllDeselected)}
                onChange={() => {
                  isAllSelected
                    ? toggleCheckedAll(false)
                    : toggleCheckedAll(true);
                }}
                disabled={!isAllSelected && !isAllDeselected}
              >
                All products
              </Checkbox>
              {renderCheckboxes()}
              <TextButton prefixIcon={<Icons.Add />}>
                Create Collection
              </TextButton>
            </Box>
          </Card.Content>
        </Card>
      </Cell>
    </Layout>
  );
};
```

### With a label
- description: <p>Use any component for checkbox labels, make sure that they are either textual components or self-explanatory within the given context.</p>
- example: 
```jsx 
() => {
  const checkboxes = [
    {
      id: 'members',
      label: 'Members',
      description: 'All registered users',
      initialState: true,
    },
    {
      id: 'roles',
      label: 'Roles',
      description: 'Users who are assigned to a special role',
      initialState: false,
    },
    {
      id: 'badges',
      label: 'Badges',
      description: 'Users who have selected badges',
      initialState: false,
    },
  ];

  const getCheckboxLabel = item => (
    <Box direction="vertical">
      <Text weight="bold">{item.label}</Text>
      <Text size="small" secondary>
        {item.description}
      </Text>
    </Box>
  );

  const renderCheckboxes = () => {
    return checkboxes.map(item => {
      const [checked, setChecked] = React.useState(item.initialState);

      return (
        <Checkbox
          checked={checked}
          onChange={() => setChecked(!checked)}
          selectionArea="hover"
          id={item.id}
        >
          {getCheckboxLabel(item)}
        </Checkbox>
      );
    });
  };

  return (
    <Card>
      <Card.Header title="Permissions" />
      <Card.Divider />
      <Card.Content>
        <Box direction="vertical">
          <FormField label="Who can access this category?">
            <Box direction="vertical" gap="12px">
              {renderCheckboxes()}
            </Box>
          </FormField>
        </Box>
      </Card.Content>
    </Card>
  );
};
```

### Manage panel
- description: <p>Use checkboxes to manage which elements of an app are visible on your site.</p>
- example: 
```jsx 
<SidePanel
  onCloseButtonClick={() => {}}
  skin="floating"
  width="288px"
  height="576px"
>
  <SidePanel.Header title="Widget Elements" />
  <SidePanel.Content noPadding>
    <SidePanel.Field divider={false}>
      <Text size="small" secondary>
        Choose which elements to display on Post Header
      </Text>
    </SidePanel.Field>
    <SidePanel.Field divider={false}>
      <FieldSet legend="Main elements" direction="vertical">
        <Checkbox checked size="small">
          Categories
        </Checkbox>
        <Checkbox checked size="small">
          Title
        </Checkbox>
        <Checkbox checked size="small">
          Ratings
        </Checkbox>
        <Checkbox checked size="small">
          Tags
        </Checkbox>
        <Checkbox checked size="small">
          Writers
        </Checkbox>
        <Checkbox checked size="small">
          Counters
        </Checkbox>
      </FieldSet>
    </SidePanel.Field>
    <SidePanel.Field divider={false}>
      <Divider />
    </SidePanel.Field>
    <SidePanel.Field divider={false}>
      <FieldSet legend="Metadata" direction="vertical">
        <Checkbox checked size="small">
          Categories
        </Checkbox>
        <Checkbox checked size="small">
          Writer
        </Checkbox>
        <Checkbox checked size="small">
          Publish date
        </Checkbox>
        <Checkbox checked size="small">
          Reading time
        </Checkbox>
        <Checkbox checked size="small">
          Last updated
        </Checkbox>
      </FieldSet>
    </SidePanel.Field>
    <SidePanel.Field divider={false}>
      <Divider />
    </SidePanel.Field>
    <SidePanel.Field divider={false}>
      <FieldSet legend="Counters" direction="vertical">
        <Checkbox checked size="small">
          Likes
        </Checkbox>
        <Checkbox checked size="small">
          Views
        </Checkbox>
        <Checkbox checked size="small">
          Comments
        </Checkbox>
      </FieldSet>
    </SidePanel.Field>
  </SidePanel.Content>
</SidePanel>;
```


