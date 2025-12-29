
## Feature Examples


### Size
- description: <p>Use <code>size</code> prop to choose the size of the close button: </p><p></p><li>Use <code>large</code>  in larger size layouts, such as <SidePanel/> or modals.</li><li>Use <code>medium</code> in medium size layouts, such as <FloatingNotification/>.</li><li>Use <code>small</code> (default) for common use cases.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <CloseButton size="large" />
  <CloseButton size="medium" />
  <CloseButton />
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Use  <code>skin</code> prop to control the appearance of the close button.</p><p></p><li>Use <code>standard</code> on white backgrounds.</li><li>Use <code>standardFilled</code> on white backgrounds when action needs to be emphasised.</li><li>Use <code>transparent</code> on colour or image backgrounds.</li><li>Use <code>light</code> on dark backgrounds.</li><li>Use <code>dark</code> on white or light color backgrounds.</li><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Box align="center"  padding="8px" backgroundColor="D80">
    <CloseButton skin="standard" />
  </Box>
  <Box align="center"  padding="8px" backgroundColor="D80">
    <CloseButton skin="standardFilled" />
  </Box>
  <Box align="center"  padding="8px" backgroundColor="B20">
    <CloseButton skin="transparent" />
  </Box>
  <Box align="center"  padding="8px" backgroundColor="D10">
    <CloseButton skin="light" />
  </Box>
  <Box align="center"  padding="8px" backgroundColor="D80">
    <CloseButton skin="dark" />
  </Box>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Use <code>disabled</code> prop to disable all close button interactions and to highlight unavailable functions.</p>
- example: 
```jsx 
<CloseButton disabled />;
```




## Developer Examples


### Custom HTML tag
- description: <p>Use <code>as</code> prop to render close button as any given HTML tag.</p><p></p><p>For example, they can be rendered as:</p><li><code><a></code> when attributes like href, target, etc., are needed.</li><li><code><Link> </code>when props like to, replace, etc. are needed.</li><p>All attributes will be passed to the rendered HTML tag.</p>
- example: 
```jsx 
() => {
  const ReactRouterLink = (props) => <div {...props} />;
  return (
    <StorybookComponents.Stack gap="60px">
      <Box direction="vertical">
        <CloseButton
          as="a"
          href="https://www.wix.com"
          target="_blank"
          size="large"
        />
        <Text size="small">An <a/> tag</Text>
      </Box>
      <Box direction="vertical">
        <CloseButton
          as={ReactRouterLink}
          href="https://www.wix.com"
          target="_blank"
          size="large"
        />
        <Text size="small">A react router <Link/> tag</Text>
      </Box>
      <Box direction="vertical">
        <CloseButton
          as="button"
          href="https://www.wix.com"
          target="_blank"
          size="large"
        />
        <Text size="small">A native <button/> tag</Text>
      </Box>
    </StorybookComponents.Stack>
  );
};
```


    


## Common Use Case Examples


### Marketing card
- description: <p>Allow users to dismiss a promotional marketing card by passing a close button as <code><Card/></code> controls. </p>
- example: 
```jsx 
<Card controls={<CloseButton skin="dark" />}>
  <MarketingLayout
    title="Add sessions to get booked"
    description="Set when this service is offered and which staff member will provide it."
    actions={
      <Box gap="6px">
        <Button size="small">Add Sessions</Button>
        <Button size="small" skin="inverted">
          Learn More
        </Button>
      </Box>
    }
    size="small"
    image={
      <Box width="100%" align="right">
        <Image width="120px" src="PromotionalBookingsUpgrade.svg" transparent />
      </Box>
    }
  />
</Card>;
```

### Custom icon
- description: <p>To add a help icon next to the close button, pass the help icon as a child element to <code><CloseButton/></code>. </p><p></p><p>This is valid only when the help icon is next to the close button. For all other cases use <code><IconButton/></code> instead.</p><p></p><p>While it is possible to override the <code>x</code> icon with any other icon, it is not recommended to ensure the component's consistency.</p>
- example: 
```jsx 
<Card
  controls={
    <Box>
      <CloseButton skin="dark" size="medium">
        <Icons.HelpSmall />
      </CloseButton>
      <CloseButton skin="dark" size="medium" />
    </Box>
  }
>
  <Card.Content>
    <Box height="90px" />
  </Card.Content>
</Card>;
```


