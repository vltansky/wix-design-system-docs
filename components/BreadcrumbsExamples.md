
## Feature Examples


### Size
- description: <p>Control the size of breadcrumbs with the <code>size</code> property. It supports 2 sizes:</p><li><code>medium</code> is used by default in regular page layouts.</li><li>When it's necessary to emphasize the path, use <code>large</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Breadcrumbs
    items={[
      { id: 0, value: 'Medium' },
      { id: 1, value: 'Medium' },
      { id: 2, value: 'Medium' },
    ]}
    size="medium"
    activeId={2}
  />
  <Breadcrumbs
    items={[
      { id: 0, value: 'Large' },
      { id: 1, value: 'Large' },
      { id: 2, value: 'Large' },
    ]}
    size="large"
    activeId={2}
  />
</StorybookComponents.Stack>;
```

### Theme
- description: <p>Control breadcrumbs' appearance with the <code>theme</code> prop. It supports 3 styles:</p><li><code>onGrayBackground</code> is used by default with the default page header style.</li><li>Use <code>onDarkBackground</code> when breadcrumbs appear on a dark background or an image.</li><li>Use <code>onWhiteBackground</code> when breadcrumbs appear on a white background, for example in a modal.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack padding="24px">
    <Breadcrumbs
      theme="onGrayBackground"
      items={[
        { id: 0, value: 'On grey background' },
        { id: 1, value: 'On grey background' },
        { id: 2, value: 'On grey background' },
      ]}
      activeId={2}
    />
  </StorybookComponents.Stack>
  <StorybookComponents.Background skin="dark">
    <StorybookComponents.Stack padding="24px">
      <Breadcrumbs
        theme="onDarkBackground"
        items={[
          { id: 0, value: 'On dark background' },
          { id: 1, value: 'On dark background' },
          { id: 2, value: 'On dark background' },
        ]}
        activeId={2}
      />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="24px">
      <Breadcrumbs
        theme="onWhiteBackground"
        items={[
          { id: 0, value: 'On white background' },
          { id: 1, value: 'On white background' },
          { id: 2, value: 'On white background' },
        ]}
        activeId={2}
      />
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
</StorybookComponents.Stack>;
```

### Max width
- description: <p>Control when a breadcrumb item gets truncated with the <code>itemMaxWidth</code> property. When truncated, the breadcrumb item shows an ellipsis and the full text appears in a tooltip on hover.</p><p></p><p>Default max width is <code>240</code> px.</p><p></p><p>Avoid truncating breadcrumb items at all by setting max width to <code>max-content</code>.</p>
- example: 
```jsx 
() => {
  const items = [
    { id: 0, value: 'Title' },
    { id: 1, value: 'Title' },
    {
      id: 2,
      value: 'Long title is truncated when default maximum width is reached',
    },
    { id: 3, value: 'Title' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Breadcrumbs items={items} activeId={3} itemMaxWidth="150px" />
      <Breadcrumbs items={items} activeId={3} />
      <Breadcrumbs items={items} activeId={3} itemMaxWidth="max-content" />
    </StorybookComponents.Stack>
  );
};
```

### Disabled
- description: <p>Stop users from navigating to a particular breadcrumb item with the <code>disabled</code> property.</p>
- example: 
```jsx 
<Breadcrumbs
  items={[
    { id: 0, value: 'Title (Disabled)', disabled: true },
    { id: 1, value: 'Title' },
    { id: 2, value: 'Title' },
    { id: 3, value: 'Title' },
  ]}
  activeId={3}
/>;
```




    


## Common Use Case Examples


### Navigation between pages
- description: <p>Add breadcrumbs to <code><Page.Header/></code> <a href="https://www.wix-style-react.com/storybook/?path=/story/components-layout-page--page-header"></a>to let users quickly navigate back to the previous page in the hierarchy.</p>
- example: 
```jsx 
<Page.Header
  title="Appointment Hours"
  subtitle="Set default hours for when you and your staff are available to take appointments."
  breadcrumbs={
    <Breadcrumbs
      activeId="3"
      items={[
        { id: '1', value: 'Home', link: '' },
        { id: '2', value: 'Booking Settings', link: '' },
        { id: '3', value: 'Appointment Hours', link: '' },
      ]}
      onClick={() => {}}
    />
  }
  showBackButton
  onBackClicked={() => {}}
  actionsBar={
    <StorybookComponents.Stack gap="12px">
      <Button skin="inverted">Cancel</Button>
      <Button>Save</Button>
    </StorybookComponents.Stack>
  }
/>;
```

### Navigate between folders
- description: <p>Use breadcrumbs to let users navigate between folders and files.</p>
- example: 
```jsx 
() => {
  const renderThumbnail = backgroundImage => (
    <Cell span={2}>
      <Thumbnail
        backgroundImage={backgroundImage}
        title={
          <Text secondary size="tiny">
            {backgroundImage}
          </Text>
        }
        height={132}
      />
    </Cell>
  );

  return (
    <CustomModalLayout
      title="Choose images"
      onCloseButtonClick={() => {}}
      removeContentPadding={true}
      showHeaderDivider
      content={
        <Box>
          <Box>
            <SidebarNext
              skin="neutral"
              isLoading={false}
              selectedKey="2"
              header={
                <SidebarHeaderNext>
                  <Button prefixIcon={<Icons.Add />}>Upload Media</Button>
                </SidebarHeaderNext>
              }
            >
              <SidebarItemNext itemKey="1">Home</SidebarItemNext>
              <SidebarDividerNext />
              <SidebarTitleItemNext>Manage</SidebarTitleItemNext>
              <SidebarItemNext itemKey="2">Site Files</SidebarItemNext>
              <SidebarItemNext itemKey="3">My Boards</SidebarItemNext>
              <SidebarItemNext itemKey="4">Trash</SidebarItemNext>
              <SidebarDividerNext />
              <SidebarTitleItemNext>Explore</SidebarTitleItemNext>
              <SidebarItemNext itemKey="5">Media from Wix</SidebarItemNext>
              <SidebarItemNext itemKey="6">Shutterstock</SidebarItemNext>
              <SidebarItemNext itemKey="7">Unsplash</SidebarItemNext>
            </SidebarNext>
          </Box>
          <Box direction="vertical" width="100%">
            <Box direction="vertical" padding="24px">
              <Search />
            </Box>
            <Box padding="0px 24px 24px 24px">
              <Breadcrumbs
                theme="onWhiteBackground"
                items={[
                  { id: 0, value: 'Site Files', link: '' },
                  { id: 1, value: 'Stores', link: '' },
                  { id: 2, value: 'Product images', link: '' },
                  { id: 3, value: 'Photos', link: '' },
                ]}
                activeId={3}
              />
            </Box>
            <Box padding="0px 24px">
              <Layout>
                {renderThumbnail('ProductExample1.jpg')}
                {renderThumbnail('ProductExample2.jpg')}
                {renderThumbnail('ProductExample3.jpg')}
                {renderThumbnail('ProductExample4.jpg')}
                {renderThumbnail('ProductExample5.jpg')}
                {renderThumbnail('ProductExample6.jpg')}
                {renderThumbnail('ProductExample7.jpg')}
                {renderThumbnail('ProductExample8.jpg')}
              </Layout>
            </Box>
            <Box paddingTop="60px">
              <Divider />
            </Box>
            <Box padding="12px 24px" align="right">
              <Box>
                <Button>Add to Page</Button>
              </Box>
            </Box>
          </Box>
        </Box>
      }
    />
  );
};
```


