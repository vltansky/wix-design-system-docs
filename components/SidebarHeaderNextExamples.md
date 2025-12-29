
## Feature Examples


### Structure
- description: <p>Provides three containers <code>title</code>, <code>subtitle</code> and <code>children</code></p><p></p><p>Title and subtitle allow only single line text, if overflows shows ellipsis.</p>
- example: 
```jsx 
<SidebarHeaderNext title="Title" subtitle="Subtitle">
  <StorybookComponents.Placeholder skin="light">
    Children
  </StorybookComponents.Placeholder>
</SidebarHeaderNext>;
```




    


## Common Use Case Examples


### Overriding header content
- description: <p>Sidebar header allows to display other components within if it's the most valuable information for the user navigating the sidebar. </p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('2');

  return (
    <Box height="400px">
      <SidebarNext
        skin="light"
        isLoading={false}
        selectedKey={selectedKey}
        header={
          <SidebarHeaderNext>
            <TextButton
              prefixIcon={<Icons.ArrowLeft />}
              size="tiny"
              skin="dark"
              weight="normal"
            >
              Back to Site Dashboard
            </TextButton>
            <Box direction="vertical" align="center" marginTop={3}>
              <Avatar size="size60" />
              <Box direction="vertical" align="center" marginTop={2}>
                <Text size="small" weight="bold" secondary>
                  Jon Doe
                </Text>
                <Text size="tiny" secondary light>
                  jond@mail.com
                </Text>
              </Box>
            </Box>
          </SidebarHeaderNext>
        }
      >
        <SidebarItemNext itemKey="1" onClick={() => setSelectedKey('1')}>
          Account settings
        </SidebarItemNext>
        <SidebarDividerNext />
        <SidebarItemNext itemKey="2" onClick={() => setSelectedKey('2')}>
          Domains
        </SidebarItemNext>
        <SidebarItemNext itemKey="3" onClick={() => setSelectedKey('3')}>
          Business email
        </SidebarItemNext>
        <SidebarItemNext itemKey="4" onClick={() => setSelectedKey('4')}>
          Vouchers
        </SidebarItemNext>
        <SidebarItemNext itemKey="5" onClick={() => setSelectedKey('5')}>
          Billing history
        </SidebarItemNext>
      </SidebarNext>
    </Box>
  );
};
```


