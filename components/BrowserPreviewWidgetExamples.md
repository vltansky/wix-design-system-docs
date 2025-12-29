
## Feature Examples


### Structure
- description: <p>Component consists of preview content area and a browser bar:</p><li>Preview content area displays any type of content, like an image, text, or video. Add it inside the component as its <code>children</code>.</li><li>A styled browser bar is added at the top by default.</li>
- example: 
```jsx 
<BrowserPreviewWidget>
  <StorybookComponents.Placeholder width="320px" height="120px">
    <Box verticalAlign="middle" align="center" height="100%">
      <Text>Preview content area</Text>
    </Box>
  </StorybookComponents.Placeholder>
</BrowserPreviewWidget>;
```

### Skin
- description: <p>Change the background style with <code>skin</code> prop:</p><li>Use <code>neutral</code> (default) in all common cases.</li><li>Use <code>gradient</code> for larger preview areas.</li><li>Use <code>custom</code> to set the <code>backgroundColor</code> to any color using design system color tokens, RGB or HEX formats.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <BrowserPreviewWidget skin="neutral">
    <StorybookComponents.Placeholder width="320px" height="120px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Neutral</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
  <BrowserPreviewWidget skin="gradient">
    <StorybookComponents.Placeholder width="320px" height="120px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Gradient</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
  <BrowserPreviewWidget skin="custom" backgroundColor="B40">
    <StorybookComponents.Placeholder width="320px" height="120px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Custom background</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
</StorybookComponents.Stack>;
```

### Browser bar size
- description: <p>Control the height of the browser bar with <code>browserBarSize</code> prop, depending on the preview area width:</p><li>Use <code>size9</code>  when preview's width is <312 px.</li><li>Use <code>size12</code>  (default) when width is 312–443 px.</li><li>Use <code>size18</code>  when width is 444–660 px.</li><li>Use <code>size24</code>  when width is >660 px.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <BrowserPreviewWidget browserBarSize="size9">
    <StorybookComponents.Placeholder width="240px" height="60px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Shorter than 312 px</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
  <BrowserPreviewWidget browserBarSize="size12">
    <StorybookComponents.Placeholder width="320px" height="60px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>312–443 px wide</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
  <BrowserPreviewWidget browserBarSize="size18">
    <StorybookComponents.Placeholder width="520px" height="60px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>444–660 px wide</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
  <BrowserPreviewWidget browserBarSize="size24">
    <StorybookComponents.Placeholder width="720px" height="60px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Wider than 660 px</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
</StorybookComponents.Stack>;
```

### Width and height
- description: <p>Control dimensions of the component by setting <code>width</code> and <code>height</code> props to custom % or px.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <BrowserPreviewWidget width="50%">
    <StorybookComponents.Placeholder width="240px" height="60px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Custom width</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
  <BrowserPreviewWidget height="240px">
    <StorybookComponents.Placeholder width="240px" height="60px">
      <Box verticalAlign="middle" align="center" height="100%">
        <Text>Custom height</Text>
      </Box>
    </StorybookComponents.Placeholder>
  </BrowserPreviewWidget>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Site previews
- description: <p>Use browser preview widget to showcase a design prepared by or suggested for the user.</p><p></p><p>It is often used together with <code><MobilePreviewWidget/></code> preview.</p>
- example: 
```jsx 
() => {
  const VIEW_TYPE = {
    desktopView: 'desktopView',
    mobileView: 'mobileView',
  };
  const [viewType, setViewType] = React.useState(VIEW_TYPE.desktopView);

  const changeViewType = (_, value) => setViewType(value);

  const desktopView = () => (
    <BrowserPreviewWidget skin="gradient" height="718px">
      <Image
        width="360px"
        height="180px"
        borderRadius="0"
        src="browserPreview.png"
      />
    </BrowserPreviewWidget>
  );

  const mobileView = () => (
    <MobilePreviewWidget skin="gradient" height="718px">
      <Image height="476px" borderRadius="0" src="browserPreviewMobile.png" />
    </MobilePreviewWidget>
  );

  return (
    <CustomModalLayout
      height="720px"
      onCloseButtonClick={() => {}}
      removeContentPadding
      content={
        <Layout gap="0px">
          <Cell span={6}>
            {viewType === VIEW_TYPE.desktopView ? desktopView() : mobileView()}
          </Cell>
          <Cell span={6}>
            <Box
              direction="vertical"
              paddingLeft="24px"
              paddingRight="24px"
              gap="24px"
              verticalAlign="middle"
              height="100%"
            >
              <Box>
                <SegmentedToggle selected={viewType} onClick={changeViewType}>
                  <SegmentedToggle.Icon
                    value={VIEW_TYPE.desktopView}
                    tooltipText="Desktop"
                  >
                    <Icons.Desktop />
                  </SegmentedToggle.Icon>
                  <SegmentedToggle.Icon
                    value={VIEW_TYPE.mobileView}
                    tooltipText="Mobile"
                  >
                    <Icons.Mobile />
                  </SegmentedToggle.Icon>
                </SegmentedToggle>
              </Box>
              <Heading size="large">Your campaign is live!</Heading>
              <Box direction="vertical" gap="12px">
                <Text>
                  Be proud. Get the word out about the amazing things you're
                  doing.
                </Text>
                <TextButton prefixIcon={<Icons.Link />}>
                  Share your Campaign
                </TextButton>
              </Box>
              <Box width="100%" align="right">
                <Button priority="secondary">Done</Button>
              </Box>
            </Box>
          </Cell>
        </Layout>
      }
    />
  );
};
```

### Selected page validation
- description: <p>Use browser preview widget to validate if the selected site is the one the user wants to proceed with.</p>
- example: 
```jsx 
() => {
  const [checked, setChecked] = React.useState(false);

  return (
    <CustomModalLayout
      primaryButtonText="Import Posts"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => {}}
      title="Import posts to your blog"
      content={
        <Box direction="vertical" gap="12px">
          <Text>Is this your blog?</Text>
          <Layout gap="0px">
            <Cell span={6}>
              <BrowserPreviewWidget
                skin="custom"
                backgroundColor="D80"
                browserBarSize="size9"
              >
                <Image
                  width="240px"
                  height="140px"
                  borderRadius="0"
                  src="browserPreview.png"
                />
              </BrowserPreviewWidget>
            </Cell>
            <Cell span={6}>
              <Box
                direction="vertical"
                gap="3x"
                height="100%"
                verticalAlign="middle"
              >
                <Text>Home | Wix Design System</Text>
                <TextButton>wixdesignsystem.com</TextButton>
              </Box>
            </Cell>
          </Layout>
          <Checkbox
            checked={checked}
            onChange={() => setChecked(!checked)}
            vAlign="top"
          >
            By checking the box you allow Wix to import this content, confirm
            you own or are licenced to use it and assume liability for this use
          </Checkbox>
        </Box>
      }
    />
  );
};
```


