
## Feature Examples


### Size
- description: <p>Control the size of a button with the <code>size</code> prop:</p><li><code>Medium</code> is the default size for general actions.</li><li><code>Small</code> should be used for cards and widgets.</li><li><code>Tiny</code> is for dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection='column' gap='60px'>
  <TextButton size="medium">Medium</TextButton>
  <TextButton size="small">Small</TextButton>
  <TextButton size="tiny">Tiny</TextButton>
</StorybookComponents.Stack>
```

### Skin
- description: <p>Control the appearance of a button with <code>skin</code> prop:</p><li><code>Standard</code> is the default for general actions.</li><li><code>Destructive</code> is for actions that have a destructive effect on user data, such as delete.</li><li><code>Standard-light</code> is for main actions placed on dark backgrounds.</li><li><code>Light</code> is for general actions placed on dark backgrounds.</li><li><code>Premium</code> is used for actions that prompt users to upgrade their plans.</li><li><code>Dark</code> is for a list of actions stacked in a single place, like quick links in the sidebar.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="60px">
  <TextButton skin="standard">Standard</TextButton>
  <TextButton skin="destructive">Destructive</TextButton>
    <StorybookComponents.Background skin="dark">
    <TextButton skin="standard-light">Standard Light</TextButton>
  </StorybookComponents.Background>
    <StorybookComponents.Background skin="dark">
    <TextButton skin="light">Light</TextButton>
  </StorybookComponents.Background>
  <TextButton skin="premium">Premium</TextButton>
  <TextButton skin="dark">Dark</TextButton>
</StorybookComponents.Stack>;
```

### Affix
- description: <p>Add more context to actions with affix icons:</p><li>Emphasize the button action with a <code>prefixIcon</code>.</li><li>Indicate that an action will open a popover or navigate users to another page with a <code>suffixIcon</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap='60px'>
  <StorybookComponents.Stack>
    <TextButton size="medium" prefixIcon={<Icons.Add />}>
      Prefix
    </TextButton>
    <TextButton size="medium" suffixIcon={<Icons.ChevronDown />}>
      Suffix
    </TextButton>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <TextButton size="small" prefixIcon={<Icons.AddSmall />}>
      Prefix
    </TextButton>
    <TextButton size="small" suffixIcon={<Icons.ChevronDownSmall />}>
      Suffix
    </TextButton>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack>
    <TextButton size="tiny" prefixIcon={<Icons.AddSmall />}>
      Prefix
    </TextButton>
    <TextButton size="tiny" suffixIcon={<Icons.ChevronDownSmall />}>
      Suffix
    </TextButton>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Underline
- description: <p>Control underline visibility with <code>underline</code> prop:</p><li><code>none</code> is the default.</li><li><code>onHover</code> shows an underline on mouse hover.</li><li><code>always</code> shows an underline at all times. It is most suitable for text links.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap='60px'>
  <TextButton>None</TextButton>
  <TextButton underline="onHover">On Hover</TextButton>
  <TextButton underline="always">Always</TextButton>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>To disable a button, use the <code>disabled</code> prop which indicates a button can't be selected.</p>
- example: 
```jsx 
<TextButton disabled>Disabled</TextButton>
```

### Text overflow
- description: <p>Use an <code>ellipsis</code> prop for overflow text. The full text will be displayed when a user hovers over the button.</p><p></p><p><em>Note</em>: Try to avoid lengthy action labels. CTA text should be short and clear – one to two words, or three max for specific use cases.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" width="360px">
  <TextButton ellipsis>
    This label exceeds available space and is shown in a tooltip
  </TextButton>
