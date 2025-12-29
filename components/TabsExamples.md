
## Feature Examples


### Size
- description: <p>Control tabs size with <code>size</code> prop:</p><li>Use <code>small</code> in dense layouts, like narrow panels.</li><li>Use <code>medium</code> (default) in all other layouts, like below <code><Page.Header/></code>.</li>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(2);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Tabs
        size="small"
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
        items={[
          { id: 1, title: 'Small' },
          { id: 2, title: 'Small' },
        ]}
      />
      <Tabs
        size="medium"
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
        items={[
          { id: 1, title: 'Medium' },
          { id: 2, title: 'Medium' },
        ]}
      />
    </StorybookComponents.Stack>
  );
};
```

### Min width
- description: <p>By default, tabs fill in the entire width of their parent container and have a minimum width of 628 px.</p><p></p><p>Set custom min width of tabs using the <code>minWidth</code> prop.</p>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(2);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Tabs
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
        items={[
          { id: 1, title: 'Default' },
          { id: 2, title: 'Default' },
        ]}
      />
      <Box>
        <Tabs
          minWidth="360px"
          activeId={activeId}
          onClick={(value) => setActiveId(value.id)}
          items={[
            { id: 1, title: 'Min width' },
            { id: 2, title: 'Min width' },
          ]}
        />
      </Box>
    </StorybookComponents.Stack>
  );
};
```

### Type
- description: <p>Control how tabs are positioned with <code>type</code> prop:</p><li>By default, each tab grows with its title. Side paddings are inside tabs.</li><li><code>compact</code> - each tab grows with its title. Side paddings are outside tabs.</li><li><code>compactSide</code> - each tab grows with its title. Side paddings are outside tabs. The first and the last tab has no left and right paddings respectively.</li><li><code>uniformSide</code> - each tab grows to the size defined in <code>width</code> prop. If tab content is longer than the <code>width</code>, it gets truncated by ellipsis. Side paddings are inside tabs.</li><li><code>uniformFull</code> - all tabs grow equally to fill in the whole container. Side paddings are inside tabs.</li>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(1);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Box direction="vertical" gap="1">
        <Text secondary weight="normal">
          Default
        </Text>
        <Tabs
          items={[
            { id: 1, title: 'Tab' },
            { id: 2, title: 'Tab' },
            { id: 3, title: 'Tab' },
          ]}
          activeId={activeId}
          onClick={(value) => setActiveId(value.id)}
        />
      </Box>
      <Box direction="vertical" gap="1">
        <Text secondary weight="normal">
          Compact
        </Text>
        <Tabs
          type="compact"
          items={[
            { id: 1, title: 'Tab' },
            { id: 2, title: 'Tab' },
            { id: 3, title: 'Tab' },
          ]}
          activeId={activeId}
          onClick={(value) => setActiveId(value.id)}
        />
      </Box>
      <Box direction="vertical" gap="1">
        <Text secondary weight="normal">
          Compact side
        </Text>
        <Tabs
          type="compactSide"
          items={[
            { id: 1, title: 'Tab' },
            { id: 2, title: 'Tab' },
            { id: 3, title: 'Tab' },
          ]}
          activeId={activeId}
          onClick={(value) => setActiveId(value.id)}
        />
      </Box>
      <Box direction="vertical" gap="1">
        <Text secondary weight="normal">
          Uniform side
        </Text>
        <Tabs
          type="uniformSide"
          width={120}
          items={[
            { id: 1, title: 'Tab' },
            { id: 2, title: 'Tab' },
            { id: 3, title: 'Tab' },
          ]}
          activeId={activeId}
          onClick={(value) => setActiveId(value.id)}
        />
      </Box>
      <Box direction="vertical" gap="1">
        <Text secondary weight="normal">
          Uniform full
        </Text>
        <Tabs
          type="uniformFull"
          items={[
            { id: 1, title: 'Tab' },
            { id: 2, title: 'Tab' },
            { id: 3, title: 'Tab' },
          ]}
          activeId={activeId}
          onClick={(value) => setActiveId(value.id)}
        />
      </Box>
    </StorybookComponents.Stack>
  );
};
```

### Alignment
- description: <p>Control text alignment inside tabs with <code>alignment</code> prop. It supports 3 options:</p><li>Use <code>start</code> (default) to align tab titles to to the left.</li><li>Use <code>center</code> to align them to the middle.</li><li>Use <code>end</code> to align them to the right.</li>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(1);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Tabs
        alignment="start"
        type="uniformFull"
        items={[
          { id: 1, title: 'Start' },
          { id: 2, title: 'Start' },
        ]}
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
      />
      <Tabs
        alignment="center"
        type="uniformFull"
        items={[
          { id: 1, title: 'Center' },
          { id: 2, title: 'Center' },
        ]}
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
      />
      <Tabs
        alignment="end"
        type="uniformFull"
        items={[
          { id: 1, title: 'End' },
          { id: 2, title: 'End' },
        ]}
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
      />
    </StorybookComponents.Stack>
  );
};
```

