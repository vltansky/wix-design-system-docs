
## Feature Examples


### Structure
- description: <p>A list item section consists of title and suffix areas.</p>
- example: 
```jsx 
<ListItemSection
  title="title"
  suffix={
    <StorybookComponents.Placeholder height="24px">
      suffix
    </StorybookComponents.Placeholder>
  }
/>;

```

### Types
- description: <p>Component divides lists by 4 types:</p><li><code>title</code> - acts as a title for list items.</li><li><code>subheader</code> - acts as separator between list items for differentiation</li><li><code>whitespace</code> - adds some padding between list items.</li><li><code>divider</code>  - same as whitespace, but with a line.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ListItemSection title="Section title" />
  <ListItemSection type="subheader" title="Subheader title" />
  <ListItemSection type="divider" />
  <ListItemSection type="whitespace" />
</StorybookComponents.Stack>
```

### Suffix
- description: <p>Add text, icons or a button at the  end using suffix.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ListItemSection suffix="Suffix Action" />
  <ListItemSection suffix={<InfoIcon content="Tooltip content!" />} />
</StorybookComponents.Stack>

```

### Text overflow
- description: <p>By default, text wraps into any number of lines. With <code>ellipsis</code> enabled, it will truncate to fit the width of the parent container. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ListItemSection
    ellipsis
    title="This is a very very very very long text that will be cropped by ellipsis at some point. This is a very very very very long text that will be cropped by ellipsis at some point."
  />
  <ListItemSection title="This is a very very very very long text that will *not* be cropped by ellipsis at some point" />
</StorybookComponents.Stack>

```




    


## Common Use Case Examples


### Grouping
- description: <p>Use it to group options into categories.</p>
- example: 
```jsx 
<Box direction="vertical">
  <ListItemSection type="subheader" title="Most popular" />
  <ListItemSelect title="Wix Stores" />
  <ListItemSelect title="Wix Bookings" />
  <ListItemSelect title="Wix Blog" />
  <ListItemSection type="subheader" title="Other" />
  <ListItemSection title="Wix Events" />
  <ListItemSelect title="Wix Forum" />
  <ListItemSelect title="Wix Restaurants" />
</Box>

```


