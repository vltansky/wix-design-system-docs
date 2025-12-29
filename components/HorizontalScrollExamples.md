
## Feature Examples


### Gradient color
- description: <p>Use <code>gradientColor</code> prop to make items transition smoother with the background.</p>
- example: 
```jsx 
<Box width="200px">
  <HorizontalScroll gradientColor="#FF0000">
    <Box height="24px" gap="SP2">
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
    </Box>
  </HorizontalScroll>
</Box>

```

### Gradient width
- description: <p>Use <code>gradientWidth</code> prop to adjust the length of the transition gradient.</p>
- example: 
```jsx 
<Box width="200px">
  <HorizontalScroll gradientColor="#FF0000" gradientWidth="120px">
    <Box height="24px" gap="SP2">
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
    </Box>
  </HorizontalScroll>
</Box>

```

### Scroll button size
- description: <p>Use <code>scrollButtonSize</code> prop to change icon button size.</p><p>Choose between:</p><li><code>large</code></li><li><code>medium</code></li><li><code>small</code></li><li><code>tiny</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box width="200px">
    <HorizontalScroll scrollButtonSize="large">
      <Box height="42px" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
  <Box width="200px">
    <HorizontalScroll scrollButtonSize="medium">
      <Box height="36px" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
    <Box width="200px">
    <HorizontalScroll scrollButtonSize="small">
      <Box height="30" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
    <Box width="200px">
    <HorizontalScroll scrollButtonSize="tiny">
      <Box height="24px" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
</StorybookComponents.Stack>;

```

### Scroll button skin
- description: <p>Use <code>scrollButtonSkin</code> to choose from the following icon button skins:</p><li><code>standard</code></li><li><code>light</code></li><li><code>dark</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box width="200px">
    <HorizontalScroll scrollButtonSkin="standard">
      <Box height="24px" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
  <Box width="200px">
    <HorizontalScroll gradientColor="#000" scrollButtonSkin="light">
      <Box height="24px" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
  <Box width="200px">
    <HorizontalScroll scrollButtonSkin="dark">
      <Box height="24px" gap="SP2">
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
        <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      </Box>
    </HorizontalScroll>
  </Box>
</StorybookComponents.Stack>

```

### Scroll debounce
- description: <p>Change the debounce time to limit scroll even rate, by using the <code>scrollDebounce</code> prop.</p>
- example: 
```jsx 
<Box width="200px">
  <HorizontalScroll scrollDebaounce="10">
    <Box height="24px" gap="SP2">
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
    </Box>
  </HorizontalScroll>
</Box>

```

### Scroll distance
- description: <p>Change the number of pixels the scrollable content moves per button press by using <code>scrollDistance</code> prop.</p>
- example: 
```jsx 
<Box width="200px">
  <HorizontalScroll scrollDistance="2">
    <Box height="24px" gap="SP2">
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
      <StorybookComponents.Placeholder>Item</StorybookComponents.Placeholder>
    </Box>
  </HorizontalScroll>
</Box>

```




    


## Common Use Case Examples


### Tabs
- description: <p><HorizontallScroll /> is commonly used to scroll a list of tabs which is too wide for the parent container. </p>
- example: 
```jsx 
() => {
  const [activeId, setActiveId] = React.useState(2);

  return (
    <SidePanel width="500px">
      <SidePanel.Header title="Add elements"></SidePanel.Header>
      <SidePanel.Content noPadding>
        <HorizontalScroll>
          <Tabs
            size="small"
            scrollOnOverflow
            activeId={activeId}
            onClick={(value) => setActiveId(value.id)}
            items={[
              { id: 1, title: 'For you', prefix: <Icons.HomeSmall /> },
              { id: 2, title: 'Stickers', prefix: <Icons.BookmarkSmall /> },
              { id: 3, title: 'Text', prefix: <Icons.TextSmall /> },
              { id: 4, title: 'Images', prefix: <Icons.ImageSmall /> },
              { id: 4, title: 'Icons', prefix: <Icons.HeartSmall /> },
              { id: 5, title: 'Shapes', prefix: <Icons.FavoriteSmall /> },
              {
                id: 6,
                title: 'Designers images',
                prefix: <Icons.ManagePhotosSmall />,
              },
            ]}
          />
        </HorizontalScroll>
        <Divider></Divider>
        <HorizontalScroll>
          <Box padding="24px" gap="SP2">
            <ToggleButton
              border={true}
              selected
              interactive={false}
              size="small"
              labelValue="All"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              size="small"
              border={true}
              labelPlacement="tooltip"
              labelValue="Birthday"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Decorative"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Abstract"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Wedding"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Flowers"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Love"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Scribbles"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Christmas"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Lifestyle"
              shape="pill"
              skin="inverted"
            />
            <ToggleButton
              border={true}
              size="small"
              labelValue="Baby"
              shape="pill"
              skin="inverted"
            />

            <ToggleButton
              border={true}
              size="small"
              labelValue="Frames"
              shape="pill"
              skin="inverted"
            />
          </Box>
        </HorizontalScroll>
      </SidePanel.Content>
    </SidePanel>
  );
};

```


