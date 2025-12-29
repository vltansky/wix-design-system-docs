
## Feature Examples


### Structure
- description: Composer header consists of 3 areas:<br/>
      &emsp;- Back button on the left.<br/>
      &emsp;- Additional actions container in the center.<br/>
      &emsp;- Main actions container on the right.<br/>
      <br/>
      There can be multiple containers with Additional actions in the middle. Available space will be evenly divided among them.<br/>
      <br/>
      Note that all areas are optional.
- example: 
```jsx 

<StorybookComponents.Stack flexDirection="column">
  <ComposerHeader backButtonValue="Back button">
    <ComposerHeader.Actions>
      <StorybookComponents.Placeholder height="35px">
        Additional actions
      </StorybookComponents.Placeholder>
    </ComposerHeader.Actions>
    <ComposerHeader.MainActions>
      <StorybookComponents.Placeholder height="35px">
        Main actions
      </StorybookComponents.Placeholder>
    </ComposerHeader.MainActions>
  </ComposerHeader>
  <ComposerHeader backButtonValue="Back button">
    <ComposerHeader.Actions justifyContent="flex-start">
      <StorybookComponents.Placeholder height="35px">
        Additional actions (1)
      </StorybookComponents.Placeholder>
    </ComposerHeader.Actions>
    <ComposerHeader.Actions justifyContent="flex-end">
      <StorybookComponents.Placeholder height="35px">
        Additional actions (2)
      </StorybookComponents.Placeholder>
    </ComposerHeader.Actions>
    <ComposerHeader.MainActions>
      <StorybookComponents.Placeholder height="35px">
        Main actions
      </StorybookComponents.Placeholder>
    </ComposerHeader.MainActions>
  </ComposerHeader>
</StorybookComponents.Stack>

```

### Size
- description: Control component height and back button size with `size` prop:<br/>
      &emsp;- `medium` (default) - use it in all common cases. Height is fixed at 66 px.<br/>
      &emsp;- `small` - use it to maximise space for the content area. Height is fixed at 54 px.<br/>
      <br/>
      Note that the size for child items in `<ComposerHeader.MainActions/>`, `<ComposerHeader.Actions/>`, and `<ComposerHeader.SaveStatus/>` containers will have to be adjusted manually.
- example: 
```jsx 

<StorybookComponents.Stack flexDirection='column'>
  <ComposerHeader backButtonValue="Medium Size">
    <ComposerHeader.Actions justifyContent="flex-end">
      <ComposerHeader.SaveStatus saveStatusValue="Medium size..." />
    </ComposerHeader.Actions>
    <ComposerHeader.MainActions>
      <Button skin="inverted">Medium</Button>
      <Button>Medium</Button>
    </ComposerHeader.MainActions>
  </ComposerHeader>
  <ComposerHeader size="small" backButtonValue="Small Size">
    <ComposerHeader.Actions justifyContent="flex-end">
      <ComposerHeader.SaveStatus size="small" saveStatusValue="Small size..."/>
    </ComposerHeader.Actions>
    <ComposerHeader.MainActions>
      <Button size="small" skin="inverted">Small</Button>
      <Button size="small">Small</Button>
    </ComposerHeader.MainActions>
  </ComposerHeader>
</StorybookComponents.Stack>

```

### Shadow
- description: Add a shadow with `dropShadow` prop. It will replace the default bottom divider.
- example: 
```jsx 

<ComposerHeader backButtonValue="Back to Posts" dropShadow>
  <ComposerHeader.MainActions>
    <Button skin="inverted">Preview</Button>
    <Button>Publish</Button>
  </ComposerHeader.MainActions>
</ComposerHeader>

```

### Back Button
- description: Add a back button by specifying its label with `backButtonValue` prop.<br/>
      <br/>
      Button is added to the left side of a Composer header. Its position cannot be changed.
- example: 
```jsx 
<ComposerHeader backButtonValue="Back to Posts" />
```

### Main Actions
- description: Add main actions as children items to `<ComposerHeader.MainActions>` container on the right side of the Composer header. Container position is fixed and cannot be changed.<br/>
      <br/>
      In all common cases, use <a href="https://wix-style-react.com/?path=/story/components-actions--button">`<Button/>`</a> and <a href="https://wix-style-react.com/?path=/story/components-actions--textbutton">`<TextButton/>`</a> components to display the actions.
- example: 
```jsx 

<ComposerHeader>
  <ComposerHeader.MainActions>
    <Button skin="inverted">Preview</Button>
    <Button>Publish</Button>
  </ComposerHeader.MainActions>
</ComposerHeader>

```

### Additional Actions
- description: <p>Add secondary actions or content to <code><ComposerHeader.Actions/></code> container in the middle of the Composer header.</p><p></p><p>Use justifyContent prop to distribute content inside the container. It accepts 3 values:</p><li><code>flex-start</code> (default) - aligns items to the left.</li><li><code>center</code> - centers items within the container.</li><li><code>flex-end</code> - aligns items to the right.</li><p></p><p>Vertical dividers will be added automatically to separate primary and secondary actions.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="Column">
  <ComposerHeader backButtonValue="Back to Posts">
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
</StorybookComponents.Stack>;
```

### Save Status
- description: Add a save status to the Composer header with a compound `<ComposerHeader.SaveStatus/>` component. Include it in the additional actions container, justified to the end.<br/>
      <br/>
      Set save status label with `saveStatusValue` prop.<br/>
      <br/>
      Change its status to error with `saveStatusError` prop.
- example: 
```jsx 

