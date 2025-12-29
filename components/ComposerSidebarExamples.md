
## Feature Examples


### Size
- description: Control component size with `size` prop:<br/>
      &emsp;- `large` - use it when the component needs to be emphasized.<br/>
      &emsp;- `medium` (default) - use it in all default cases, especially if there are many (5 or more) items to show.<br/>
      &emsp;- `small` - use in more dense layouts.<br/>
- example: 
```jsx 

() => {
  return (
    <StorybookComponents.Stack justifyContent="space-around">
      <ComposerSidebar size="large" items={[
    {
      id: 0,
      label: 'Large',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      label: 'Large',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      label: 'Large',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      label: 'Large',
      icon: <Icons.CutOut />,
    },
  ]} />
      <ComposerSidebar size="medium" items={[
    {
      id: 0,
      label: 'Medium',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      label: 'Medium',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      label: 'Medium',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      label: 'Medium',
      icon: <Icons.CutOut />,
    },
  ]} />
  <ComposerSidebar
      size="small"
      items={[
        {
          id: 0,
          label: 'Small',
          icon: <Icons.CropRotate />,
        },
        {
          id: 1,
          label: 'Small',
          icon: <Icons.MagicWand />,
        },
        {
          id: 2,
          label: 'Small',
          icon: <Icons.Adjust />,
        },
        {
          id: 3,
          label: 'Small',
          icon: <Icons.CutOut />,
        },
      ]}
    />
    </StorybookComponents.Stack>
  );
};

```

### Label Placement
- description: Control the position of a toggle button labels with `labelPlacement` prop. It supports 2 values:<br/>
      &emsp;- `end` (default) - use it if there are many (5 or more) items to show. Button width depends on a label length but has a max width of 270 px. Label will be truncated if the limit is reached.<br/>
      &emsp;- `bottom` - use it with few  items to show. Component's width is fixed to 90 px.<br/>
      &emsp;- `tooltip` - use it only for professional tools that users are good at and use side actions repeatedly.
      For example, image editing tools like color fill, text, shape, etc. Configure tooltip's placement and size with `labelTooltipProps`.
- example: 
```jsx 

() => {
  const items = [
    {
      id: 0,
      label: 'Crop & Rotate',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      label: 'Enhance',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      label: 'Adjust',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      label: 'Cut Out',
      icon: <Icons.CutOut />,
    },
    {
      id: 4,
      label: 'Text',
      icon: <Icons.Rename />,
    },
  ];

  return (
    <StorybookComponents.Stack justifyContent="space-around">
      <ComposerSidebar labelPlacement="end" items={items} />
      <ComposerSidebar labelPlacement="bottom" items={items} />
      <ComposerSidebar labelPlacement="tooltip" items={items} />
    </StorybookComponents.Stack>
  );
};

```

### Ellipsis
- description: <p>Use <code>ellipsis</code> prop to change between truncated or wrapped label.</p>
- example: 
```jsx 
() => {
  const items = [
    {
      id: 0,
      label: 'Item',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      label: 'Item with a very very long label',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      label: 'Item',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      label: 'Item',
      icon: <Icons.CutOut />,
    },
    {
      id: 4,
      label: 'Item',
      icon: <Icons.Rename />,
    },
  ];

  return (
    <StorybookComponents.Stack justifyContent="space-around">
      <ComposerSidebar ellipsis={true} labelPlacement="end" items={items} />
      <ComposerSidebar ellipsis={false} labelPlacement="end" items={items} />
    </StorybookComponents.Stack>
  );
};
```

### Selected Item
- description: Highlight currently selected item with `selectedId` prop.
- example: 
```jsx 

() => {
  const items = [
    {
      id: 0,
      label: 'Item',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      label: 'Selected Item',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      label: 'Item',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      label: 'Item',
      icon: <Icons.CutOut />,
    },
  ];

  return <ComposerSidebar labelPlacement="end" items={items} selectedId={1} />;
};

```

