
## Feature Examples


### Type
- description: <p>Control stepper appearance with <code>type</code> prop:</p><li>Use <code>circle</code> (default) in all common cases.</li><li>Use <code>text</code> in dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Stepper
    type="circle"
    steps={[{ text: 'Circle' }, { text: 'Circle' }, { text: 'Circle' }]}
  />
  <Stepper
    type="text"
    steps={[{ text: 'Text' }, { text: 'Text' }, { text: 'Text' }]}
  />
</StorybookComponents.Stack>;
```

### Fit mode
- description: <p>Control how component fits in the parent container with <code>fit</code> prop:</p><li>Use <code>compact</code> (default) to set the stepper width based on its content.</li><li>Use <code>stretched</code> to fill in all available space.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Stepper
    fit="compact"
    steps={[{ text: 'Compact' }, { text: 'Compact' }, { text: 'Compact' }]}
  />
  <Stepper
    fit="stretched"
    steps={[
      { text: 'Stretched' },
      { text: 'Stretched' },
      { text: 'Stretched' },
    ]}
  />
</StorybookComponents.Stack>;
```

### States
- description: <p>Control the state of each step individually with <code>type</code> prop:</p><li>Use <code>normal</code> (default) for non completed steps.</li><li>Use <code>completed</code> for previously completed steps.</li><li>Use <code>error</code> for steps with incomplete information or other issues.</li><li>Use <code>disabled</code> to indicate that step cannot be interacted with at a given moment.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Stepper
    steps={[
      { text: 'Normal', type: 'normal' },
      { text: 'Completed', type: 'completed' },
      { text: 'Error', type: 'error' },
      { text: 'Disabled', type: 'disabled' },
    ]}
  />
  <Stepper
    type="text"
    steps={[
      { text: 'Normal', type: 'normal' },
      { text: 'Completed', type: 'completed' },
      { text: 'Error', type: 'error' },
      { text: 'Disabled', type: 'disabled' },
    ]}
  />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Multi-step flow
- description: <p>Split a long form into steps and demonstrate the user’s progress.</p><p></p><p>Use linear or nonlinear Stepper logic for navigation based on your form content:</p><li>In linear logic, users cannot go back to previous steps or check future steps. Disable steps that they cannot navigate to.</li><li>In nonlinear logic, users can freely move across all steps.</li>
- example: 
```jsx 
() => {
  const [activeStep, setActiveStep] = React.useState(0);

  return (
    <CustomModalLayout
      title="Create your loyalty program"
      showFooterDivider
      showHeaderDivider
      primaryButtonText="Next"
      secondaryButtonText="Cancel"
    >
      <Layout>
        <Cell span={12}>
          <Stepper
            activeStep={0}
            onClick={(step) => setActiveStep(step)}
            steps={[
              { text: 'Brand your program' },
              { text: 'Set points' },
              { text: 'Set rewards', type: 'disabled' },
              { text: 'Add description', type: 'disabled' },
            ]}
          />
        </Cell>
        <Cell span={12}>
          <Divider />
        </Cell>
        <Cell span={6}>
          <FormField labelSize="small" label="Program name">
            <Input placeholder="" />
          </FormField>
        </Cell>
        <Cell span={6}>
          <FormField labelSize="small" label="Points name">
            <Input placeholder="" />
          </FormField>
        </Cell>
        <Cell span={6}>
          <FormField labelSize="small" label="Short description">
            <InputArea
              placeholder="Add more details about your program"
              rows={3}
              hasCounter
              resizable
            />
          </FormField>
        </Cell>
        <Cell span={6}>
          <Box width="72px">
            <FormField labelSize="small" label="Points icon">
              <AddItem theme="image" tooltipContent="Pick points icon">
                Add Item
              </AddItem>
            </FormField>
          </Box>
        </Cell>
      </Layout>
    </CustomModalLayout>
  );
};
```

### Composers
- description: <p>Use stepper in composer header to split a complex flow into smaller steps.</p>
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
        render: (row) => row.name,
        width: '40%',
      },
      {
        title: 'Email',
        render: (row) => row.email,
        width: '30%',
      },
      {
        title: 'Phone',
        render: (row) => row.phone,
        width: '20%',
      },
      {
        render: (row) => (
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
              onClick={(step) => setActiveStep(step)}
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