</StorybookComponents.Stack>;
```

### Full width
- description: <p>Set the button to fill 100% of its parent container width with the <code>fluid</code> prop. Use this setting for mobile designs only.</p>
- example: 
```jsx 
<TextButton fluid>Full Width</TextButton>;
```




## Developer Examples


### Custom HTML tag
- description: <p>Render buttons as any given HTML tag with the <code>as</code> prop.</p><p></p><p>Render text buttons that are links as:</p><li> <code><a></code> when attributes like href, target, etc., are needed. </li><li><code><Link></code> when props like <code>to</code>, <code>replace</code>, etc. are needed.</li><p></p><p>All attributes will be passed to the rendered HTML tag.</p>
- example: 
```jsx 
() => {
  const ReactRouterLink = props => <div {...props} />;
  return (
    <StorybookComponents.Stack flexDirection="column">
      <TextButton as="a" href="https://www.wix.com" target="_blank">
        {'Native <a/> tag'}
      </TextButton>
      <TextButton as={ReactRouterLink} skin="premium" to="/home">
        {'React Router <Link/> tag'}
      </TextButton>
      <TextButton as="button">{'Native <button/> tag'}</TextButton>
    </StorybookComponents.Stack>
  );
};
```


    


## Common Use Case Examples


### Settings panel
- description: <p>Use text buttons for optional actions, such as links to help center articles.  </p>
- example: 
```jsx 
<SidePanel skin="floating" width="420px" onCloseButtonClick onHelpButtonClick>
  <SidePanel.Header title="Booking Calendar" />
  <Box height="480px">
    <VerticalTabs size="small" activeTabId={5} onChange={() => {}}>
      <VerticalTabs.TabItem id={0}>Manage</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={1}>Layout</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={2}>Display</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={3}>Design</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={4}>Text</VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={5}>Support</VerticalTabs.TabItem>
    </VerticalTabs>
    <Divider direction="vertical" />
    <SidePanel.Content noPadding>
      <SidePanel.Field>
        <section>
          <Text size="small" secondary>
            Frequently asked questions
          </Text>
          <Box gap={2} direction="vertical" paddingTop={2}>
            <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />} ellipsis>
              Customize calendar page
            </TextButton>
            <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />} ellipsis>
              Time zone display
            </TextButton>
            <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />} ellipsis>
              Appointment time slots
            </TextButton>
            <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />} ellipsis>
              Date and time formatting
            </TextButton>
            <TextButton size="small" suffixIcon={<Icons.ExternalLinkSmall />} ellipsis>
              How-to articles
            </TextButton>
          </Box>
        </section>
      </SidePanel.Field>
      <SidePanel.Field>
        <section>
          <Text size="small" secondary>
            Still having issues?
          </Text>
          <Box gap={2} direction="vertical" paddingTop={2}>
            <TextButton size="small" prefixIcon={<Icons.ChatSmall />} suffixIcon={<Icons.ExternalLinkSmall />} ellipsis>
              Contact customer care
            </TextButton>
          </Box>
        </section>
      </SidePanel.Field>
    </SidePanel.Content>
  </Box>
</SidePanel>
```

### List of actions
- description: <p>Use a <code>dark</code> skin for a list of actions to avoid distracting or overwhelming the user.</p>
- example: 
```jsx 
<Layout>
  <Cell span={6}>
    <Card>
      <Card.Header title="Promote" />
      <Card.Divider />
      <Card.Content>
        <Box direction="vertical" gap="18px">
          <TextButton skin="dark" prefixIcon={<Icons.Coupon />}>
            Create Coupon
          </TextButton>
          <TextButton skin="dark" prefixIcon={<Icons.VideoCamera />}>
            Create Promo Video
          </TextButton>
          <TextButton skin="dark" prefixIcon={<Icons.EmailSend />}>
            Send Email Campaign
          </TextButton>
          <TextButton skin="dark" prefixIcon={<Icons.Share />}>
            Share Product
          </TextButton>
          <TextButton skin="dark" prefixIcon={<Icons.Settings />}>
            Edit SEO Settings
          </TextButton>
        </Box>
      </Card.Content>
    </Card>
  </Cell>
</Layout>;
```


