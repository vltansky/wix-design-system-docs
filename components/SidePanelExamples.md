
## Feature Examples


### Structure
- description: <p>Side panels are composed of up to four compound components:   </p><li><code><SidePanel.Header/></code></li><li><code><SidePanel.Content/></code></li><li><code><SidePanel.Divider/></code></li><li><code><SidePanel.Footer/></code></li><p></p><p>All of these components are optional.</p>
- example: 
```jsx 
<SidePanel onCloseButtonClick={() => {}}>
  <SidePanel.Header title="Header" />
  <SidePanel.Content>
    <StorybookComponents.Placeholder height="480px">
      Content
    </StorybookComponents.Placeholder>
  </SidePanel.Content>
  <SidePanel.Footer>
    <StorybookComponents.Placeholder height="36px" >
      Footer
    </StorybookComponents.Placeholder>
  </SidePanel.Footer>
</SidePanel>;
```

### Skin
- description: <p>Control the component style with <code>skin</code> prop:</p><li><code>standard</code> is the default style used in all common cases.</li><li><code>floating</code> is used for settings panels that float on top of content in editor platforms (<a href="https://www.wix.com/">Wix</a> or <a href="https://www.wix.com/studio">Wix Studio</a>). </li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="Standard" />
    <SidePanel.Content>
      <StorybookComponents.Stack height="480px" />
    </SidePanel.Content>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px">
    <SidePanel.Header title="Floating" />
    <SidePanel.Content>
      <StorybookComponents.Stack height="492px" />
    </SidePanel.Content>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Width
- description: <p>Set the side panel’s width using the <code>width</code> property. The default width is 420px.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidePanel onCloseButtonClick={() => {}} width="300px">
    <SidePanel.Header title="Narrow panel" />
    <SidePanel.Content>
      <StorybookComponents.Stack height="360px" />
    </SidePanel.Content>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}} width="600px">
    <SidePanel.Header title="Wide panel" />
    <SidePanel.Content>
      <StorybookComponents.Stack height="360px" />
    </SidePanel.Content>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Height
- description: <p>By default, panel height depends on the amount of content it contains. To define the maximum height it can grow to use <code>maxHeight</code> property.</p><p></p><p>Fix the panel height to a specific number with <code>height</code> property. </p><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidePanel onCloseButtonClick={() => {}} maxHeight="480px">
    <SidePanel.Header title="No height set" />
    <SidePanel.Content>
      <StorybookComponents.Placeholder height="40px" />
    </SidePanel.Content>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}} height="480px">
    <SidePanel.Header title="Fixed height set" />
    <SidePanel.Content>
      <StorybookComponents.Placeholder height="40px" />
    </SidePanel.Content>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Padding
- description: <p>Content padding is enabled in the side panel by default, but can be disabled  with the <code>noPadding</code> property for:</p><li><code><SidePanel.Content/></code></li><li><code><SidePanel.Footer/></code></li><p></p><p>The padding can be removed to display lists or other components with built-in padding.</p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="With padding" />
    <SidePanel.Content>
      <StorybookComponents.Placeholder height="360px" />
    </SidePanel.Content>
    <SidePanel.Footer>
      <StorybookComponents.Placeholder height="42px" />
    </SidePanel.Footer>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="No padding" />
    <SidePanel.Content noPadding={true}>
      <StorybookComponents.Placeholder height="360px" />
    </SidePanel.Content>
    <SidePanel.Footer noPadding={true}>
      <StorybookComponents.Placeholder height="42px" />
    </SidePanel.Footer>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Dividers
- description: <p>Dividers are enabled in the side panel by default but can be disabled using the <code>showDivider</code> property for:</p><li><code><SidePanel.Header/></code></li><li><code><SidePanel.Footer/></code></li><p></p><p>Always show dividers in the side panel if users have the option to scroll vertically inside the panel.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="With divider" />
    <SidePanel.Content>
      <StorybookComponents.Stack height="360px" />
    </SidePanel.Content>
    <SidePanel.Footer>
      <StorybookComponents.Stack height="42px" />
    </SidePanel.Footer>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="No divider" showDivider={false} />
    <SidePanel.Content>
      <StorybookComponents.Stack height="360px" />
    </SidePanel.Content>
    <SidePanel.Footer showDivider={false}>
      <StorybookComponents.Stack height="42px" />
    </SidePanel.Footer>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Header
