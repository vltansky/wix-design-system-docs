
## Feature Examples


### Size
- description: <p>Update the dimensions of a button with the <code>size</code> prop.  </p><li><code>large</code> is for onboarding flows and marketing pages where the action needs more emphasis.</li><li><code>medium</code> is the default for all common cases.</li><li><code>small</code>  is for icon buttons used in cards and widgets.</li><li><code>tiny</code>  is for small and dense layouts.</li><p></p><p><em>Note</em>:  small and tiny size buttons should use the small icon size (18x18).</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <IconButton size="large">
    <Icons.Add />
  </IconButton>
  <IconButton size="medium">
    <Icons.Add />
  </IconButton>
  <IconButton size="small">
    <Icons.AddSmall />
  </IconButton>
  <IconButton size="tiny">
    <Icons.AddSmall />
  </IconButton>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Change the button's appearance with the <code>skin</code> prop.  </p><li><code>standard</code> is the default for all general actions.</li><li><code>light</code>  is for dark backgrounds.</li><li><code>transparent</code> is for backgrounds with colors or images.  </li><li><code>premium</code> is for actions that prompt users to upgrade their plans.</li><li><code>dark</code> should be used with buttons on backgrounds with colors. </li><li><code>ai</code> should be used with AI based features.</li><p></p><p>Each action can be <code>primary</code>, <code>secondary</code> or <code>tertiary</code>, depending on priority. There should only be one primary action per page.</p><p></p><p><em>Note</em>: Secondary buttons should be used alongside primary buttons for less utilized actions, such as cancel or back. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack padding="12px" gap="6px">
    <IconButton skin="standard" priority="primary">
      <Icons.Check />
    </IconButton>
    <IconButton skin="standard" priority="secondary">
      <Icons.X />
    </IconButton>
    <IconButton skin="standard" priority="tertiary">
      <Icons.More />
    </IconButton>
  </StorybookComponents.Stack>
  <StorybookComponents.Background skin="dark">
    <StorybookComponents.Stack padding="12px" gap="6px">
      <IconButton skin="light" priority="primary">
        <Icons.Check />
      </IconButton>
      <IconButton skin="light" priority="secondary">
        <Icons.X />
      </IconButton>
      <IconButton skin="light" priority="tertiary">
        <Icons.More />
      </IconButton>
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="blue">
    <StorybookComponents.Stack padding="12px" gap="6px">
      <IconButton skin="transparent" priority="primary">
        <Icons.Check />
      </IconButton>
      <IconButton skin="transparent" priority="secondary">
        <Icons.X />
      </IconButton>
      <IconButton skin="transparent" priority="tertiary">
        <Icons.More />
      </IconButton>
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Background skin="light">
    <StorybookComponents.Stack padding="12px" gap="6px">
      <IconButton skin="premium" priority="primary">
        <Icons.Check />
      </IconButton>
      <IconButton skin="premium" priority="secondary">
        <Icons.X />
      </IconButton>
      <IconButton skin="premium" priority="tertiary">
        <Icons.More />
      </IconButton>
    </StorybookComponents.Stack>
  </StorybookComponents.Background>
  <StorybookComponents.Stack padding="12px" gap="6px">
    <IconButton skin="dark" priority="primary">
      <Icons.Check />
    </IconButton>
    <IconButton skin="dark" priority="secondary">
      <Icons.X />
    </IconButton>
    <IconButton skin="dark" priority="tertiary">
      <Icons.More />
    </IconButton>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack padding="12px" gap="6px">
    <IconButton skin="ai" priority="primary">
      <Icons.Check />
    </IconButton>
    <IconButton skin="ai" priority="secondary">
      <Icons.X />
    </IconButton>
    <IconButton skin="ai" priority="tertiary">
      <Icons.More />
    </IconButton>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>To disable a button, use the <code>disabled</code> prop which indicates a button can't be selected.</p>
- example: 
```jsx 
<IconButton disabled>
  <Icons.Add />
</IconButton>;
```




## Developer Examples


### Custom HTML tag
- description: <p>Render buttons as any given HTML tag with the <code>as</code> prop. For example, they can be rendered as:</p><li><code><a></code> when attributes like <code>href</code>, <code>target</code> are needed.</li><li><code><Link></code> when props like <code>to</code>, <code>replace</code>, etc. are needed.</li><p></p><p>All attributes will be passed to the rendered element.</p>
- example: 
```jsx 
() => {
  const ReactRouterLink = props => <div {...props} />;

  return (
    <StorybookComponents.Stack justifyContent="space-between">
      <StorybookComponents.Stack
        flexDirection="column"
        gap="12px"
        alignItems="center"
      >
        <Text secondary size="small">
          {'<a/> tag'}
        </Text>
        <IconButton as="a" href="https://www.wix.com" target="_blank">
          <Icons.Add />
        </IconButton>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack
        flexDirection="column"
        gap="12px"
        alignItems="center"
      >
        <Text secondary size="small">
          {'React router <Link/> tag'}
        </Text>
        <IconButton as={ReactRouterLink} to="/home">
          <Icons.Add />
        </IconButton>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack
        flexDirection="column"
        gap="12px"
        alignItems="center"
      >
        <Text secondary size="small">
          {'Native <button/> tag'}
        </Text>
        <IconButton as="button">
          <Icons.Add />
        </IconButton>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```


    


