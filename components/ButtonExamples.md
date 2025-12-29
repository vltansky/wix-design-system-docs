
## Feature Examples


### Size
- description: <p>Control button size with <code>size</code> prop:</p><li><code>large</code> is best for calls to action that require more emphasis. </li><li><code>medium</code> is for main page actions and common use cases.</li><li><code>small</code> fits into smaller UI elements like cards and widgets.</li><li><code>tiny</code> is used for dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Button size="large">Large</Button>
  <Button size="medium">Medium</Button>
  <Button size="small">Small</Button>
  <Button size="tiny">Tiny</Button>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Change the appearance of a button with a <code>skin</code> prop.  </p><li><code>standard</code> is for general primary actions.</li><li><code>light</code> is for primary actions that are on dark backgrounds. </li><li><code>destructive</code> is only for actions that have a destructive effect on user data, like delete.</li><li><code>premium</code> is for actions that prompt users to upgrade their plans to premium subscription.</li><li><code>premium-light</code> is best for upgrade actions that appear on dark backgrounds.</li><li><code>dark</code> should be used with buttons on backgrounds with colors.  </li><li><code>transparent</code> is for general actions on backgrounds with vivid colors or images.</li><li><code>ai</code> should be used with AI based features.</li><p></p><p>Each action can be <code>primary</code> or <code>secondary</code>. There should only be one primary action per page.</p><p></p><p><em>Note</em>: Secondary buttons should be used alongside primary buttons for less utilized actions, such as cancel or back. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="40px">
  <Box gap="20px">
    <Button>Standard Primary</Button>
    <Button priority="secondary">Standard Secondary</Button>
  </Box>
  <Box gap="20px" backgroundColor="#000" padding="6px">
    <Button skin="light">Light Primary</Button>
    <Button skin="light" priority="secondary">
      Light Secondary
    </Button>
  </Box>
  <Box gap="20px">
    <Button skin="destructive">Destructive Primary</Button>
    <Button skin="destructive" priority="secondary">
      Destructive Secondary
    </Button>
  </Box>
  <Box gap="20px">
    <Button skin="premium">Premium Primary</Button>
    <Button skin="premium" priority="secondary">
      Premium Secondary
    </Button>
  </Box>
  <Box gap="20px" backgroundColor="#000" padding="6px">
    <Button skin="premium-light">Premium Light Primary</Button>
    <Button skin="premium-light" priority="secondary">
      Premium Light Secondary
    </Button>
  </Box>
  <Box gap="20px">
    <Button skin="dark">Dark Primary</Button>
    <Button skin="dark" priority="secondary">
      Dark Secondary
    </Button>
  </Box>
  <Box gap="20px" backgroundColor="#3899EB" padding="6px">
    <Button skin="transparent">Transparent Primary</Button>
    <Button skin="transparent" priority="secondary">
      Transparent Secondary
    </Button>
  </Box>
  <Box gap="20px">
    <Button skin="ai">Ai Primary</Button>
    <Button skin="ai" priority="secondary">
      Ai Secondary
    </Button>
  </Box>
</StorybookComponents.Stack>;
```

### Affix
- description: <p>Add more context to actions with affix icons:</p><li>Emphasize the button action with a <code>prefixIcon</code>.</li><li>Indicate that an action will open a popover or navigate users to another page with a <code>suffixIcon</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="line">
  <StorybookComponents.Stack flexDirection="column">
    <StorybookComponents.Stack>
      <Button size="large" prefixIcon={<Icons.Add />}>
        Prefix
      </Button>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack>
      <Button size="medium" prefixIcon={<Icons.Add />}>
        Prefix
      </Button>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack>
      <Button size="small" prefixIcon={<Icons.AddSmall />}>
        Prefix
      </Button>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack>
      <Button size="tiny" prefixIcon={<Icons.AddSmall />}>
        Prefix
      </Button>
    </StorybookComponents.Stack>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <StorybookComponents.Stack>
      <Button size="large" suffixIcon={<Icons.ChevronDown />}>
        Suffix
      </Button>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack>
      <Button size="medium" suffixIcon={<Icons.ChevronDown />}>
        Suffix
      </Button>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack>
      <Button size="small" suffixIcon={<Icons.ChevronDownSmall />}>
        Suffix
      </Button>
    </StorybookComponents.Stack>
    <StorybookComponents.Stack>
      <Button size="tiny" suffixIcon={<Icons.ChevronDownSmall />}>
        Suffix
      </Button>
    </StorybookComponents.Stack>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>To disable a button, use the <code>disabled</code> prop which indicates a button can't be selected.</p>
- example: 
```jsx 
<Button disabled>Disabled</Button>
```

### Text overflow
- description: <p>Use the <code>ellipsis</code> prop for overflow text. The full text will be displayed in a <code><Tooltip/></code> when a user hovers over the button. Control the style of the tooltip using the <code>tooltipProps</code>.</p><p></p><p><em>Note</em>: Try to avoid lengthy action labels. CTA text should be short and clear – one to two words, or max three for specific use cases.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" width="180px">
  <Button ellipsis>
    This label exceeds available space and is shown in a tooltip
  </Button>
</StorybookComponents.Stack>;
```

