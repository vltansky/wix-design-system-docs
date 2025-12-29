
## Feature Examples


### Structure
- description: <p>Modal consists of an overlay only and should contain one of the following layouts:</p><li><code><CustomModalLayout/></code></li><li><code><ModalPreviewLayout/></code></li><li><code><AnnouncementModalLayout/></code></li><li><code><ModalMobileLayout/></code></li>
- example: 
```jsx 
() => {
  const [isModalOpened, setModalOpened] = React.useState(false);

  const openModal = () => setModalOpened(true);
  const closeModal = () => setModalOpened(false);

  const renderModalContent = () => (
    <StorybookComponents.Placeholder skin="light" width="600px" height="600px">
      <StorybookComponents.Stack
        flexDirection="column"
        alignItems="center"
        padding="30px"
      >
        <Text light>Modal content goes here.</Text>
        <TextButton onClick={closeModal} underline="always" skin="light">
          Close Modal
        </TextButton>
      </StorybookComponents.Stack>
    </StorybookComponents.Placeholder>
  );

  return (
    <StorybookComponents.Stack>
      <Button onClick={openModal} prefixIcon={<Icons.OpenModal />}>
        Open Modal
      </Button>
      <Modal isOpen={isModalOpened} onRequestClose={closeModal}>
        {renderModalContent()}
      </Modal>
    </StorybookComponents.Stack>
  );
};
```

### Side margins
- description: <p>Control the spacing between the viewport and the modal content by using <code>screen</code> prop. It has 3 options:</p><li><code>full</code> (default) - used with <code><ModalPreviewLayout/></code>.</li><li><code>desktop</code> - used with all major desktop modals.</li><li><code>mobile</code> - used with <code><ModalMobileLayout/></code> component.</li>
- example: 
```jsx 
() => {
  const [isModalOpened, setModalOpened] = React.useState(false);
  const [currentScreen, setCurrentScreen] = React.useState(null);

  const openModal = screen => {
    setCurrentScreen(screen);
    setModalOpened(true);
  };
  const closeModal = () => setModalOpened(false);

  const renderModalContent = () => (
    <StorybookComponents.Placeholder skin="light">
      <StorybookComponents.Stack padding="30px">
        <TextButton onClick={closeModal} underline="always" skin="light">
          Close Modal
        </TextButton>
      </StorybookComponents.Stack>
    </StorybookComponents.Placeholder>
  );

  return (
    <StorybookComponents.Stack>
      <Button
        prefixIcon={<Icons.FullScreen />}
        onClick={() => openModal('full')}
      >
        Full
      </Button>

      <Button
        prefixIcon={<Icons.Desktop />}
        onClick={() => openModal('desktop')}
      >
        Desktop
      </Button>

      <Button prefixIcon={<Icons.Mobile />} onClick={() => openModal('mobile')}>
        Mobile
      </Button>
      <Modal
        screen={currentScreen}
        isOpen={isModalOpened}
        onRequestClose={closeModal}
      >
        {renderModalContent()}
      </Modal>
    </StorybookComponents.Stack>
  );
};
```

### Navigation controls
- description: <p>Add the option to navigate between modals by using the <code>showNavigationPreviousButton</code> and <code>showNavigationNextButton</code> props.</p>
- example: 
```jsx 
() => {
  const content = [
    {
      title: 'Title (Item 1)',
      body: 'Body content (Item 1).',
    },
    {
      title: 'Title (Item 2)',
      body: 'Body content (Item 2).',
    },
    {
      title: 'Title (Item 3)',
      body: 'Body content (Item 3).',
    },
  ];
  const [isModalOpened, setModalOpened] = React.useState(false);
  const [currentContent, setCurrentContent] = React.useState(0);

  const openModal = () => setModalOpened(true);
  const closeModal = () => setModalOpened(false);

  const renderModalContent = () => {
    const { title, body } = content[currentContent];
    return (
      <MessageModalLayout
        onCloseButtonClick={() => closeModal()}
        primaryButtonOnClick={() => closeModal()}
        secondaryButtonOnClick={() => closeModal()}
        primaryButtonText={'Save'}
        secondaryButtonText={'Cancel'}
        title={title}
      >
        <Text>{body}</Text>
      </MessageModalLayout>
    );
  };

  return (
    <StorybookComponents.Stack>
      <Button onClick={openModal} prefixIcon={<Icons.OpenModal />}>
        Open Modal
      </Button>
      <Modal
        isOpen={isModalOpened}
        onRequestClose={closeModal}
        showNavigationPreviousButton
        showNavigationNextButton
        navigationPreviousLabel="Previous"
        navigationNextLabel="Next"
        onNavigationClickPrevious={() =>
          setCurrentContent(
            (currentContent > 0 ? currentContent : content.length) - 1,
          )
        }
        onNavigationClickNext={() =>
          setCurrentContent((currentContent + 1) % content.length)
        }
      >
        {renderModalContent()}
      </Modal>
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Desktop modal with popover elements
- description: <p>By default, modal layouts do not allow content to overflow into the background.</p><p></p><p>Use <code>popoverProps</code>, <code>appendTo</code> and <code>dynamicWidth</code> props to display overlays as intended. For more guidance, read about the <code><Popover/></code> component.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);

  return (
    <Card>
      <Card.Header
        title="Allow using coupons"
        subtitle="Let visitors use coupons to get discounts & special deals."
        suffix={
          <Button
            size="small"
            priority="secondary"
            onClick={() => setShown(true)}
          >
            Apply Coupon
          </Button>
        }
      />
      <Modal
        isOpen={shown}
        onRequestClose={() => setShown(false)}
        shouldCloseOnOverlayClick
        screen="desktop"
      >
        <CustomModalLayout
          primaryButtonText="Apply"
          primaryButtonOnClick={() => setShown(false)}
          secondaryButtonText="Cancel"
          secondaryButtonOnClick={() => setShown(false)}
          onCloseButtonClick={() => setShown(false)}
          title="Apply a coupon"
          overflowY="none"
          content={
            <FormField label="Select coupon">
              <Dropdown
                popoverProps={{
                  appendTo: 'scrollParent',
                  dynamicWidth: 'true',
                }}
                options={[
                  { id: 0, value: 'None' },
                  { id: 1, value: 'SUMMER15' },
                  { id: 2, value: 'BACKTOSCHOOL' },
                  { id: 3, value: 'AUGUST10' },
                  { id: 4, value: 'OUTWITHTHEOLD' },
                ]}
                placeholder="Select from the list"
              />
            </FormField>
          }
        />
      </Modal>
    </Card>
  );
};
```