<StorybookComponents.Stack flexDirection="Column">
  <ComposerHeader backButtonValue="Back to Posts">
    <ComposerHeader.Actions justifyContent="flex-end">
      <ComposerHeader.SaveStatus saveStatusValue="Saving..." />
    </ComposerHeader.Actions>
    <ComposerHeader.MainActions>
      <Button skin="inverted">Preview</Button>
      <Button>Publish</Button>
    </ComposerHeader.MainActions>
  </ComposerHeader>
  <ComposerHeader backButtonValue="Back to Posts">
    <ComposerHeader.Actions justifyContent="flex-end">
      <ComposerHeader.SaveStatus
        saveStatusValue="Draft not saved"
        saveStatusError
      />
    </ComposerHeader.Actions>
    <ComposerHeader.MainActions>
      <Button skin="inverted">Preview</Button>
      <Button>Publish</Button>
    </ComposerHeader.MainActions>
  </ComposerHeader>
</StorybookComponents.Stack>

```




    


## Common Use Case Examples


### Composer
- description: Include a Composer header on top of the composer environment.
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

### Multiple Steps
- description: Allow users to break the creation process into multiple steps by placing <a href="https://wix-style-react.com/?path=/story/components-navigation--stepper">`<Stepper/>`</a> inside the Composer header.<br/>
      <br/>
      Use `<ComposerSidebar.Actions/>` container to store it.
- example: 
```jsx 