## Common Use Case Examples


### Button labels
- description: <p>Use <code><Tooltip/></code> <a href="https://www.wix-style-react.com/storybook/?path=/story/components-overlays--tooltip"></a> to add a label to icon buttons.</p>
- example: 
```jsx 
<Box align="center">
  <Tooltip content="Edit program">
    <IconButton priority="secondary">
      <Icons.Edit />
    </IconButton>
  </Tooltip>
</Box>;
```

### Small layouts
- description: <p>Use icon buttons in small and crowded layouts.</p>
- example: 
```jsx 
<Layout>
  <Cell span={4}>
    <Proportion aspectRatio={1}>
      <MediaOverlay skin="gradient" media="FoodExample2.jpg">
        <MediaOverlay.Content placement="top-end" visible="always">
          <Tooltip content="Edit image">
            <IconButton priority="secondary" skin="inverted" size="small">
              <Icons.CropSmall />
            </IconButton>
          </Tooltip>
          <Tooltip content="Mark as favorite">
            <IconButton priority="secondary" skin="inverted" size="small">
              <Icons.FavoriteSmall />
            </IconButton>
          </Tooltip>
          <PopoverMenu
            textSize="small"
            triggerElement={
              <Tooltip content="More actions">
                <IconButton priority="secondary" skin="inverted" size="small">
                  <Icons.MoreSmall />
                </IconButton>
              </Tooltip>
            }
          >
            <PopoverMenu.MenuItem text="Edit" />
            <PopoverMenu.MenuItem text="Remove" skin="destructive" />
          </PopoverMenu>
        </MediaOverlay.Content>
        <MediaOverlay.Content placement="bottom-start" visible="always">
        <Text light size="small">Pasta with Ricotta Cheese</Text>
        </MediaOverlay.Content>
      </MediaOverlay>
    </Proportion>
  </Cell>
</Layout>;
```

### Popover menu
- description: <p>Use icon buttons to open a <code><PopoverMenu/></code>.</p>
- example: 
```jsx 
() => {
  const renderImage = () => <Image width={230} borderRadius={0}></Image>;

  const renderContent = () => (
    <Box
      direction="vertical"
      verticalAlign="space-between"
      padding="24px 29px 27px"
      backgroundColor="D80"
      flexGrow={1}
    >
      <Box direction="vertical" gap={1}>
        <Text weight="bold">JAVA meetup</Text>
        <Text size="small" weight="thin" secondary light>
          Jan 20, 2021, 10:00 AM, Location will be announced later
        </Text>
      </Box>
      <Box align="space-between">
        <Box />
        <Box align="space-between" verticalAlign="middle" gap={1}>
          <PopoverMenu
            textSize="small"
            triggerElement={
              <Tooltip content="More actions">
                <IconButton priority="secondary" size="small">
                  <Icons.MoreSmall />
                </IconButton>
              </Tooltip>
            }
          >
            <PopoverMenu.MenuItem
              text="Edit SEO settings"
              prefixIcon={<Icons.SettingsSmall />}
            />
            <PopoverMenu.Divider />
            <PopoverMenu.MenuItem
              text="Duplicate as draft"
              prefixIcon={<Icons.DuplicateSmall />}
            />
            <PopoverMenu.MenuItem
              text="Cancel event"
              skin="destructive"
              prefixIcon={<Icons.BlockSmall />}
            />
          </PopoverMenu>
          <Button
            priority="secondary"
            size="small"
            prefixIcon={<Icons.PromoteSmall />}
          >
            Promote
          </Button>
          <Button priority="secondary" size="small">
            Edit
          </Button>
        </Box>
      </Box>
    </Box>
  );

  return (
    <Card hideOverflow>
      <Box minHeight={200}>
        {renderImage()}
        {renderContent()}
      </Box>
    </Card>
  );
};
```

### Low priority actions
- description: <p>Use icon buttons for lower-priority actions that have no effect on the main user flow. For example, to change the cover image of an audio.</p>
- example: 
```jsx 
<SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px">
  <SidePanel.Header title="Audio Player Settings" />
  <SidePanel.Content noPadding>
    <SidePanel.Field>
      <FieldSet
        legend="Track cover image"
        alignment="center"
        columns="168px auto auto"
      >
        <Image width="156px" height="102px" src="TravelExample6.jpg" />
        <Tooltip content="Change image">
          <IconButton size="small" skin="standard" priority="secondary">
            <Icons.RefreshSmall />
          </IconButton>
        </Tooltip>
        <Tooltip content="Remove image">
          <IconButton size="small" skin="standard" priority="secondary">
            <Icons.DeleteSmall />
          </IconButton>
        </Tooltip>
      </FieldSet>
    </SidePanel.Field>
    <SidePanel.Field>
      <FormField label="Source (URL)">
        <Input placeholder="Add link to the track" size="small" />
      </FormField>
    </SidePanel.Field>
    <SidePanel.Field>
      <FormField label="Name">
        <Input value="Track Name" size="small" />
      </FormField>
    </SidePanel.Field>
    <SidePanel.Field>
      <FormField label="Description">
        <InputArea
          placeholder="Add a short description to promote your audio track."
          size="small"
          minHeight="120px"
          resizable
        />
      </FormField>
    </SidePanel.Field>
  </SidePanel.Content>
</SidePanel>;
```