### Disabled Item
- description: Show that a certain action or category in a sidebar is not available with `disabled` prop.
- example: 
```jsx 

() => {
  const items = [
    {
      id: 0,
      label: 'Item',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      label: 'Disabled Item',
      icon: <Icons.MagicWand />,
      disabled: true,
    },
    {
      id: 2,
      label: 'Item',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      label: 'Item',
      icon: <Icons.CutOut />,
    },
  ];

  return <ComposerSidebar labelPlacement="end" items={items} />;
};

```

### Section Title
- description: Group related items together with sections using `sectionTitle` prop.
- example: 
```jsx 

() => {
  const items = [
    {
      id: 0,
      sectionTitle: 'Section 1',
      label: 'Item',
      icon: <Icons.CropRotate />,
    },
    {
      id: 1,
      sectionTitle: 'Section 1',
      label: 'Item',
      icon: <Icons.MagicWand />,
    },
    {
      id: 2,
      sectionTitle: 'Section 2',
      label: 'Item',
      icon: <Icons.Adjust />,
    },
    {
      id: 3,
      sectionTitle: 'Section 2',
      label: 'Item',
      icon: <Icons.CutOut />,
    },
  ];

  return <ComposerSidebar labelPlacement="end" items={items} />;
};

```




    


## Common Use Case Examples


