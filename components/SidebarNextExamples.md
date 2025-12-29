
## Feature Examples


### Structure
- description: <p>This component consists of 3 containers:</p><p>- <code>header</code> - use it to display application name or to reflect application setup progress.</p><p>- <code>children</code> - use it to list all navigation elements linking to all major application pages.</p><p>- <code>footer</code> - use it for a special call to action.</p><p></p><p>Header and footer containers are always sticky.</p>
- example: 
```jsx 
() => {
  const placeholder = (children, height) => (
    <StorybookComponents.Placeholder width="100%" height={height} skin="light">
      {children}
    </StorybookComponents.Placeholder>
  );

  return (
    <StorybookComponents.Stack height="204px">
      <SidebarNext
        header={placeholder('Header', '42px')}
        footer={placeholder('Footer', '42px')}
        isLoading={false}
      >
        {placeholder('Children', '120px')}
      </SidebarNext>
    </StorybookComponents.Stack>
  );
};
```

### Skin
- description: <p>Control the sidebar's style with <code>skin</code> prop:</p><p>- <code>dark</code> (default) - used in <em>Business Manager</em> application.</p><p>- <code>light</code> - used in <em>My Account</em> application.</p><p>- <code>neutral</code> - used in <em>Media Manager</em>.</p>
- example: 
```jsx 
<StorybookComponents.Stack height="90px">
  <SidebarNext skin="dark" selectedKey="1-2" isLoading={false}>
    <SidebarItemNext itemKey="1-1">Dark option 1</SidebarItemNext>
    <SidebarItemNext itemKey="1-2">Dark option 2</SidebarItemNext>
  </SidebarNext>
  <SidebarNext skin="light" selectedKey="1-2" isLoading={false}>
    <SidebarItemNext itemKey="1-1">Light option 1</SidebarItemNext>
    <SidebarItemNext itemKey="1-2">Light option 2</SidebarItemNext>
  </SidebarNext>
  <SidebarNext skin="neutral" selectedKey="1-2" isLoading={false}>
    <SidebarItemNext itemKey="1-1">Neutral option 1</SidebarItemNext>
    <SidebarItemNext itemKey="1-2">Neutral option 2</SidebarItemNext>
  </SidebarNext>
</StorybookComponents.Stack>;
```

### Skeleton
- description: <p>Toggle component's loading state with <code>isLoading</code> prop. Prop's default value is <code>true</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack height="270px">
  <SidebarNext
    isLoading={true}
    header={
      <StorybookComponents.Placeholder width="100%" height="42px" skin="light">
        Header
      </StorybookComponents.Placeholder>
    }
    footer={
      <StorybookComponents.Placeholder width="100%" height="42px" skin="light">
        Footer
      </StorybookComponents.Placeholder>
    }
  />
</StorybookComponents.Stack>;
```




## Developer Examples


### Control selected state
- description: <p>Control which sidebar option is selected by passing a key number with <code>selectedKey</code> prop in <code><SidebarNext/></code> component.</p><p></p><p>Specify each sidebar option's key number with <code>itemKey</code> prop in <code><SidebarItemNext/></code> component.</p><p></p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('2');

  return (
    <Box height="120px">
      <SidebarNext isLoading={false} selectedKey={selectedKey}>
        <SidebarItemNext itemKey="1" onClick={() => setSelectedKey('1')}>
          Option 1
        </SidebarItemNext>
        <SidebarItemNext itemKey="2" onClick={() => setSelectedKey('2')}>
          Option 2
        </SidebarItemNext>
        <SidebarItemNext itemKey="3" onClick={() => setSelectedKey('3')}>
          Option 3
        </SidebarItemNext>
      </SidebarNext>
    </Box>
  );
}
```