- description: <p>Customize the side panel’s header using these properties:</p><li><code>title</code> </li><li><code>subtitle </code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="Title" showDivider={true} />
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="Title" subtitle="Subtitle" showDivider={true} />
  </SidePanel>
</StorybookComponents.Stack>;
```

### Header Actions
- description: <p>Header has these properties for actions available:</p><li><code>infoTooltipContent</code> - provides additional details or an explanation in a tooltip</li><li><code>onHelpButtonClick</code>- allows users to access help articles and contextual information</li><li><code>onBackButtonClick</code>- allows users to navigate back in the Side Panel</li><li><code>backButtonDescription</code> - sets content of the back button's tooltip</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header
      title="Title"
      subtitle="Subtitle"
      infoTooltipContent="Additional info here"
      showDivider={true}
    />
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}} onHelpButtonClick={() => {}}>
    <SidePanel.Header title="Title" subtitle="Subtitle" showDivider={true} />
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}} onBackButtonClick={() => {}} backButtonDescription="Back">
    <SidePanel.Header
      title="Title"
      subtitle="Subtitle"
      showDivider={true}
    />
  </SidePanel>
</StorybookComponents.Stack>;
```

### Custom header
- description: <p>Create a custom header layout by adding children elements to the <code><SidePanel.Header/></code> container.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="Title">
      <StorybookComponents.Stack margin="0px 24px 12px 24px">
        <StorybookComponents.Placeholder height="42px" />
      </StorybookComponents.Stack>
    </SidePanel.Header>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="Title" showDivider={false}>
      <Tabs
        items={[
          { id: 1, title: 'First Tab' },
          { id: 2, title: 'Second Tab' },
        ]}
        activeId={1}
        type="uniformSide"
        width="174px"
      />
    </SidePanel.Header>
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header title="Title">
      <StorybookComponents.Stack margin="0px 24px 12px 24px">
        <Search />
      </StorybookComponents.Stack>
    </SidePanel.Header>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Text overflow
- description: <p>Panel title and subtitle wraps to multiple lines by default. Limit the amount of lines using <code>ellipsis</code> and <code>maxLines</code> properties.</p><p></p><p>Ellipsis do not apply to the subtitle, as its main purpose is to provide more information. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header
      title="A long title that needs to wrap into multiple lines"
      subtitle="A long subtitle that needs to wrap into multiple lines because it is so long."
      showDivider={true}
    />
  </SidePanel>
  <SidePanel onCloseButtonClick={() => {}}>
    <SidePanel.Header
      ellipsis
      maxLines={1}
      title="A long title that needs to wrap into multiple lines"
      subtitle="A long subtitle that needs to wrap into multiple lines because it is so long."
      showDivider={true}
    />
  </SidePanel>
</StorybookComponents.Stack>;
```

### Content sections
- description: <p>Create sections inside of a panel by adding multiple <code><SidePanel.Content/></code> areas.</p><p></p><p>Separate them from one another with a dedicated <code><SidePanel.Divider/></code> element. </p>
- example: 
```jsx 
<SidePanel onCloseButtonClick={() => {}}>
  <SidePanel.Header title="Content sections" />
  <SidePanel.Content>
    <StorybookComponents.Stack height="150px" />
  </SidePanel.Content>
  <SidePanel.Divider />
  <SidePanel.Content>
    <StorybookComponents.Stack height="150px" />
  </SidePanel.Content>
  <SidePanel.Divider />
  <SidePanel.Content>
    <StorybookComponents.Stack height="150px" />
  </SidePanel.Content>