### Bottom divider
- description: <p>Control if the default bottom divider is shown with <code>hasDivider</code> prop.</p>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(1);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Tabs
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
        items={[
          { id: 1, title: 'Default' },
          { id: 2, title: 'Default' },
        ]}
      />
      <Tabs
        hasDivider={false}
        activeId={activeId}
        onClick={(value) => setActiveId(value.id)}
        items={[
          { id: 1, title: 'No divider' },
          { id: 2, title: 'No divider' },
        ]}
      />
    </StorybookComponents.Stack>
  );
};
```

### Side content
- description: <p>Add any component to the end of tabs with <code>sideContent</code> prop.</p><p></p><p>For example, use it to store a filter or form actions like Save and Cancel.</p>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(1);

  return (
    <Tabs
      activeId={activeId}
      onClick={(value) => setActiveId(value.id)}
      items={[
        { id: 1, title: 'Tab' },
        { id: 2, title: 'Tab' },
      ]}
      sideContent=<StorybookComponents.Placeholder>
        Side content
      </StorybookComponents.Placeholder>
    />
  );
};
```




    


## Common Use Case Examples


### In a page
- description: <p>Use tabs to divide all page contents into shorter, digestible parts.</p><p></p><p>Divide content in a way that allows users completing their task under each tab independently.</p>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(1);

  const tabContent = {
    1: (
      <Card>
        <Card.Header
          title="General (RSVP event)"
          subtitle={
            <Box gap="1">
              <Text skin="standard" secondary>
                Guests register by submitting yes & no responses.
              </Text>
              <TextButton underline="always">Learn More</TextButton>
            </Box>
          }
        />
        <Card.Divider />
        <Card.Content>
          <Layout>
            <Cell span={8}>
              <Layout>
                <Cell>
                  <FormField label="Event name">
                    <Input value="90s Rock Concert" />
                  </FormField>
                </Cell>
                <Cell>
                  <FormField label="Short teaser (optional)">
                    <InputArea
                      placeholder="Add a few words under the name of the event to inspire guests, e.g., An unforgettable show!"
                      resizable
                      rows={3}
                    />
                  </FormField>
                </Cell>
              </Layout>
            </Cell>
            <Cell span={4}>
              <FormField label="Event cover">
                <ImageViewer width="100%" height="168px" />
              </FormField>
            </Cell>
          </Layout>
        </Card.Content>
      </Card>
    ),

    2: (
      <Card>
        <MarketingLayout
          title="Customize your own automated emails"
          description="Design customized emails and set the automated triggers. Remember to disable the relevant default email above if you're creating your own branded emails."
          actions={
            <Button size="small" priority="secondary">
              Create Automations
            </Button>
          }
          image={
            <Box width="100%" align="right">
              <Image
                width="120px"
                src="PromotionalPromoteMarketingHomeEmail.svg"
                transparent
              />
            </Box>
          }
        />
      </Card>
    ),

    3: (
      <EmptyState
        theme={'page-no-border'}
        title="Start inviting guests"
        subtitle="Once guests RSVP to your event, you’ll see their info here. To get started, send an invite."
      >
        {<TextButton prefixIcon={<Icons.Add />}>Create Invitation</TextButton>}
      </EmptyState>
    ),
  };

  return (
    <Page>
      <Page.Header
        breadcrumbs={
          <Breadcrumbs
            activeId="2"
            items={[
              { id: '1', value: 'Events' },
              { id: '2', value: '90s Rock Concert' },
            ]}
            onClick={() => {}}
          />
        }
        showBackButton
        onBackClicked={() => {}}
        title="90s Rock Concert"
        actionsBar=<Box gap="2" height="60px">
          <Button priority="secondary">Cancel</Button>
          <Button>Save</Button>
        </Box>
      />
      <Page.Content>
        <Layout>
          <Cell>
            <Tabs
              activeId={activeId}
              onClick={(value) => setActiveId(value.id)}
              items={[
                { id: 1, title: 'Event details' },
                { id: 2, title: 'Emails' },
                { id: 3, title: 'Guest list' },
              ]}
            />
          </Cell>
          <Cell>{tabContent[activeId]}</Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};
```

### In a panel
- description: <p>Let users switch between parts of content in the same context of a <code><SidePanel/></code>.</p><p></p><p>Select to show either panel divider or a default tabs’ divider to separate panel header from its main content.</p>
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
  const [publishDate, setPublishDate] = React.useState();
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
    setTags(previousTags.filter((currTag) => currTag.id !== tag));

  const renderSettingsPanel = () => (
    <SidePanel width="300px" onCloseButtonClick={() => {}}>
      <SidePanel.Header title="Post Settings" showDivider={false}>
        <Tabs
          items={[
            { id: 0, title: 'General' },
            { id: 1, title: 'Advanced' },
          ]}
          activeId={activeTab}
          type="uniformSide"
          width="114px"
          onClick={(value) => setActiveTab(value.id)}
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
                onChange={(date) => setPublishDate(date)}
              />
            </FormField>
            <FormField label="Author">
              <AutoComplete
                placeholder="Select Author"
                options={authorOptions}
                selectedId={author}
                popoverProps={{ appendTo: 'window' }}
                value={author}
                onSelect={(option) => setAuthor(option.label)}
                onChange={(event) => setAuthor(event.target.value)}
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
                onChange={(e) => setDescriptionValue(e.target.value)}
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
                onSelect={(tag) =>
                  handleSelectTag(tag, authorTags, setAuthorTags)
                }
                onRemoveTag={(tag) =>
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
              selectedId={0}
            />

            {selectedSidebar === 0 && renderSettingsPanel()}

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