### Full width
- description: <p>When working on mobile designs, use the <code>fullWidth</code> prop to fill the button to 100% of the parent container.</p>
- example: 
```jsx 
<Button fullWidth>Full width</Button>
```




## Developer Examples


### Custom HTML tag
- description: <p>Render buttons as any given HTML tag with the <code>as</code> prop. For example, they can be rendered as:</p><li> <code><a></code> when attributes like href, target, etc., are needed. </li><li><code><Link></code> when props like to, replace, etc. are needed.</li><p></p><p>All attributes will be passed to the rendered HTML tag.</p>
- example: 
```jsx 
() => {
  const ReactRouterLink = props => <div {...props} />;
  return (
    <StorybookComponents.Stack>
      <Button as="a" href="https://www.wix.com" target="_blank">
        {'Native <a/> tag'}
      </Button>
      <Button as={ReactRouterLink} skin="premium" to="/home">
        {'React Router <Link/> tag'}
      </Button>
      <Button as="button" onClick={() => alert('yay')}>
        {'Native <button/> tag'}
      </Button>
    </StorybookComponents.Stack>
  );
};
```


    


## Common Use Case Examples


### Loading state
- description: <p>When an action is delayed and still loading, use <code><Loader/></code> <a href="https://www.wix-style-react.com/storybook/?path=/story/components-feedback--loader&previewId=22f5352e-1f78-4f97-8edc-1a1d5a42ff77&storyName=Button"></a>instead of a label on the button.</p>
- example: 
```jsx 
<CustomModalLayout
  primaryButtonText={<Loader size="tiny" />}
  secondaryButtonText="Cancel"
  onCloseButtonClick={() => {}}
  title="Add menu"
>
  <Layout>
    <Cell>
      <FormField label="Name">
        <Input value="Brunch Menu" />
      </FormField>
    </Cell>
    <Cell>
      <FormField label="Description">
        <InputArea value="Brunch includes pastries, fruits, omelettes, coffee, and more." />
      </FormField>
    </Cell>
    <Cell>
      <Box>
        <FormField label="Visible to customers" labelPlacement="right" stretchContent={false}>
          <ToggleSwitch checked />
        </FormField>
      </Box>
    </Cell>
  </Layout>
</CustomModalLayout>;
```

### Main action of a panel
- description: <p>Place the primary CTA button in the <code><SidePanel.Footer/></code> to make sure it is always clearly visible to the user. </p>
- example: 
```jsx 
<SidePanel
  onCloseButtonClick={() => {}}
  skin="floating"
  width="288px"
  height="576px"
>
  <SidePanel.Header title="Manage Accordion" />
  <SidePanel.Content noPadding>
    <NestableList
      withBottomBorder
      items={[
        {
          id: 1,
          options: [{ value: <Text size="small">Color</Text> }],
          dragHandleSize: 'small',
        },
        {
          id: 2,
          options: [{ value: <Text size="small">Price</Text> }],
          dragHandleSize: 'small',
        },
        {
          id: 3,
          options: [{ value: <Text size="small">Size</Text> }],
          dragHandleSize: 'small',
        },
        {
          id: 4,
          options: [{ value: <Text size="small">Collections</Text> }],
          dragHandleSize: 'small',
        },
      ]}
      onChange={() => {}}
    />
  </SidePanel.Content>
  <SidePanel.Footer>
    <Box direction="vertical" align="center">
      <Button size="small">Add Item</Button>
    </Box>
  </SidePanel.Footer>
</SidePanel>;
```


