
## Feature Examples


### Structure
- description: <p>Use the <code>SegmentedToggle</code> to wrap a set of related options. It should be used to present two to five options. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SegmentedToggle defaultSelected="option1">
    <SegmentedToggle.Button value="option1">Option 1</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option2">Option 2</SegmentedToggle.Button>
  </SegmentedToggle>
  <SegmentedToggle defaultSelected="option1">
    <SegmentedToggle.Button value="option1">Option 1</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option2">Option 2</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option3">Option 3</SegmentedToggle.Button>
  </SegmentedToggle>
  <SegmentedToggle defaultSelected="option1">
    <SegmentedToggle.Button value="option1">Option 1</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option2">Option 2</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option3">Option 3</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option4">Option 4</SegmentedToggle.Button>
  </SegmentedToggle>
</StorybookComponents.Stack>;
```

### Child items
- description: <p>Each button should be set as a child item of the component. </p><li>Use <code><SegmentedToggle.Button/></code>  for text labels.</li><li>Use <code><SegmentedToggle.Icon/></code>  when short on space, or when there’s enough context to make the option distinguishable only using icons.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SegmentedToggle defaultSelected="option1">
    <SegmentedToggle.Button value="option1">Option 1</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option2">Option 2</SegmentedToggle.Button>
  </SegmentedToggle>
  <SegmentedToggle defaultSelected="option1">
    <SegmentedToggle.Icon value="option1" tooltipText="Option 1">
      <Icons.LockLocked />
    </SegmentedToggle.Icon>
    <SegmentedToggle.Icon value="option2" tooltipText="Option 2">
      <Icons.LockUnlocked />
    </SegmentedToggle.Icon>
  </SegmentedToggle>
</StorybookComponents.Stack>;
```

### Size
- description: <p>Adjust the size of the component with the <code>size</code> property. </p><li>Use  <code>medium</code> as the default in all forms, card or page layouts.</li><li>Use <code>small</code> in compact environments or other dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SegmentedToggle defaultSelected="option1" size="medium">
    <SegmentedToggle.Button value="option1">Medium</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option2">Medium</SegmentedToggle.Button>
  </SegmentedToggle>
  <SegmentedToggle defaultSelected="option1" size="small">
    <SegmentedToggle.Button value="option1">Small</SegmentedToggle.Button>
    <SegmentedToggle.Button value="option2">Small</SegmentedToggle.Button>
  </SegmentedToggle>
</StorybookComponents.Stack>;
```

### Prefix icon
- description: <p>Add an icon next to the option label using <code><SegmentedToggle.Button/></code> to make it easier to scan.</p>
- example: 
```jsx 
<SegmentedToggle defaultSelected="option1">
  <SegmentedToggle.Button prefixIcon={<Icons.LockLocked />} value="option1">
    Option 1
  </SegmentedToggle.Button>
  <SegmentedToggle.Button prefixIcon={<Icons.LockUnlocked />} value="option2">
    Option 2
  </SegmentedToggle.Button>
</SegmentedToggle>;
```

### Disabled options
- description: <p>Disable buttons with the <code>disabled</code> prop. Use it to disable the whole composite. </p>
- example: 
```jsx 
<SegmentedToggle defaultSelected="option1" disabled>
  <SegmentedToggle.Button value="option1">Option</SegmentedToggle.Button>
  <SegmentedToggle.Button value="option2">Option</SegmentedToggle.Button>
</SegmentedToggle>;
```




## Developer Examples


### Selection control
- description: <p>The component value can be controlled manually using the <code>selected</code> prop.</p>
- example: 
```jsx 
() => {
  const [selectedValue, setSelectedValue] = React.useState('option1');
  const onClick = (_, value) => setSelectedValue(value);

  return (
    <FormField label="Alignment">
      <Box>
        <SegmentedToggle selected={selectedValue} onClick={onClick}>
          <SegmentedToggle.Icon value="option1" tooltipText="Left align">
            <Icons.TextAlignLeft />
          </SegmentedToggle.Icon>
          <SegmentedToggle.Icon value="option2" tooltipText="Center align">
            <Icons.TextAlignCenter />
          </SegmentedToggle.Icon>
          <SegmentedToggle.Icon value="option3" tooltipText="Right align">
            <Icons.TextAlignRight />
          </SegmentedToggle.Icon>
          <SegmentedToggle.Icon value="option4" tooltipText="Justify">
            <Icons.TextJustify />
          </SegmentedToggle.Icon>
        </SegmentedToggle>
      </Box>
    </FormField>
  );
};
```


    


## Common Use Case Examples


### Settings panel
- description: <p>Use a segmented toggle to let users control element settings.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');
  return (
    <SidePanel maxHeight="576px" width="288px" skin="floating">
      <SidePanel.Header title="Text Box Settings" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField label="Description">
            <InputArea
              placeholder="Collapsible text is great for longer section titles and descriptions."
              size="small"
              rows={3}
              maxLength={300}
              hasCounter
              resizable
              value={value}
              onChange={(e) => setValue(e.target.value)}
            />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="What does the button do?">
            <SegmentedToggle size="small" defaultSelected="Open">
              <SegmentedToggle.Button value="Open">
                Expand
              </SegmentedToggle.Button>
              <SegmentedToggle.Button value="Closed">
                Link
              </SegmentedToggle.Button>
            </SegmentedToggle>
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FormField label="Link button text">
            <Input size="small" placeholder="Link to full article" />
          </FormField>
        </SidePanel.Field>
      </SidePanel.Content>
    </SidePanel>
  );
};
```

