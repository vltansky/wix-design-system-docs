
## Feature Examples


### Size
- description: <p>Control the tab size with the <code>size</code> prop:</p><p></p><li><code>medium</code> (default) is the standard used in common cases. </li><li><code>small</code> fits into smaller elements and compact designs.</li><li><code>tiny</code> is used for dense layouts. </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" width="200px">
  <VerticalTabs onChange={(/*id*/) => {}}>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Medium tab 1
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Medium tab 2
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Medium tab 3
      </VerticalTabs.TabItem>
  </VerticalTabs>
  <VerticalTabs size="small" onChange={(/*id*/) => {}}>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Small tab 1
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Small tab 2
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Small tab 3
      </VerticalTabs.TabItem>
  </VerticalTabs>
    <VerticalTabs size="tiny" onChange={(/*id*/) => {}}>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Tiny tab 1
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Tiny tab 2
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
        Tiny tab 3
      </VerticalTabs.TabItem>
  </VerticalTabs>
</StorybookComponents.Stack>;
```

### Group title
- description: <p>Group related tabs together  under a title by using a  <code><VerticalTabs.TabsGroup/></code> wrapper.</p>
- example: 
```jsx 
<div style={{ width: 200 }}>
  <VerticalTabs onChange={(/*id*/) => {}}>
    <VerticalTabs.TabsGroup title="Group Title">
      <VerticalTabs.TabItem>
        Tab 1
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem>
        Tab 2
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem>
        Tab 3
      </VerticalTabs.TabItem>
    </VerticalTabs.TabsGroup>
  </VerticalTabs>
</div>;
```

### Selected tab
- description: <p>Specify which tab is currently selected with the <code>activeTabId</code> prop.</p>
- example: 
```jsx 
<div style={{ width: 200 }}>
  <VerticalTabs activeTabId={0} onChange={(/*id*/) => {}}>
    <VerticalTabs.TabsGroup title="Group Title">
      <VerticalTabs.TabItem id={0}>
       Tab 1
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={1}>
        Tab 2
      </VerticalTabs.TabItem>
      <VerticalTabs.TabItem id={2}>
        Tab 3
      </VerticalTabs.TabItem>
    </VerticalTabs.TabsGroup>
  </VerticalTabs>
</div>;
```




    


## Common Use Case Examples


### Sidebar in a custom modal
- description: <p>Place tabs inside a <code></CustomModalLayout></code> to create a sidebar with structured content.</p>
- example: 
```jsx 
<CustomModalLayout
  showFooterDivider
  showHeaderDivider
  primaryButtonText="Save"
  secondaryButtonText="Cancel"
  onCloseButtonClick={() => {}}
  title="Account settings"
  removeContentPadding
  content={
    <Box>
      <Box width="200px" direction="vertical" paddingBottom="16px">
        <VerticalTabs size="small" onChange={(/*id*/) => {}}>
          <VerticalTabs.TabsGroup title="Settings">
            <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
              Account info
            </VerticalTabs.TabItem>
            <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
              Login info
            </VerticalTabs.TabItem>
            <VerticalTabs.TabItem suffixIcon={<Icons.ChevronRight />}>
              Email preferences
            </VerticalTabs.TabItem>
          </VerticalTabs.TabsGroup>
        </VerticalTabs>
      </Box>
      <Divider direction="vertical"></Divider>
    </Box>
  }
/>;
```