### Composer Settings
- description: Use the composer sidebar to display available tools and settings in the composer environment.<br/>
      <br/>
      Position it below the <a href="https://wix-style-react.com/?path=/story/components-navigation-composer--composerheader">`<ComposerHeader/>`</a> and fix it to the start of the remaining composer content area.
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

  const authorOptions = [
    listItemSelectBuilder({
      id: 0,
      prefix: <Avatar size="size18" />,
      title: 'Doe John',
      label: 'Doe John',
    }),
    listItemSelectBuilder({
      id: 1,
      prefix: <Avatar size="size18" />,
      title: 'John Doe',
      label: 'John Doe',
    }),
    listItemActionBuilder({
      title: 'New Author',
      prefixIcon: <Icons.Add />,
    }),
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
    <SidePanel width="300px" onCloseButtonClick={handleCloseSidePanel}>
      <SidePanel.Header title="Post Settings">
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
      <SidePanel.Content>
        {activeTab === 0 && (
          <Box direction="vertical" gap="24px">
            <FormField label="Display cover image" labelPlacement="left">
              <ToggleSwitch
                width="100%"
                checked={toggleImage}
                onChange={() => setToggleImage(!toggleImage)}
              />
            </FormField>
            {toggleImage && (
              <Cell>
                <Box height="120px">
                  <AddItem theme="image" tooltipContent="Add Item" />
                </Box>
              </Cell>
            )}
            <FormField label="Publish date">
              <DatePicker
                width="100%"
                placeholderText="Publish Now"
                popoverProps={{ appendTo: 'scrollParent' }}
                autoFocus={false}
                value={publishDate}
                onChange={date => setPublishDate(date)}
              />
            </FormField>
            <FormField label="Author">
              <AutoComplete
                placeholder="Select Author"
                options={authorOptions}
                selectedId={author}
                popoverProps={{ appendTo: 'window' }}
                value={author}
                onSelect={option => setAuthor(option.label)}
                onChange={event => setAuthor(event.target.value)}
              />
            </FormField>
            <FormField label="Set as featured post" labelPlacement="left">
              <ToggleSwitch
                width="100%"
                checked={togglePosts}
                onChange={() => setTogglePosts(!togglePosts)}
              />
            </FormField>
          </Box>
        )}
        {activeTab === 1 && (
          <Box direction="vertical" gap="24px">
            <FormField label="Description">
              <InputArea
                placeholder="Add a description..."
                value={descriptionValue}
                onChange={e => setDescriptionValue(e.target.value)}
                maxLength={140}
                hasCounter
              />
            </FormField>
            <FormField label="Related post">
              <MultiSelect
                tags={authorTags}
                options={[
                  { id: '1', value: 'British authors' },
                  { id: '2', value: 'French authors' },
                ]}
                customSuffix={
                  <Box>
                    <TextButton prefixIcon={<Icons.Add />}>
                      Add Posts
                    </TextButton>
                  </Box>
                }
                onSelect={tag =>
                  handleSelectTag(tag, authorTags, setAuthorTags)
                }
                onRemoveTag={tag =>
                  handleRemoveTag(tag, authorTags, setAuthorTags)
                }
              />
            </FormField>
            <FormField label="Enable commenting" labelPlacement="left">
              <ToggleSwitch
                width="100%"
                checked={toggleCommenting}
                onChange={() => setToggleCommenting(!toggleCommenting)}
              />
            </FormField>
          </Box>
        )}
      </SidePanel.Content>
    </SidePanel>
  );

  const renderTagPanel = () => (
    <SidePanel width="300px" onCloseButtonClick={handleCloseSidePanel}>
      <SidePanel.Header title="Tags" showDivider={false} />
      <SidePanel.Content noPadding>
        <Box
          direction="vertical"
          gap="24px"
          width="252px"
          padding="0 24px 24px 24px"
        >
          <Text>
            Add tags that describe what your post is about. Readers can use them
            to find other posts with similar content.
          </Text>
          <FormField label="Tags">
            <MultiSelect
              tags={themeTags}
              options={[
                { id: '1', value: 'Sport' },
                { id: '2', value: 'Routine' },
              ]}
              onSelect={tag => handleSelectTag(tag, themeTags, setThemeTags)}
              onRemoveTag={tag => handleRemoveTag(tag, themeTags, setThemeTags)}
            />
          </FormField>
        </Box>
      </SidePanel.Content>
    </SidePanel>
  );

  const renderCheckboxes = () => {
    return categories.map(item => {
      const handleChecked = id => {
        const updatedCategories = [...categories];
        const index = categories.findIndex(c => c.id === id);
        updatedCategories[index].isChecked = !updatedCategories[index]
          .isChecked;
        setCategories(updatedCategories);
      };

      return (
        <Checkbox
          checked={item.isChecked}
          onChange={() => handleChecked(item.id)}
          id={item.id}
        >
          {item.label}
        </Checkbox>
      );
    });
  };

  const renderCategoryPanel = () => {
    return (
      <SidePanel width="300px" onCloseButtonClick={handleCloseSidePanel}>
        <SidePanel.Header title="Categories" showDivider={false} />
        <SidePanel.Content noPadding>
          <Box
            direction="vertical"
            gap="24px"
            width="252px"
            padding="0 24px 24px 24px"
          >
            <Text>
              Let readers browse your posts by topic, e.g. food, lifestyle &
              travel.
            </Text>
            <FormField label="Assign a category">
              <Box direction="vertical" gap="12px">
                {renderCheckboxes()}
                <TextButton prefixIcon={<Icons.Add />}>
                  Create category
                </TextButton>
              </Box>
            </FormField>
          </Box>
        </SidePanel.Content>
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
        <Box direction="vertical">
          <Box gap="0" height="600px">
            <ComposerSidebar
              labelPlacement="bottom"
              items={items}
              selectedId={selectedSidebar}
              onClick={(_, { id }) => handleSidebarClick(id)}
            />

            {selectedSidebar === 0 && renderSettingsPanel()}
            {selectedSidebar === 1 && renderCategoryPanel()}
            {selectedSidebar === 2 && renderTagPanel()}

            <Box backgroundColor="D70" width="100%">
              <Box width="100%" padding={4}>
                <StorybookComponents.Placeholder>
                  <Box verticalAlign="middle" align="center" height="100%">
                    <Text>Composer content area</Text>
                  </Box>
                </StorybookComponents.Placeholder>
              </Box>
            </Box>
          </Box>
        </Box>
      </Cell>
    </Layout>
  );
};

```