</SidePanel>;
```

### Content fields
- description: <p>Separate controls inside of a panel from one another by wrapping each one into <code><SidePanel.Field/></code> container.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
<SidePanel onCloseButtonClick={() => {}}>
  <SidePanel.Header title="Content fields" />
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
</SidePanel>
<SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px">
  <SidePanel.Header title="Content fields" />
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
  <SidePanel.Field>
    <StorybookComponents.Placeholder height="48px" />
  </SidePanel.Field>
</SidePanel>
</StorybookComponents.Stack>
```

### Custom footer
- description: <p>To display confirmation or close actions use the <code><SidePanel.Footer/></code> container.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidePanel>
    <SidePanel.Footer>
      <StorybookComponents.Placeholder height="36px" />
    </SidePanel.Footer>
  </SidePanel>
  <SidePanel>
    <SidePanel.Footer>
      <Button priority="secondary" fullWidth>
        Close
      </Button>
    </SidePanel.Footer>
  </SidePanel>
  <SidePanel>
    <SidePanel.Footer>
      <StorybookComponents.Stack justifyContent="flex-end" gap="12px">
        <Button priority="secondary">Cancel</Button>
        <Button>Save</Button>
      </StorybookComponents.Stack>
    </SidePanel.Footer>
  </SidePanel>
</StorybookComponents.Stack>;
```

### Draggable
- description: <p>Let users know that panel position on the screen can be changed by changing the mouse cursor to grab with <code>draggable</code> property.</p><p></p><p>The behaviour itself has to be developed separately.</p>
- example: 
```jsx 
 <SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px" draggable>
    <SidePanel.Header title="Draggable panel"/>
    <SidePanel.Content>
      <StorybookComponents.Stack height="492px" />
    </SidePanel.Content>
  </SidePanel>
```




    


## Common Use Case Examples


### Settings panel
- description: <p>Use side panel to create settings panels that allow users to control the design and behavior aspects of their app.</p>
- example: 
```jsx 
<SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px">
  <SidePanel.Header title="Button Settings" />
  <SidePanel.Field>
    <FormField label="Choose what displays">
      <Dropdown
        size="small"
        selectedId={0}
        options={[
          { id: 0, value: 'Text and icon' },
          { id: 1, value: 'Icon only' },
          { id: 2, value: 'Text only' },
          { id: 3, value: 'Nothing' },
        ]}
      />
    </FormField>
  </SidePanel.Field>
  <SidePanel.Field>
    <FormField label="Text">
      <Input size="small" value="New Folder" />
    </FormField>
  </SidePanel.Field>
  <SidePanel.Field>
    <FieldSet
      legend="Icon"
      columns="auto 30px 30px"
      gap="small"
      alignment="center"
    >
      <ImageViewer height="102px" width="160px" />
      <IconButton size="small" priority="secondary">
        <Icons.ReplaceSmall />
      </IconButton>
      <IconButton size="small" priority="secondary">
        <Icons.DeleteSmall />
      </IconButton>
    </FieldSet>
  </SidePanel.Field>
  <SidePanel.Field>
    <FormField label="Links to">
      <Button
        size="small"
        priority="secondary"
        fullWidth
        suffixIcon={<Icons.LinkSmall />}
      >
        Choose a link
      </Button>
    </FormField>
  </SidePanel.Field>