() => {
  const [activeStep, setActiveStep] = React.useState(0);
  const [selectedSidebar, setSelectedSidebar] = React.useState(0);
  const [selectedThumbnail, setSelectedThumbnail] = React.useState(0);
  const items = [
    {
      id: 0,
      label: 'Add',
      icon: <Icons.Add />,
    },
    {
      id: 1,
      label: 'Background',
      icon: <Icons.Background />,
    },
  ];

  const handleNextClick = () => {
    setActiveStep(activeStep + 1);
  };

  const handleBackClick = () => {
    setActiveStep(activeStep - 1);
  };

  const handleCloseSidePanel = () => setSelectedSidebar();

  const renderPublishPage = () => {
    return (
      <Page>
        <Page.Header title="Publish & Share on Social" />
        <Page.Content>
          <Layout>
            <Cell span={6}>
              <BrowserPreviewWidget
                backgroundColor="D70"
                skin="custom"
                browserBarSize="size18"
              >
                <Image
                  width="450px"
                  height="200px"
                  src="example.jpg"
                  borderRadius={0}
                />
              </BrowserPreviewWidget>
            </Cell>
            <Cell span={6}>
              <Box paddingBottom="30px" paddingTop="24px">
                <Text>
                  Once you publish a campaign online, you can share it on social
                  to reach more people. To send it as an email, go back and add
                  recipients.
                  <br />
                  <br />
                  <b>Note:</b> Publishing a campaign without sending it first
                  will count as one of your monthly campaigns.
                </Text>
              </Box>
              <Box align="right" gap={1}>
                <Button priority="secondary">Cancel</Button>
                <Button>Publish</Button>
              </Box>
            </Cell>
          </Layout>
        </Page.Content>
      </Page>
    );
  };

  const renderRecipientsPage = () => {
    const columns = [
      {
        title: 'Name',
        render: row => row.name,
        width: '40%',
      },
      {
        title: 'Email',
        render: row => row.email,
        width: '30%',
      },
      {
        title: 'Phone',
        render: row => row.phone,
        width: '20%',
      },
      {
        render: row => (
          <TableActionCell
            popoverMenuProps={{ appendTo: 'window' }}
            secondaryActions={[
              {
                icon: <Icons.Delete />,
                text: 'Delete',
                onClick: () => {},
              },
            ]}
          />
        ),
        width: '10%',
      },
    ];

    const records = [
      { name: 'Yuki Tsunoda', email: 'yukif1@mail.com', phone: '214-399-0638' },
      {
        name: 'Ben Simons',
        email: 'ben.simons@mail.com',
        phone: '269-267-2573',
      },
      {
        name: 'Alex Halifax',
        email: 'ahalifaxalex@mail.com',
        phone: '317-900-9252',
      },
      {
        name: 'Walter Jenning',
        email: 'walterjen@mail.com',
        phone: '440-263-0433',
      },
    ];
    return (
      <Page>
        <Page.Header
          title="Add Recipients"
          subtitle="Type your recipients below or select from your contacts, labels, or filters."
        />
        <Page.Content>
          <Layout>
            <Cell>
              <FormField label="To:">
                <MultiSelect
                  popoverProps={{ appendTo: 'window' }}
                  tags={[{ id: '0', label: 'Alex Halifax' }]}
                  options={[]}
                  customSuffix={
                    <Box>
                      <TextButton prefixIcon={<Icons.Add />}>
                        Add Contacts
                      </TextButton>
                    </Box>
                  }
                />
              </FormField>
            </Cell>
            <Cell>
              <Card>
                <Table data={records} columns={columns} showSelection>
                  <Page.Sticky>
                    <Card>
                      <TableToolbar>
                        <TableToolbar.ItemGroup position="start">
                          <TableToolbar.Item>
                            <TableToolbar.Title>Contacts</TableToolbar.Title>
                          </TableToolbar.Item>
                        </TableToolbar.ItemGroup>
                      </TableToolbar>
                      <Table.Titlebar />
                    </Card>
                  </Page.Sticky>
                  <Card>
                    <Table.Content titleBarVisible={false} />
                  </Card>
                </Table>
              </Card>
            </Cell>
          </Layout>
        </Page.Content>
      </Page>
    );
  };

  const renderThumbnail = (title, id, isBackground) => (
    <Thumbnail
      selected={selectedThumbnail === id}
      title={<Text size="medium">{title}</Text>}
      image={<Image />}
      onClick={() => setSelectedThumbnail(id)}
      backgroundImage={isBackground ? <Image height="114px" /> : undefined}
      height="114px"
      width="114px"
    />
  );

  const renderCreateStepSidePanel = () => (
    <SidePanel width="300px" onCloseButtonClick={handleCloseSidePanel}>
      <SidePanel.Header title="Add" showDivider={false} />
      <SidePanel.Content noPadding stretchVertically>
        <Box
          direction="vertical"
          gap="24px"
          width="252px"
          padding="10px 24px 24px 24px"
        >
          <Box gap={4}>
            {renderThumbnail('Text', 0)}
            {renderThumbnail('Image', 1)}
          </Box>
          <Box gap={4}>
            {renderThumbnail('Button', 2)}
            {renderThumbnail('Divider', 3)}
          </Box>
          <Box gap={4}>
            {renderThumbnail('Social', 4)}
            {renderThumbnail('Columns', 5)}
          </Box>
        </Box>
      </SidePanel.Content>
    </SidePanel>
  );

  const renderBackgroundSidePanel = () => {
    return (
      <SidePanel width="306px" onCloseButtonClick={handleCloseSidePanel}>
        <SidePanel.Header title="Change background" showDivider={false} />
        <SidePanel.Content noPadding>
          <Box
            direction="vertical"
            gap="24px"
            width="252px"
            padding="0 24px 24px 24px"
          >
            <FormField label="Background color">
              <ColorInput
                value="#8EF2D8"
                popoverProps={{ appendTo: 'scrollParent' }}
              />
            </FormField>

            <FormField label="Patterns & Images" />

            <Box gap={4}>
              <Box width="50%" height="114px">
                <AddItem tooltipContent="Add Item" theme="image" />
              </Box>
              {renderThumbnail('', 0, true)}
            </Box>
            <Box gap={4}>
              {renderThumbnail('', 1, true)}
              {renderThumbnail('', 2, true)}
            </Box>
            <Box gap={4}>
              {renderThumbnail('', 3, true)}
              {renderThumbnail('', 4, true)}
            </Box>
          </Box>
        </SidePanel.Content>
      </SidePanel>
    );
  };

  const renderCreateStep = () => (
    <>
      <ComposerSidebar
        labelPlacement="bottom"
        items={items}
        selectedId={selectedSidebar}
        onClick={(_, { id }) => setSelectedSidebar(id)}
      />
      {selectedSidebar === 0 && renderCreateStepSidePanel()}
      {selectedSidebar === 1 && renderBackgroundSidePanel()}

      <Box backgroundColor="D70" width="100%">
        <Box width="100%" padding={4}>
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center" height="100%">
              <Text>Composer content area</Text>
            </Box>
          </StorybookComponents.Placeholder>
        </Box>
      </Box>
    </>
  );

  return (
    <Layout gap={0}>
      <Cell>
        <ComposerHeader
          backButtonValue={activeStep > 0 ? 'Back' : undefined}
          onBackClick={handleBackClick}
        >
          <ComposerHeader.Actions justifyContent="center">
            <Stepper
              type="text"
              activeStep={activeStep}
              steps={[
                { text: 'Create' },
                { text: 'Add Recipients' },
                { text: 'Publish & Send' },
              ]}
              onClick={step => setActiveStep(step)}
            />
          </ComposerHeader.Actions>
          {activeStep !== 2 && (
            <ComposerHeader.MainActions>
              <Button
                onClick={handleNextClick}
                suffixIcon={<Icons.ArrowRight />}
              >
                Next
              </Button>
            </ComposerHeader.MainActions>
          )}
        </ComposerHeader>
      </Cell>
      <Cell>
        <Box direction="vertical">
          <Box gap="0" height="800px">
            {activeStep === 0 && renderCreateStep()}
            {activeStep === 1 && renderRecipientsPage()}
            {activeStep === 2 && renderPublishPage()}
          </Box>
        </Box>
      </Cell>
    </Layout>
  );
};

```