### Switch between views
- description: <p>Use segmented toggles to let users switch between different layouts, such as between a grid or a list view. </p>
- example: 
```jsx 
() => {
  const VIEW_TYPE = {
    listView: 'listView',
    tileView: 'tileView',
  };
  const [viewType, setViewType] = React.useState(VIEW_TYPE.listView);

  const changeViewType = (_, value) => setViewType(value);

  const ActionsCell = (
    <TableActionCell
      primaryAction={{
        text: 'Edit',
        skin: 'standard',
        onClick: () => {},
      }}
      secondaryActions={[
        {
          text: 'Move',
          icon: <Icons.MoveToSmall />,
          onClick: () => {},
        },
        {
          text: 'Mark as sold out',
          icon: <Icons.FoodOutOfStockSmall />,
          onClick: () => {},
        },
        {
          text: 'Hide',
          icon: <Icons.HiddenSmall />,
          onClick: () => {},
        },
        {
          text: 'Archive',
          icon: <Icons.ArchiveSmall />,
          onClick: () => {},
        },
      ]}
      numOfVisibleSecondaryActions={0}
    />
  );

  const ListView = () => [
    <TableListItem
      key="1"
      draggable
      showDivider
      options={[
        {
          value: <Image src="FoodExample1.jpg" width="90px" height="52px" />,
          width: '90px',
        },
        { value: <Text>French toast</Text> },
        { value: <Text>$8.00</Text> },
        {
          value: ActionsCell,
        },
      ]}
    />,
    <TableListItem
      key="2"
      draggable
      showDivider
      options={[
        {
          value: <Image src="FoodExample2.jpg" width="90px" height="52px" />,
          width: '90px',
        },
        { value: <Text>House pasta</Text> },
        { value: <Text>$27.00</Text> },
        {
          value: ActionsCell,
        },
      ]}
    />,
    <TableListItem
      key="3"
      draggable
      options={[
        {
          value: <Image src="FoodExample3.jpg" width="90px" height="52px" />,
          width: '90px',
        },
        { value: <Text>Paella</Text> },
        { value: <Text>$18.00</Text> },
        {
          value: ActionsCell,
        },
      ]}
    />,
  ];

  const Tile = ({ media, title }) => (
    <Proportion aspectRatio={1}>
      <MediaOverlay skin="gradient" media={media}>
        <MediaOverlay.Content placement="top-end" visible="hover">
          <IconButton priority="secondary" skin="inverted" size="tiny">
            <Icons.Edit />
          </IconButton>
        </MediaOverlay.Content>
        <MediaOverlay.Content placement="bottom-start" visible="always">
          <Text size="small" weight="normal" light>
            {title}
          </Text>
        </MediaOverlay.Content>
      </MediaOverlay>
    </Proportion>
  );

  const TileView = () => (
    <Card.Content>
      <Layout cols={4}>
        <Tile media="FoodExample1.jpg" title="French toast" />
        <Tile media="FoodExample2.jpg" title="House pasta" />
        <Tile media="FoodExample3.jpg" title="Paella" />
      </Layout>
    </Card.Content>
  );

  return (
    <Card>
      <Card.Header
        title="Dishes"
        suffix={
          <Box gap="18px" verticalAlign="middle">
            <SegmentedToggle selected={viewType} onClick={changeViewType}>
              <SegmentedToggle.Icon
                value={VIEW_TYPE.tileView}
                tooltipText="Tile view"
              >
                <Icons.LayoutGallery />
              </SegmentedToggle.Icon>
              <SegmentedToggle.Icon
                value={VIEW_TYPE.listView}
                tooltipText="List view"
              >
                <Icons.LayoutList />
              </SegmentedToggle.Icon>
            </SegmentedToggle>
            <Button size="small" prefixIcon={<Icons.Add />}>
              Add Dish
            </Button>
          </Box>
        }
      />
      <Card.Divider />
      {viewType === VIEW_TYPE.listView ? <ListView /> : <TileView />}
    </Card>
  );
};
```

### Status toggle
- description: <p>Use segmented toggles to let users control an item's status. </p><p></p>
- example: 
```jsx 
() => {
  const [registrationOrigin, setRegistrationOrigin] = React.useState(1);
  return (
    <Card>
      <Card.Header title="Guest registration" />
      <Card.Divider />
      <Card.Content>
        <Layout cols={1}>
          <Box direction="vertical" gap="12px">
            <FormField label="Where do guests register?">
              <RadioGroup
                value={registrationOrigin}
                onChange={setRegistrationOrigin}
              >
                <RadioGroup.Radio value={1}>
                  On my Wix Events registration page
                </RadioGroup.Radio>
                <RadioGroup.Radio value={2}>
                  On a different page or website
                </RadioGroup.Radio>
                <RadioGroup.Radio value={3}>
                  Guest don't need to register
                </RadioGroup.Radio>
              </RadioGroup>
            </FormField>
          </Box>
          <Divider />
          <FormField label="Registration for this event is:">
            <Box>
              <SegmentedToggle defaultSelected="option1">
                <SegmentedToggle.Button
                  prefixIcon={<Icons.LockUnlocked />}
                  value="option1"
                >
                  Open
                </SegmentedToggle.Button>
                <SegmentedToggle.Button
                  prefixIcon={<Icons.LockLocked />}
                  value="option2"
                >
                  Closed
                </SegmentedToggle.Button>
              </SegmentedToggle>
            </Box>
          </FormField>
        </Layout>
      </Card.Content>
    </Card>
  );
};
```


