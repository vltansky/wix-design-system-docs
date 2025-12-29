
## Feature Examples


### Types 
- description: <p>Use the <code>type</code> prop to change the behavior of the tab item:</p><p></p><li><code>tab</code> can be used to organize settings into logical categories. </li><li><code>action</code> can be used as a button. </li><li><code>title</code> can be used to maintain structure between tab elements.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <VerticalTabsItem type="tab">Vertical Tab</VerticalTabsItem>
  <VerticalTabsItem type="action"> Vertical Tab Action </VerticalTabsItem>
  <VerticalTabsItem type="title">Vertical Tab Title</VerticalTabsItem>
</StorybookComponents.Stack>;
```

### Affix
- description: <p>Add more context to actions with affix icons:</p><p></p><li>Emphasize the tab action with a <code>prefixIcon</code>.</li><li>Indicate that the tab will open a popover or navigate users to another page with a <code>suffixIcon</code>.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <VerticalTabsItem prefixIcon={<Icons.Add />}>Prefix icon</VerticalTabsItem>
  <VerticalTabsItem suffixIcon={<Icons.ChevronRight />}>
    Suffix icon
  </VerticalTabsItem>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Use the <code>disabled</code> prop to indicate that a tab can't be selected.</p>
- example: 
```jsx 
<VerticalTabsItem disabled>Disabled tab</VerticalTabsItem>
```




    


