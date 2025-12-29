
## Feature Examples


### Size
- description: <p>Adjust loader size using the <code>size</code> prop. It supports 4 sizes:</p><li><code>large</code>  - use for a full page, like when saving applied changes.</li><li><code>medium</code> (default) - use for a specific area inside of a page.</li><li><code>small</code> - use in larger components, like a table or a modal.</li><li><code>tiny</code> - use in smaller components, like a button.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection='column' gap='48px'>
  <Loader size="large" />
  <Loader size="medium" />
  <Loader size="small" />
  <Loader size="tiny" />
</StorybookComponents.Stack>;
```

### Color
- description: <p>Change the colors of the loader circle with the <code>color</code> prop. There are 2 color options:</p><li><code>blue</code> (default) - use on white and light grey backgrounds.</li><li><code>white</code> - use on dark backgrounds.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box backgroundColor="D80" align="center" padding="SP4">
    <Loader color="blue" />
  </Box>
  <Box backgroundColor="D10" align="center" padding="SP4">
    <Loader color="white" />
  </Box>
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Show the process status using the <code>statusMessage</code> prop. The message is displayed when a user mouse hovers over the loader.</p><p></p><p><em>Note:</em> users navigating with a keyboard will not be able to see the message. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" padding="48px">
  <Loader statusMessage="Uploading" />
</StorybookComponents.Stack>;
```

### Text
- description: <p>Add a descriptive label below a loader with the <code>text</code> prop. Use it to explain what is happening when additional info is required. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" padding="48px">
  <Loader text="Loading..." />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Load more items
- description: <p>Use loader to indicate that more items are being loaded to a list as a user scrolls down a component or layout, e.g., inside a <code><Table/></code>.</p>
- example: 
```jsx 
() => {
  const containerRef = React.useRef(null);
  const [container, setContainer] = React.useState(null);
  const data = Array.from(Array(10).keys()).map(() => ({
    image: <Image width="42px" height="42px" />,
  }));

  const [records, setRecords] = React.useState(data);

  const columns = [{ title: '', render: row => row.image }];

  const fetchMoreData = () =>
    new Promise(resolve => {
      setTimeout(() => setRecords([...records, ...data]), 2000);
    });

  React.useEffect(() => {
    setContainer(containerRef);
  }, []);

  return (
      <div style={{ maxHeight: '360px', overflowY: 'scroll' }} ref={container}>
        <Card stretchVertically={true} hideOverflow>
          <Table
            data={records}
            columns={columns}
            rowVerticalPadding="tiny"
            loadMore={fetchMoreData}
            infiniteScroll
            hasMore={records.length < 226}
            itemsPerPage={10}
            scrollElement={container && container.current}
            loader={
              <Box align="center" padding="24px 0px">
                <Loader size="small" />
              </Box>
            }
          >
            <TableToolbar>
              <TableToolbar.ItemGroup position="start">
                <TableToolbar.Item>
                  <Text size="small">226 products</Text>
                </TableToolbar.Item>
              </TableToolbar.ItemGroup>
            </TableToolbar>
            <Table.Content />
          </Table>
        </Card>
      </div>
  );
};

```

### Triggered action in process
- description: <p>Add a loader inside of a <code><Button/></code> to inform users that the action has started and is currently being processed.</p>
- example: 
```jsx 
() => {
  const [isLoading, setIsLoading] = React.useState(false);
  return (
    <Box direction="vertical" align="center">
      <CustomModalLayout
        primaryButtonText={isLoading ? <Loader size="tiny" /> : 'Add Member'}
        secondaryButtonText="Cancel"
        onCloseButtonClick={() => {}}
        primaryButtonOnClick={() => {
          if (isLoading) {
            return;
          }
          
          setIsLoading(true);
          setTimeout(() => {
            setIsLoading(false)
          }, 2000)
        }}
        title="Add member"
      >
        <Box height="180px" />
      </CustomModalLayout>
    </Box>
  );
};
```

### Save page changes
- description: <p>Use a loader to indicate that changes a user made on the page are being saved.</p>
- example: 
```jsx 
() => {
  const [isModalOpened, setModalOpened] = React.useState(false);
  const [currentScreen, setCurrentScreen] = React.useState(null);

  const openModal = screen => {
    if (isModalOpened) {
      return;
    }

    setCurrentScreen(screen);
    setModalOpened(true);

    setTimeout(() => {
      setModalOpened(false);
    }, 2000);
  };
  const closeModal = () => setModalOpened(false);

  const renderModalContent = () => <Loader size="large" />;

  return (
    <Page height="760px">
      <Page.Header
        title="Basic Info"
        actionsBar={
          <Box gap="SP2">
            <Button skin="inverted">Cancel</Button>
            <Button onClick={() => openModal('desktop')}>Save</Button>
          </Box>
        }
      />
      <Page.Content>
        <Modal
          screen={currentScreen}
          isOpen={isModalOpened}
          onRequestClose={closeModal}
        >
          {renderModalContent()}
        </Modal>
        <Layout>
          <Cell>
            <Card>
              <Card.Header title="Program details" />
              <Card.Divider />
              <Card.Content>
                <Box height="360px" />
              </Card.Content>
            </Card>
          </Cell>
          <Cell>
            <Page.Footer divider>
              <Page.Footer.End>
                <Box gap="SP2">
                  <Button priority="secondary">Cancel</Button>
                  <Button onClick={() => openModal('desktop')}>Save</Button>
                </Box>
              </Page.Footer.End>
            </Page.Footer>
          </Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};

```


