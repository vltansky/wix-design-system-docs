
## Feature Examples


### Structure
- description: <p>Display title for navigation's section with <code>children</code> prop.</p>
- example: 
```jsx 
<SidebarTitleItemNext>Title</SidebarTitleItemNext>;
```




    


## Common Use Case Examples


### Sections with titles
- description: <p>Split actions into the groups using <code>SidebarTitleItemNext</code>.</p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('2');

  return (
    <Box height="275px">
      <SidebarNext isLoading={false} selectedKey={selectedKey}>
        <SidebarTitleItemNext>Contacts</SidebarTitleItemNext>
        <SidebarItemNext itemKey="1" onClick={() => setSelectedKey('1')}>
          Segments
        </SidebarItemNext>
        <SidebarItemNext itemKey="2" onClick={() => setSelectedKey('2')}>
          Site members
        </SidebarItemNext>
        <SidebarItemNext itemKey="3" onClick={() => setSelectedKey('3')}>
          Workflows
        </SidebarItemNext>
        <SidebarTitleItemNext>Settings</SidebarTitleItemNext>
        <SidebarItemNext itemKey="4" onClick={() => setSelectedKey('4')}>
          Business Info
        </SidebarItemNext>
        <SidebarItemNext itemKey="5" onClick={() => setSelectedKey('5')}>
          Language and region
        </SidebarItemNext>
        <SidebarItemNext itemKey="6" onClick={() => setSelectedKey('6')}>
          Roles and permissions
        </SidebarItemNext>
      </SidebarNext>
    </Box>
  );
};
```


