
## Feature Examples


### Background
- description: Define a gallery item's background using one of the following:<br/>
        &emsp;- `backgroundImageUrl` - use it to pass a link to the background image source file.<br/>
        &emsp;- `backgroundImageNode` - use it to pass a custom component as a background.
- example: 
```jsx 

<StorybookComponents.Stack>
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
  />
  <CardGalleryItem
    backgroundImageNode=<Image height="100%" />
    primaryActionProps={{
      label: 'Button',
    }}
  />
  <CardGalleryItem
    backgroundImageNode=<FillPreview fill="linear-gradient(45deg, rgba(14,0,255,1) 0%, rgba(0,212,255,1) 80%)" />
    primaryActionProps={{
      label: 'Button',
    }}
  />
</StorybookComponents.Stack>;

```

### Image placement 
- description: <p>Specify the placement of the background image using one of the following:</p><p>- <code>top</code> (default) - Places the background image on top of the footer, as a <code><MediaOverlay/></code>.</p><p>- <code>side</code> - Places the image in the footer, to the left of the title/subtitle.</p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    title="Title"
    imagePlacement="top"
  />
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{}}
    title="Title"
    imagePlacement="side"
  />
</StorybookComponents.Stack>;
```

### Title
- description: Give more context to a card with following props:<br/>
        &emsp;- `title` - use it for a short and descriptive card title.<br/>
        &emsp;- `subtitle` - use it for a short caption to provide more narrative.
- example: 
```jsx 

<StorybookComponents.Stack width="200px">
  <CardGalleryItem 
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    title="Title"
    subtitle="Subtitle"
  />
</StorybookComponents.Stack>;

```

### Badge
- description: Emphasise item status with a `badge`. Use it to promote new items or highlight ones that require attention.
- example: 
```jsx 

<StorybookComponents.Stack width="200px">
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    badge={<Badge skin="standard">Badge</Badge>}
  />
</StorybookComponents.Stack>;

```

### Actions
- description: Define primary and secondary actions for an item with `primaryActionProps` and `secondaryActionProps`. 
        This component is an interactive element so primary action is mandatory, while the secondary button is optional.
- example: 
```jsx 

<StorybookComponents.Stack width="400px">
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    secondaryActionProps={{
      label: 'Text Button',
    }}
  />
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
      disabled: true,
      disabledMessage: 'Message explaining the status',
    }}
    secondaryActionProps={{
      label: 'Text Button',
    }}
  />
</StorybookComponents.Stack>;

```

### Settings menu
- description: Allow users to act on a specific item by providing a settings menu.
        Popover menu can contain any required number of actions inside of it.
- example: 
```jsx 

```

### Size
- description: <p>Control the size of the card. It supports 2 sizes:</p><p></p><p>- <code>small</code>. Use this size if the card is stretched to less than 200px.</p><p></p><p>- <code>medium</code> (default). This size is supposed to be used if the card is stretched to more than or equal 200px in the container.</p><p></p><p>Note that if <code>imagePlacement="side"</code> is enabled, the size prop will change the size of the image.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box width="198px">
    <CardGalleryItem
      backgroundImageUrl="example.jpg"
      size="small"
      primaryActionProps={{
        label: 'Edit',
      }}
      title="Title"
      subtitle="Subtitle"
    />
  </Box>
  <Box width="300px">
    <CardGalleryItem
      backgroundImageUrl="example.jpg"
      size="medium"
      primaryActionProps={{
        label: 'Edit',
      }}
      title="Title"
      subtitle="Subtitle"
    />
  </Box>
  <Box width="300px">
 <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{}}
    title="Title"
   size="small"
    imagePlacement="side"
  />
</Box>
  <Box width="300px">
 <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{}}
    title="Title"
   size="medium"
    imagePlacement="side"
  />
</Box>
</StorybookComponents.Stack>;
```