</SidePanel>;
```

### Group content in settings panels
- description: <p>Use <code><SidePanel.Section/></code> wrapper to organize panel info into categories.</p><p></p><p>It will make the whole panel easier to scan.</p>
- example: 
```jsx 
() => {
  const [selectedOption, setSelectedOption] = React.useState(0)
  const options = [
    { id: 0, value: 'Monday' },
    { id: 1, value: 'Sunday' },
  ]
  return (
    <SidePanel
      maxHeight="576px"
      width="288px"
      skin="floating"
      onCloseButtonClick={() => {}}
    >
      <SidePanel.Header title="Calendar Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Week starts on">
            <Dropdown
              value=""
              size="small"
              options={options}
              onSelect={(option) => setSelectedOption(option.id)}
              selectedId={selectedOption}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            legend="Set active days"
            legendSize="small"
            legendPlacement="top"
            direction="vertical"
            gap="12px"
          >
            <Checkbox size="small" checked>
              Monday
            </Checkbox>
            <Checkbox size="small" checked>
              Tuesday
            </Checkbox>
            <Checkbox size="small" checked>
              Wednesday
            </Checkbox>
            <Checkbox size="small" checked>
              Thursday
            </Checkbox>
            <Checkbox size="small" checked>
              Friday
            </Checkbox>
            <Checkbox size="small">Saturday</Checkbox>
            <Checkbox size="small">Sunday</Checkbox>
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Section title="Available dates">
          <SidePanel.Field>
            <FieldSet
              alignment="end"
              direction="horizontal"
              legendPlacement="none"
            >
              <FormField label="From">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="Start"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <FormField label="To">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="End"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <Tooltip content="Delete">
                <IconButton size="small" priority="secondary">
                  <Icons.DeleteSmall />
                </IconButton>
              </Tooltip>
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <TextButton size="small" prefixIcon={<Icons.AddSmall />}>
              Add Available Dates
            </TextButton>
          </SidePanel.Field>
        </SidePanel.Section>
        <SidePanel.Section title="Unavailable dates">
          <SidePanel.Field>
            <FieldSet
              alignment="end"
              direction="horizontal"
              legendPlacement="none"
            >
              <FormField label="From">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="Start"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <FormField label="To">
                <DatePicker
                  size="small"
                  width="auto"
                  placeholderText="End"
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
              <Tooltip content="Delete">
                <IconButton size="small" priority="secondary">
                  <Icons.DeleteSmall />
                </IconButton>
              </Tooltip>
            </FieldSet>
          </SidePanel.Field>
          <SidePanel.Field>
            <TextButton size="small" prefixIcon={<Icons.AddSmall />}>
              Add Unavailable Dates
            </TextButton>
          </SidePanel.Field>
        </SidePanel.Section>
      </SidePanel.Content>
    </SidePanel>
  )
}

