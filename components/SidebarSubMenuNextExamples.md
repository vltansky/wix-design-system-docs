
## Feature Examples


### Structure
- description: <p>Component consists of 2 containers:</p><p>- <code>title</code> - use it do display sub item's label.</p><p>- <code>children</code> - use it do display item's child actions.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidebarSubMenuNext
    title="Label"
    >
    <SidebarItemNext>Child label</SidebarItemNext>
    <SidebarItemNext>Child label</SidebarItemNext>
  </SidebarSubMenuNext>
</StorybookComponents.Stack>;
```

### Suffix
- description: <p>Add a counter badge or other indication after the item's label using <code>suffix</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidebarSubMenuNext
    title="Parent label"
    suffix={<CounterBadge>1</CounterBadge>}
  >
    <SidebarItemNext>Child label</SidebarItemNext>
    <SidebarItemNext>Child label</SidebarItemNext>
  </SidebarSubMenuNext>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Control item's interaction with <code>disabled</code> prop. Disable item when it's unavailable, but has to remain visible.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SidebarSubMenuNext
    title="Disabled"
    disabled
    >
    <SidebarItemNext>Child label</SidebarItemNext>
    <SidebarItemNext>Child label</SidebarItemNext>
  </SidebarSubMenuNext>
</StorybookComponents.Stack>;
```




## Developer Examples


### Custom HTML tag
- description: <p>Render action as any given HTML tag with <code>as</code> prop. For example it can be rendered as:</p><p></p><p><code><a></code> - use when attributes like href, target, etc., are needed.</p><p></p><p><code><Link></code> - use this react router item to have props like to, replace, etc.</p><p></p><p>All attributes will be passed to the rendered element.</p><p></p><p><strong>Link works only if any of inner elements are NOT selected.</strong></p>
- example: 
```jsx 
<StorybookComponents.Stack height="55px">
  <SidebarNext isLoading={false} selectedKey={0}>
    <SidebarSubMenuNext
      title="Go to Wix.com"
      as="a"
      target="_blank"
      href="https://www.wix.com"
    >
      <SidebarItemNext>Child item</SidebarItemNext>
      <SidebarItemNext>Child item</SidebarItemNext>
    </SidebarSubMenuNext>
  </SidebarNext>
</StorybookComponents.Stack>;
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
            isInQuickNavigation
          >
            Child item with a long label to show its ellipsis
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


    


## Common Use Case Examples


### Navigating between items
- description: <p>Redirect <code><SidebarSubMenuNext/></code> selection to its first child when clicked. It helps a user to understand sidebar's hierarchy and navigate between the items easily.</p>
- example: 
```jsx 
() => {
  const [selectedKey, setSelectedKey] = React.useState('3-1');

  return (
    <StorybookComponents.Stack height="384px">
      <SidebarNext selectedKey={selectedKey} isLoading={false}>
        <SidebarSubMenuNext
          title="Contacts"
          itemKey="3"
          onClick={() => setSelectedKey('3-1')}
        >
          <SidebarItemNext itemKey="3-1" onClick={() => setSelectedKey('3-1')}>
            Contacts
          </SidebarItemNext>
          <SidebarItemNext itemKey="3-2" onClick={() => setSelectedKey('3-2')}>
            Segments
          </SidebarItemNext>
          <SidebarItemNext itemKey="3-3" onClick={() => setSelectedKey('3-3')}>
            Site Members
          </SidebarItemNext>
          <SidebarItemNext itemKey="3-4" onClick={() => setSelectedKey('3-4')}>
            Workflows
          </SidebarItemNext>
        </SidebarSubMenuNext>
        <SidebarSubMenuNext
          title="Communications"
          itemKey="3"
          onClick={() => setSelectedKey('4-1')}
        >
          <SidebarItemNext itemKey="4-1" onClick={() => setSelectedKey('4-1')}>
            Inbox
          </SidebarItemNext>
          <SidebarItemNext itemKey="4-2" onClick={() => setSelectedKey('4-2')}>
            Chat
          </SidebarItemNext>
          <SidebarItemNext itemKey="4-3" onClick={() => setSelectedKey('4-3')}>
            Forms & Submissions
          </SidebarItemNext>
          <SidebarItemNext itemKey="4-4" onClick={() => setSelectedKey('4-4')}>
            Business Email
          </SidebarItemNext>
        </SidebarSubMenuNext>
      </SidebarNext>
    </StorybookComponents.Stack>
  );
};
```


