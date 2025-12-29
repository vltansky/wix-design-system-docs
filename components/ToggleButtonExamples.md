
## Feature Examples


### Size
- description: <p>Control toggle button size with <code>size</code> prop:</p><li><code>large</code> is best for main actions in a composer.</li><li><code>medium</code> (default) is for main composer toolbars.</li><li><code>small</code> fits into smaller toolbars and UI elements like cards and widgets.</li><li><code>tiny</code> is used in dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="flex-start">
  <ToggleButton labelValue="Large" size="large">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Medium" size="medium">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Small" size="small">
    <Icons.CropRotateSmall />
  </ToggleButton>
  <ToggleButton labelValue="Tiny" size="tiny">
    <Icons.CropRotateSmall />
  </ToggleButton>
</StorybookComponents.Stack>;
```

### Label placement
- description: <p>Position the label with <code>labelPlacement</code> prop:</p><li><code>tooltip</code> (default) - use it in dense layouts and for repetitive intuitive actions that don't need the exposed label, such as making text italic.</li><li><code>end</code> saves vertical space.</li><li><code>bottom</code> saves horizontal space.</li>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="flex-start">
  <ToggleButton labelValue="Tooltip" labelPlacement="tooltip">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="End" labelPlacement="end">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Bottom" labelPlacement="bottom">
    <Icons.CropRotate />
  </ToggleButton>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the appearance of a button with <code>skin</code> prop:</p><li><code>standard</code> (default) is used it in all default cases.</li><li><code>inverted</code> is used when selected actions need additional emphasis.</li><li><code>destructive</code> is best for actions that might have a negative effect, for example, when the microphone is muted.</li><li><code>success</code> is best for actions that have a positive effect, for example when camera is on or screen is shared.</li><li><code>dark</code> is used on colored backgrounds.</li><p></p><p>Note: by design, different skins are only visible when toggle buttons are selected.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ToggleButton labelValue="Standard" skin="standard" selected>
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Inverted" skin="inverted" selected>
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Destructive" skin="destructive" selected>
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Success" skin="success" selected>
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Dark" skin="dark" selected>
    <Icons.CropRotate />
  </ToggleButton>
</StorybookComponents.Stack>;
```

### Shape
- description: <p>Control toggle button form with <code>shape</code> prop:</p><li><code>square</code> (default) is best for composer toolbars and top bars.</li><li><code>round</code> is built in composer sidebars.</li><li><code>pill</code> is for main page layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ToggleButton labelValue="Square" shape="square">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Round" shape="round">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Pill" shape="pill">
    <Icons.CropRotate />
  </ToggleButton>
</StorybookComponents.Stack>;
```

### Border
- description: <p>Turn on a toggle button border using <code>border</code> prop. It is off by default.</p><p></p><p>Use it when the action needs additional emphasis.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ToggleButton labelValue="No border">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="With border" border={true}>
    <Icons.CropRotate />
  </ToggleButton>
</StorybookComponents.Stack>;
```

### State
- description: <p>Control toggle button states with these props:</p><li><code>selected</code> is used when action is set to active.</li><li><code>disabled</code> is used for unavailable actions, when toggle button cannot be clicked or selected.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <ToggleButton labelValue="Default" labelPlacement="bottom">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Selected" selected labelPlacement="bottom">
    <Icons.CropRotate />
  </ToggleButton>
  <ToggleButton labelValue="Disabled" disabled labelPlacement="bottom">
    <Icons.CropRotate />
  </ToggleButton>