### Suffix
- description: <p>Define a component (commonly icon) to be added to the footer. Use <code>showSuffixOnHover</code> to make it appear only when hovering over the card.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    size="medium"
    primaryActionProps={{
      label: 'Edit',
    }}
    title="Title"
    subtitle="Subtitle"
    suffix={<Icons.Home />}
  />
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    size="medium"
    primaryActionProps={{
      label: 'Edit',
    }}
    title="Title"
    subtitle="Subtitle"
    suffix={<Icons.Home />}
    showSuffixOnHover
  />
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the look of the card border with <code>skin</code> prop.</p><p>- <code>standard</code> (default) shows a shadow around the card</p><p>- <code>outlined</code> gives a one pixel border around the card</p>
- example: 
```jsx 
<StorybookComponents.Stack width="400px" flexDirection="column">
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    title="Title"
    skin="standard"
    imagePlacement="top"
  />
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{}}
    title="Title"
    skin="standard"
    imagePlacement="side"
  />
    <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    title="Title"
    skin="outlined"
    imagePlacement="top"
  />
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{}}
    title="Title"
    skin="outlined"
    imagePlacement="side"
  />
</StorybookComponents.Stack>;
```

### Skin visibility
- description: <p>Control if the <code>skin</code> should be visible at all times or only on hover with <code>skinVisibility</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="400px" flexDirection="column">
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{
      label: 'Button',
    }}
    title="Title"
    skinVisibility
    skin="standard"
    imagePlacement="top"
  />
  <CardGalleryItem
    backgroundImageUrl="example.jpg"
    primaryActionProps={{}}
    title="Title"
    skinVisibility
    skin="standard"
    imagePlacement="side"
  />

</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Product list
- description: Use `<CardGalleryItem/>` to list down visual items, such as dishes, blog posts, products or their collections.
        These lists are commonly accompanied by an `<AddItem/>` component at the end of the list which allows users to add a new item to the grid.
- example: 
```jsx 

() => {
  const renderCardGalleryItem = ({ imageSrc, title, subtitle, badge }) => (
      <CardGalleryItem
        backgroundImageUrl={imageSrc}
        primaryActionProps={{
          label: 'Edit',
        }}
        badge={badge}
        title={<Text weight="bold">{title}</Text>}
        subtitle={subtitle}
        settingsMenu={
          <PopoverMenu
            triggerElement={({ toggle, close }) => (
              <IconButton
                onClick={toggle}
                onMouseLeave={close}
                skin="light"
                size="small"
                priority="secondary"
              >
                <Icons.More />
              </IconButton>
            )}
          >
            <PopoverMenu.MenuItem
              text="Dublicate"
              prefixIcon={<Icons.Duplicate />}
            />
            <PopoverMenu.MenuItem
              text="Move to"
              prefixIcon={<Icons.MoveTo />}
            />
            <PopoverMenu.MenuItem
              text="Sold out"
              prefixIcon={<Icons.FoodOutOfStock />}
            />
            <PopoverMenu.MenuItem text="Hide" prefixIcon={<Icons.Hidden />} />
            <PopoverMenu.MenuItem
              text="Archive"
              skin="destructive"
              prefixIcon={<Icons.Delete />}
            />
          </PopoverMenu>
        }
      />
  );

  return (
    <Card>
      <Card.Header
        title="Dishes"
        suffix={
          <Button size="small" prefixIcon={<Icons.Add />}>
            New Dish
          </Button>
        }
      />
      <Card.Divider />
      <Card.Content>
        <Layout>
          <Cell span={4}>
            {renderCardGalleryItem({
              imageSrc: 'FoodExample1.jpg',
              title: 'Breakfast Toast',
              subtitle: '$7.89',
              badge: (
                <Badge skin="standard" skin="success">
                  New
                </Badge>
              ),
            })}
          </Cell>
          <Cell span={4}>
            {renderCardGalleryItem({
              imageSrc: 'FoodExample2.jpg',
              title: 'Lemon Ricotta Pasta',
              subtitle: '$15.99',
              badge: (
                <Badge skin="standard" skin="neutralStandard">
                  Popular
                </Badge>
              ),
            })}
          </Cell>
          <Cell span={4}>
            <AddItem size="medium" tooltipContent="Add new dish" />
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};

```


