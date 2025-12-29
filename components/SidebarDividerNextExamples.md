
## Feature Examples


### Width
- description: <p>Control divider's width with <code>fullWidth</code> prop. Default value is <code>false</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidebarDividerNext />
  <SidebarDividerNext fullWidth />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Navigation split into groups
- description: <p>Split actions into the groups using <code>SidebarDividerNext</code>.</p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('2');

  return (
    <Box height="170px">
      <SidebarNext isLoading={false} selectedKey={selectedKey}>
        <SidebarItemNext itemKey="1" onClick={() => setSelectedKey('1')}>
          Home
        </SidebarItemNext>
        <SidebarItemNext itemKey="2" onClick={() => setSelectedKey('2')}>
          Stores
        </SidebarItemNext>
        <SidebarItemNext itemKey="3" onClick={() => setSelectedKey('3')}>
          Contacts
        </SidebarItemNext>
        <SidebarDividerNext />{' '}
        <SidebarItemNext itemKey="4" onClick={() => setSelectedKey('4')}>
          Settings
        </SidebarItemNext>
      </SidebarNext>
    </Box>
  );
};
```