```

### Data filter
- description: <p>Use side panels to display data filters. When opened, the panels should slide in from the right side of the screen. Add close buttons in the header and/or footer that can be used to close the panel.</p>
- example: 
```jsx 
() => {
  const [right, setRight] = React.useState(-440);
  const [records, setRecords] = React.useState([
    {
      image: <Image width="42px" height="42px" />,
    },
    {
      image: <Image width="42px" height="42px" />,
    },
    {
      image: <Image width="42px" height="42px" />,
    },
    {
      image: <Image width="42px" height="42px" />,
    },
    {
      image: <Image width="42px" height="42px" />,
    },
    {
      image: <Image width="42px" height="42px" />,
    },
    {
      image: <Image width="42px" height="42px" />,
    },
  ]);

  const columns = [
    {
      title: '',
      render: row => row.image,
    },
  ];

  const openPanel = () => {
    setRight(0);
  };

  const closePanel = () => {
    setRight(-440);
  };

  return (
    <div style={{ display: 'block', overflow: 'hidden', position: 'relative' }}>
      <Page height="780px" maxWidth="500px">
        <Page.Header title="Products" />
        <Page.Content>
          <Card>
            <Table data={records} columns={columns} rowVerticalPadding="tiny">
              <TableToolbar>
                <TableToolbar.ItemGroup position="start">
                  <TableToolbar.Item>
                    <TableToolbar.Label>7 products</TableToolbar.Label>
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
                      Filter
                    </Button>
                  </TableToolbar.Item>
                  <TableToolbar.Item>
                    <Search size="small" />
                  </TableToolbar.Item>
                </TableToolbar.ItemGroup>
              </TableToolbar>
              <Table.Content />
            </Table>
          </Card>
        </Page.Content>
      </Page>
      <div
        style={{
          position: 'absolute',
          top: 0,
          right: `${right}px`,
          height: '100%',
          boxShadow:
            '0 3px 24px 0 rgba(22, 45, 61, 0.18), 0 8px 8px 0 rgba(22, 45, 61, 0.12)',
          transition: 'right 0.4s ease 0s',
          zIndex: 1000,
        }}
      >
        <SidePanel title="Filter" onCloseButtonClick={closePanel}>
          <SidePanel.Header title="Filter" />
          <SidePanel.Footer>
            <Button onClick={closePanel} priority="secondary" fullWidth>
              Close
            </Button>
          </SidePanel.Footer>
        </SidePanel>
      </div>
    </div>
  );
};
```

### Quick view
- description: <p>Use side panels to provide quick views of list items. </p><p></p><p>Panels can either push the page content aside or overlay it, depending on the use case:</p><li>Overlay content when part of the page’s content can be covered.</li><li>Push content aside when the user should see all the information and actions on the main page.</li>
- example: 
```jsx 
() => {
  const [right, setRight] = React.useState(-440);
  const [records, setRecords] = React.useState([
    {
      image: <Avatar size="size36" name="Jenny Wilson" />,
    },
    {
      image: <Avatar size="size36" name="Robert Fox" />,
    },
    {
      image: <Avatar size="size36" name="Albert Flores" />,
    },
    {
      image: <Avatar size="size36" name="Floyd Miles" />,
    },
    {
      image: <Avatar size="size36" name="Esther Howard" />,
    },
    {
      image: <Avatar size="size36" name="Brooklyn Simmons" />,
    },
    {
      image: <Avatar size="size36" name="Kathryn Murphy" />,
    },
    {
      image: <Avatar size="size36" name="Dianne Russell" />,
    },
  ]);

  const columns = [
    {
      title: '',
      render: row => row.image,
    },
    {
      render: () => (
        <TableActionCell
          size="small"
          primaryAction={{
            text: 'View',
          }}
        />
      ),
    },
  ];

  const openPanel = () => {
    setRight(0);
  };

  const closePanel = () => {
    setRight(-440);
  };

  return (
    <div style={{ display: 'block', overflow: 'hidden', position: 'relative' }}>
      <Page height="780px" maxWidth="500px">
        <Page.Header title="Contacts" />
        <Page.Content>
          <Card>
            <Table data={records} columns={columns} onRowClick={openPanel}>
              <TableToolbar>
                <TableToolbar.ItemGroup position="start">
                  <TableToolbar.Item>
                    <TableToolbar.Label>8 contacts</TableToolbar.Label>
                  </TableToolbar.Item>
                </TableToolbar.ItemGroup>
              </TableToolbar>
              <Table.Content />
            </Table>
          </Card>
        </Page.Content>
      </Page>
      <div
        style={{
          position: 'absolute',
          top: 0,
          right: `${right}px`,
          height: '100%',
          boxShadow:
            '0 3px 24px 0 rgba(22, 45, 61, 0.18), 0 8px 8px 0 rgba(22, 45, 61, 0.12)',
          transition: 'right 0.4s ease 0s',
          zIndex: 1000,
        }}
      >
        <SidePanel title="Filter" onCloseButtonClick={closePanel}>
          <SidePanel.Header showDivider={false}>
            <Box direction="vertical" align="center" marginBottom="12px">
              <Avatar size="size72" />
            </Box>
            <Tabs
              items={[
                { id: 1, title: 'Overview' },
                { id: 2, title: 'Inbox' },
              ]}
              activeId={1}
              type="uniformSide"
              width="174px"
            />
          </SidePanel.Header>
        </SidePanel>
      </div>
    </div>
  );
};
```

### Composer actions
- description: <p>Use side panels to display composer settings and actions. These should be anchored to the left edge of the screen since they're opened through the <code><ComposerSidebar/></code>. </p>
- example: 
```jsx 
() => {
  const [selectedSidebar, setSelectedSidebar] = React.useState(0);
  const [activeTab, setActiveTab] = React.useState(0);
  const [toggleImage, setToggleImage] = React.useState(true);
  const [togglePosts, setTogglePosts] = React.useState(false);
  const [toggleCommenting, setToggleCommenting] = React.useState(false);
  const [descriptionValue, setDescriptionValue] = React.useState('');
  const [authorTags, setAuthorTags] = React.useState([]);
  const [categories, setCategories] = React.useState([
    {
      id: 0,
      label: 'Other posts',
      isChecked: false,
    },
    {
      id: 1,
      label: 'Recipes',
      isChecked: false,
    },
    {
      id: 2,
      label: 'Lifestyle',
      isChecked: false,
    },
  ]);
  const [publishDate, setPublishDate] = React.useState();
  const [themeTags, setThemeTags] = React.useState([
    { id: '1', label: 'Sport' },
    { id: '2', label: 'Routine' },
  ]);
  const [author, setAuthor] = React.useState();

  const items = [
    {
      id: 0,
      label: 'Settings',
      icon: <Icons.Settings />,
    },
    {
      id: 1,
      label: 'Categories',
      icon: <Icons.Category />,
    },
    {
      id: 2,
      label: 'Tags',
      icon: <Icons.Tag />,
    },
  ];

  const handleSelectTag = (tag, previousTags, setTags) =>
    setTags([...previousTags, { id: tag.id, label: tag.value }]);

  const handleRemoveTag = (tag, previousTags, setTags) =>
    setTags(previousTags.filter(currTag => currTag.id !== tag));

  const handleSidebarClick = id => {
    setSelectedSidebar(id);
  };

  const handleCloseSidePanel = () => {
    setSelectedSidebar();
  };

  const renderSettingsPanel = () => (
    <SidePanel onCloseButtonClick={handleCloseSidePanel} width="300px">
      <SidePanel.Header title="Post settings" showDivider={false}>
        <Tabs
          items={[
            { id: 0, title: 'General' },
            { id: 1, title: 'Advanced' },
          ]}
          activeId={activeTab}
          type="uniformSide"
          width="114px"
          onClick={value => setActiveTab(value.id)}
        />
      </SidePanel.Header>
      <SidePanel.Content></SidePanel.Content>
    </SidePanel>
  );

  const renderTagPanel = () => (
    <SidePanel onCloseButtonClick={handleCloseSidePanel} width="300px">
      <SidePanel.Header title="Tags" showDivider={false} />
      <SidePanel.Content />
    </SidePanel>
  );

  const renderCategoryPanel = () => {
    return (
      <SidePanel onCloseButtonClick={handleCloseSidePanel} width="300px">
        <SidePanel.Header title="Categories" showDivider={false} />
        <SidePanel.Content />
      </SidePanel>
    );
  };

  return (
    <Layout gap={0}>
      <Cell>
        <ComposerHeader backButtonValue="Back">
          <ComposerHeader.Actions justifyContent="flex-end">
            <ToggleButton labelValue="Undo">
              <Icons.Undo />
            </ToggleButton>
            <ToggleButton labelValue="Redo">
              <Icons.Redo />
            </ToggleButton>
          </ComposerHeader.Actions>
          <ComposerHeader.MainActions>
            <Button skin="inverted">Preview</Button>
            <Button>Publish</Button>
          </ComposerHeader.MainActions>
        </ComposerHeader>
      </Cell>
      <Cell>
        <Box direction="vertical" backgroundColor="D70">
          <Box gap="0" height="660px">
            <ComposerSidebar
              labelPlacement="bottom"
              items={items}
              selectedId={selectedSidebar}
              onClick={(_, { id }) => handleSidebarClick(id)}
            />
            {selectedSidebar === 0 && renderSettingsPanel()}
            {selectedSidebar === 1 && renderCategoryPanel()}
            {selectedSidebar === 2 && renderTagPanel()}
          </Box>
        </Box>
      </Cell>
    </Layout>
  );
};
```