### Toggle sidebar&#39;s visibility
- description: <p>Set the sidebar as visible or hidden using <code>hidden</code> prop.</p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('1');
  const [hidden, setHidden] = React.useState(false);

  return (
    <Box overflow="hidden">
      <StorybookComponents.Stack height="264px">
        <SidebarNext
          selectedKey={selectedKey}
          isLoading={false}
          hidden={hidden}
        >
          <StorybookComponents.Placeholder skin="light" height="240px">
            Children
          </StorybookComponents.Placeholder>
        </SidebarNext>
        <Button onClick={() => setHidden(!hidden)}>Toggle Sidebar</Button>
      </StorybookComponents.Stack>
    </Box>
  );
};
```


    


## Common Use Case Examples


### Sidebar in composer application
- description: <p>Some applications like many Wix composers require a lot of horizontal space to make the app effective.</p><p></p><p>Therefore it's allowed to add an additional action in the composer header allowing to toggle sidebar's visibility.</p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('5')
  const [hidden, setHidden] = React.useState(false)

  return (
    <Box overflow="hidden" height="500px">
      <Box>
        <SidebarNext
          selectedKey={selectedKey}
          isLoading={false}
          hidden={hidden}
          header={
            <SidebarHeaderNext
              title="Let's setup the site"
              subtitle={
                <TextButton
                  skin="light"
                  size="tiny"
                  suffixIcon={
                    <Box
                      height="15px"
                      width="18px"
                      marginTop="2px"
                      verticalAlign="middle"
                    >
                      <Icons.ChevronRightSmall />
                    </Box>
                  }
                >
                  View all steps
                </TextButton>
              }
            ></SidebarHeaderNext>
          }
          footer={
            <Box width="100%" align="center" padding="18px 0px">
              <TextButton
                size="small"
                skin="light"
                prefixIcon={<Icons.QuickAccessSmall />}
              >
                Quick Access
              </TextButton>
            </Box>
          }
        >
          <SidebarItemNext itemKey="1" onClick={() => setSelectedKey('1')}>
            Home
          </SidebarItemNext>
          <SidebarItemNext itemKey="2" onClick={() => setSelectedKey('2')}>
            Activity
          </SidebarItemNext>
          <SidebarDividerNext />
          <SidebarSubMenuNext
            title="Contacts"
            itemKey="3"
            onClick={() => setSelectedKey('3-1')}
          >
            <SidebarItemNext
              itemKey="3-1"
              onClick={() => setSelectedKey('3-1')}
            >
              Contacts
            </SidebarItemNext>
            <SidebarItemNext
              itemKey="3-2"
              onClick={() => setSelectedKey('3-2')}
            >
              Segments
            </SidebarItemNext>
            <SidebarItemNext
              itemKey="3-3"
              onClick={() => setSelectedKey('3-3')}
            >
              Site Members
            </SidebarItemNext>
            <SidebarItemNext
              itemKey="3-4"
              onClick={() => setSelectedKey('3-4')}
            >
              Workflows
            </SidebarItemNext>
          </SidebarSubMenuNext>
          <SidebarItemNext itemKey="4" onClick={() => setSelectedKey('4')}>
            Communications
          </SidebarItemNext>
          <SidebarItemNext itemKey="5" onClick={() => setSelectedKey('5')}>
            Automations
          </SidebarItemNext>
          <SidebarDividerNext />
          <SidebarItemNext itemKey="6" onClick={() => setSelectedKey('6')}>
            Settings
          </SidebarItemNext>
        </SidebarNext>
      </Box>
      <Box direction="vertical" width="100%">
        <ComposerHeader>
          <ComposerHeader.Actions>
            <TextButton
              skin="dark"
              size="small"
              prefixIcon={
                !hidden ? (
                  <Icons.HideSidebarSmall />
                ) : (
                  <Icons.ShowSidebarSmall />
                )
              }
              onClick={() => setHidden(!hidden)}
            >
              {!hidden ? 'Hide sidebar' : 'Show sidebar'}
            </TextButton>
          </ComposerHeader.Actions>
        </ComposerHeader>
        <Box margin="6px 6px 0px 6px" height="100%">
          <StorybookComponents.Placeholder>
            Page content
          </StorybookComponents.Placeholder>
        </Box>
      </Box>
    </Box>
  )
}

```


