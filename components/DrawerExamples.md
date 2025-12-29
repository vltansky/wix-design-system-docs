
## Feature Examples


### Resizeable
- description: <p>Control if a handle is shown in the component header with <code>resizable</code> prop. When enabled, it allows user to expand or collapse the drawer with a swipe gesture. </p>
- example: 
```jsx 
() => {
  const [config, setConfig] = React.useState({
    backdrop: true,
    margin: true,
    dismissible: true,
  });
  const [open, setOpen] = React.useState(false);
  const [resizable, setResizable] = React.useState(true);

  const openDrawer = (isResizable) => {
    setResizable(isResizable);
    setOpen(true);
  };

  return (
    <Box padding="20px" gap="20px" direction="vertical">
      <Box gap="10px">
        <Button onClick={() => openDrawer(true)}>Open resizable drawer</Button>
        <Button onClick={() => openDrawer(false)}>Open non-resizable drawer</Button>
      </Box>

      <Drawer
        open={open}
        onClose={() => setOpen(false)}
        resizable={resizable}
        backdrop={config.backdrop}
        margin={config.margin}
        dismissible={config.dismissible}
      >
        <Box padding="20px" gap="20px" direction="vertical">
          <StorybookComponents.Placeholder height="200px">
            <Text size="medium" weight="normal">
              {resizable ? 'Resizable drawer, with handle at the top' : 'Non-resizable drawer'}
            </Text>
          </StorybookComponents.Placeholder>
          <Button onClick={() => setOpen(false)}>Close Drawer</Button>
        </Box>
      </Drawer>
    </Box>
  );
};
```

### Backdrop
- description: <p>Control whether the drawer displays a <code>backdrop</code> using the backdrop property. By default, clicking the backdrop will close the drawer.</p><p></p><p>When the backdrop is disabled, you can allow users to interact with the content behind the drawer by turning off the <code>renderBackdrop</code> property. When this property is off, make sure to provide alternative ways to close the drawer so users don’t get trapped in it.</p>
- example: 
```jsx 
() => {
  const [config, setConfig] = React.useState({
    margin: true,
    dismissible: true,
  });
  const [open, setOpen] = React.useState(false);
  const [backdrop, setBackdrop] = React.useState(true);

  const openDrawer = (withBackdrop) => {
    setBackdrop(withBackdrop);
    setOpen(true);
  };

  return (
    <Box padding="20px" gap="20px" direction="vertical">
      <Box gap="10px">
        <Button onClick={() => openDrawer(true)}>Open drawer with backdrop</Button>
        <Button onClick={() => openDrawer(false)}>Open drawer without backdrop</Button>
      </Box>

      <Drawer
        open={open}
        onClose={() => setOpen(false)}
        backdrop={backdrop}
        margin={config.margin}
        dismissible={config.dismissible}
      >
        <Box padding="20px" gap="20px" direction="vertical">
          <StorybookComponents.Placeholder height="200px">
            <Text size="medium" weight="normal">
              {backdrop ? 'Drawer with backdrop' : 'Drawer without backdrop'}
            </Text>
          </StorybookComponents.Placeholder>
          <Button onClick={() => setOpen(false)}>Close Drawer</Button>
        </Box>
      </Drawer>
    </Box>
  );
};
```

### Margin
- description: <p>Control if the drawer has a margin around it with a <code>margin</code> prop. The size of it is fixed and varies per different themes.</p>
- example: 
```jsx 
() => {
  const [config, setConfig] = React.useState({
    backdrop: true,
    dismissible: true,
  });
  const [open, setOpen] = React.useState(false);
  const [margin, setMargin] = React.useState(true);

  const openDrawer = (withMargin) => {
    setMargin(withMargin);
    setOpen(true);
  };

  return (
    <Box padding="20px" gap="20px" direction="vertical">
      <Box gap="10px">
        <Button onClick={() => openDrawer(true)}>Open drawer with margin</Button>
        <Button onClick={() => openDrawer(false)}>Open drawer without margin</Button>
      </Box>

      <Drawer
        open={open}
        onClose={() => setOpen(false)}
        margin={margin}
        backdrop={config.backdrop}
        dismissible={config.dismissible}
      >
        <Box padding="20px" gap="20px" direction="vertical">
          <StorybookComponents.Placeholder height="200px">
            <Text size="medium" weight="normal">
              {margin ? 'Drawer with margin' : 'Drawer without margin'}
            </Text>
          </StorybookComponents.Placeholder>
          <Button onClick={() => setOpen(false)}>Close Drawer</Button>
        </Box>
      </Drawer>
    </Box>
  );
};
```

### Header
- description: <p>Add header with action when needed. Drawer content is a <code>react.node</code>, so any content can be placed inside of it. </p><p></p><p>However, when adding a header, stick to the pattern that the close button is on the left, title is in the center and additional actions are on the right side.</p>
- example: 
```jsx 
() => {
  const [open, setOpen] = React.useState(false);

  return (
    <Box padding="20px">
      <Button onClick={() => setOpen(true)}>Open drawer</Button>

      <Drawer
        open={open}
        onClose={() => setOpen(false)}
      >
        <Box direction="vertical">
          <Box
            align="center"
            verticalAlign="middle"
            padding="12px 16px"
            backgroundColor="white"
          >
            <Box width="40px">
              <IconButton
                priority="tertiary"
                skin="dark"
                size="medium"
                onClick={() => setOpen(false)}
              >
                <Icons.X />
              </IconButton>
            </Box>

            <Box flexGrow={1} align="center">
              <Heading size="small">Title</Heading>
            </Box>

            <Box width="40px" align="right">
              <IconButton
                priority="tertiary"
                skin="dark"
                size="medium"
                onClick={() => {
                  console.log('Confirmed');
                  setOpen(false);
                }}
              >
                <Icons.Check />
              </IconButton>
            </Box>
          </Box>

          {/* Content */}
          <Box padding="20px" direction="vertical" gap="20px">
            <StorybookComponents.Placeholder height="300px">
              <Text size="medium" weight="normal">
                Content goes here
              </Text>
            </StorybookComponents.Placeholder>
          </Box>
        </Box>
      </Drawer>
    </Box>
  );
};
```




    