</StorybookComponents.Stack>;
```




## Developer Examples


### Custom HTML tag
- description: <p>Render toggle button as any given HTML tag with <code>as</code> prop. For example, it can be rendered as:</p><li><code><a></code> when attributes like href, target, etc., are needed.</li><li><code><Link></code> when props like to, replace, etc. are needed.</li><p></p><p>All attributes will be passed to the rendered HTML tag.</p>
- example: 
```jsx 
() => {
  const ReactRouterLink = (props) => <div {...props} />;
  return (
    <StorybookComponents.Stack>
      <ToggleButton
        as="a"
        href="https://www.wix.com"
        target="_blank"
        labelValue="Native <a/> tag"
        labelPlacement="bottom"
      >
        <Icons.CropRotate />
      </ToggleButton>

      <ToggleButton
        as={ReactRouterLink}
        to="/home"
        labelValue="React Router <Link/> tag"
        labelPlacement="bottom"
      >
        <Icons.CropRotate />
      </ToggleButton>

      <ToggleButton
        as="button"
        onClick={() => alert('You have clicked on a button!')}
        labelValue="Native <button/> tag"
        labelPlacement="bottom"
      >
        <Icons.CropRotate />
      </ToggleButton>
    </StorybookComponents.Stack>
  );
};
```


    


## Common Use Case Examples


### Composer interface
- description: <p>Toggle button is one of the main components used in Wix composers. Use it in:</p><li><ComposerHeader/> for Undo and Redo actions.</li><li><ComposerSidebar/> as built-in button for navigation.</li><li>Any other toolbar to show actions or select states.</li>
- example: 
```jsx 
() => {
  const [selectedSidebar, setSelectedSidebar] = React.useState(0);
  const [publishDate, setPublishDate] = React.useState();

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

  const handleSidebarClick = (id) => {
    setSelectedSidebar(id);
  };

  const handleCloseSidePanel = () => {
    setSelectedSidebar();
  };

  const renderSettingsPanel = () => (
    <SidePanel onCloseButtonClick={handleCloseSidePanel}>
      <SidePanel.Header title="Post Settings"></SidePanel.Header>
      <SidePanel.Content>
        <StorybookComponents.Placeholder>
          <Box
            verticalAlign="middle"
            align="center"
            height="100%"
            width="240px"
          >
            <Text>Settings side panel</Text>
          </Box>
        </StorybookComponents.Placeholder>
      </SidePanel.Content>
    </SidePanel>
  );

  const renderTagPanel = () => (
    <SidePanel onCloseButtonClick={handleCloseSidePanel}>
      <SidePanel.Header title="Tags" />
      <SidePanel.Content>
        <StorybookComponents.Placeholder>
          <Box
            verticalAlign="middle"
            align="center"
            height="100%"
            width="240px"
          >
            <Text>Tags side panel</Text>
          </Box>
        </StorybookComponents.Placeholder>
      </SidePanel.Content>
    </SidePanel>
  );

  const renderCategoryPanel = () => {
    return (
      <SidePanel onCloseButtonClick={handleCloseSidePanel}>
        <SidePanel.Header title="Categories" />
        <SidePanel.Content>
          <StorybookComponents.Placeholder>
            <Box
              verticalAlign="middle"
              align="center"
              height="100%"
              width="240px"
            >
              <Text>Categories side panel</Text>
            </Box>
          </StorybookComponents.Placeholder>
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
                    <Text>Composer content</Text>
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

### Video stream
- description: <p>Use toggle buttons in control toolbars to enable/disable actions like screen sharing.</p>
- example: 
```jsx 
() => {
  const renderToggleButton = (icon, skin, selected, labelValue) => (
    <ToggleButton
      shape="round"
      selected={selected}
      skin={skin}
      labelValue={labelValue}
      labelPlacement="bottom"
    >
      {icon}
    </ToggleButton>
  );
  return (
    <Box direction="vertical" gap="SP2">
      <StorybookComponents.Placeholder>
        <Box verticalAlign="middle" align="center" height="240px">
          <Text>Video content</Text>
        </Box>
      </StorybookComponents.Placeholder>

      <Box align="space-between">
        <Box gap="SP2" width="180px">
          {renderToggleButton(<Icons.Microphone />, '', false, 'Mute')}
          {renderToggleButton(<Icons.VideoCamera />, '', false, 'Stop video')}
        </Box>
        <Box gap="SP2" width="180px" align="center">
          {renderToggleButton(
            <Icons.Desktop />,
            'success',
            true,
            'Share screen',
          )}
        </Box>
        <Box gap="SP2" width="180px" align="right">
          {renderToggleButton(<Icons.Exit />, 'destructive', true, 'Leave')}
        </Box>
      </Box>
    </Box>
  );
};
```

### Switch between states
- description: <p>Use toggle buttons as selectors that switch between two states.</p>
- example: 
```jsx 
() => {
  const [selectedButtonToast, setSelectedButtonToast] = React.useState(false);
  const [selectedButtonPasta, setSelectedButtonPasta] = React.useState(false);
  const [selectedButtonPaella, setSelectedButtonPaella] = React.useState(false);

  return (
    <Box gap="SP4">
      <Proportion aspectRatio={1}>
        <MediaOverlay skin="gradient" media="FoodExample1.jpg">
          <MediaOverlay.Content placement="top-start" visible="always">
            <ToggleButton
              shape="pill"
              labelValue={selectedButtonToast ? 'Favorite' : 'Mark as Favorite'}
              size="tiny"
              selected={selectedButtonToast}
              onClick={() => setSelectedButtonToast(!selectedButtonToast)}
            >
              {selectedButtonToast ? (
                <Icons.FavoriteFilled />
              ) : (
                <Icons.Favorite />
              )}
            </ToggleButton>
          </MediaOverlay.Content>
          <MediaOverlay.Content placement="bottom-start" visible="always">
            <Text size="small" weight="normal" light>
              Breakfast toast
            </Text>
          </MediaOverlay.Content>
        </MediaOverlay>
      </Proportion>
      <Proportion aspectRatio={1}>
        <MediaOverlay skin="gradient" media="FoodExample2.jpg">
          <MediaOverlay.Content placement="top-start" visible="always">
            <ToggleButton
              shape="pill"
              labelValue={selectedButtonPasta ? 'Favorite' : 'Mark as Favorite'}
              size="tiny"
              selected={selectedButtonPasta}
              onClick={() => setSelectedButtonPasta(!selectedButtonPasta)}
            >
              {selectedButtonPasta ? (
                <Icons.FavoriteFilled />
              ) : (
                <Icons.Favorite />
              )}
            </ToggleButton>
          </MediaOverlay.Content>
          <MediaOverlay.Content placement="bottom-start" visible="always">
            <Text size="small" weight="normal" light>
              Lemon Ricotta Pasta
            </Text>
          </MediaOverlay.Content>
        </MediaOverlay>
      </Proportion>
      <Proportion aspectRatio={1}>
        <MediaOverlay skin="gradient" media="FoodExample3.jpg">
          <MediaOverlay.Content placement="top-start" visible="always">
            <ToggleButton
              shape="pill"
              labelValue={
                selectedButtonPaella ? 'Favorite' : 'Mark as Favorite'
              }
              size="tiny"
              selected={selectedButtonPaella}
              onClick={() => setSelectedButtonPaella(!selectedButtonPaella)}
            >
              {selectedButtonPaella ? (
                <Icons.FavoriteFilled />
              ) : (
                <Icons.Favorite />
              )}
            </ToggleButton>
          </MediaOverlay.Content>
          <MediaOverlay.Content placement="bottom-start" visible="always">
            <Text size="small" weight="normal" light>
              Spanish Paella
            </Text>
          </MediaOverlay.Content>
        </MediaOverlay>
      </Proportion>
    </Box>
  );
};
```


