
## Feature Examples


### Suffix
- description: <p>Add a counter badge or other indication after the item's label using <code>suffix</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SidebarItemNext suffix={<CounterBadge>1</CounterBadge>}>
    Label
  </SidebarItemNext>
  <SidebarItemNext suffix={<Badge skin="warning">New</Badge>}>
    Label
  </SidebarItemNext>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Control item's interaction with <code>disabled</code> prop. Disable item when it's unavailable, but has to remain visible.</p>
- example: 
```jsx 
<SidebarItemNext disabled>Disabled</SidebarItemNext>;
```




## Developer Examples


### Custom HTML tag
- description: <p>Render action as any given HTML tag with <code>as</code> prop. For example it can be rendered as:</p><p></p><p><code><a></code> - use when attributes like href, target, etc., are needed.</p><p></p><p><code><Link></code> - use this react router item to have props like to, replace, etc.</p><p></p><p>All attributes will be passed to the rendered element.</p>
- example: 
```jsx 
<SidebarItemNext as="a" href="https://www.wix.com">
  Wix.com homepage
</SidebarItemNext>;
```

### Setup selection with sidebar
- description: <p>Control item selection from Sidebar component referring to <code>itemKey</code> set value.</p><p></p><p>Truncate children item's text with <code>isInQuickNavigation</code> prop.</p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('1-1');

  return (
    <Box height="200px">
      <SidebarNext isLoading={false} selectedKey={selectedKey}>
        <SidebarSubMenuNext
          title="Parent item"
          itemKey="1"
          onClick={() => setSelectedKey('1-1')}
        >
          <SidebarItemNext
            itemKey="1-1"
            onClick={() => {
              setSelectedKey('1-1');
            }}
          >
            Child item that's setup incorrectly, it allows text wrapping{' '}
          </SidebarItemNext>
          <SidebarItemNext
            itemKey="1-2"
            onClick={() => setSelectedKey('1-2')}
            isInQuickNavigation
          >
            Child item using isInQuickNavigation property preveting from text
            being wrapped
          </SidebarItemNext>
        </SidebarSubMenuNext>
      </SidebarNext>
    </Box>
  );
};
```


    


