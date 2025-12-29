
## Feature Examples


### Size
- description: <p>Component supports two sizes - <code>small</code> and <code>medium</code></p>
- example: 
```jsx 
<Layout cols={1}>
  <ListItemSelect title="Medium size" />
  <ListItemSelect size="small" title="Small size" />
</Layout>;
```

### Checkbox
- description: <p>Item can be configured for multi select components by enabling <code>checkbox</code>.</p>
- example: 
```jsx 
<Layout cols={1}>
  <ListItemSelect title="For single selection" />
  <ListItemSelect checkbox title="For multi selection" />
</Layout>;
```

### Affix
- description: <p>Component has <code>prefix</code> and <code>suffix</code> areas. If plain text or icon is inserted, component automatically inverts the color when selected.</p>
- example: 
```jsx 
<Layout cols={1}>
  <ListItemSelect
    prefix={
      <Box>
        <Icons.Toolbox />
      </Box>
    }
    title="Title area"
    suffix="Suffix area"
  />
  <ListItemSelect
    prefix={<Avatar size="size24" />}
    title="Title area"
    suffix={
      <Box>
        <Badge size="small" skin="success">
          Badge
        </Badge>
      </Box>
    }
  />
  <ListItemSelect
    selected
    prefix={
      <Box>
        <Icons.Toolbox />
      </Box>
    }
    title="Title area"
    suffix="Suffix area"
  />
  <ListItemSelect
    selected
    prefix={<Avatar size="size24" />}
    title="Title area"
    suffix={
      <Box>
        <Badge size="small" skin="success">
          Badge
        </Badge>
      </Box>
    }
  />
</Layout>;
```

### Subtitle
- description: <p>Additional information, like user email or address can be inserted to subtitle area.</p>
- example: 
```jsx 
<ListItemSelect title="Title area" subtitle="subtitle area" />;
```

### Disabled
- description: <p>Component can be disabled, it automatically changes color of all areas if used as text or icon.</p><p></p><p>Tooltip can be added to explain why the component is disabled with <code>disabledDescription</code></p>
- example: 
```jsx 
() => {
  const listItemSelectOptions = [
    listItemSelectBuilder({
      id: 0,
      title: 'Disabled Action',
      disabled: true,
    }),
  ];

  return (
    <StorybookComponents.Stack spacing="24px" flexDirection="column">
      <ListItemSelect
        disabled
        prefix={<Icons.Toolbox />}
        width="400px"
        title="Disabled without tooltip"
        subtitle="Subtitle area"
        suffix="Suffix area"
        id={0}
      />

      <ListItemSelect
        disabled
        checkbox
        prefix={<Icons.Toolbox />}
        width="400px"
        title="Disabled with tooltip"
        subtitle="Subtitle area"
        suffix="Suffix area"
        id={0}
        disabledDescription="This action is disabled"
      />
    </StorybookComponents.Stack>
  );
};

```

### Text cropping
- description: <p>By default component wraps the text. If needed it can be configured to show ellipsis and display full value on hover.</p><p></p><p>Tooltips on truncated text will be overridden if the component is disabled. In that case, it will show <code>disabledDescription</code> first.</p>
- example: 
```jsx 
<Layout cols={1}>
 <ListItemSelect
    ellipsis
    titleMaxLines={2}
    subtitleMaxLines={2}
    title="This is a very very very very very very very very long text that will wrap to 2 lines"
    suffix="Nice long long long long long Suffix"
  />
  <ListItemSelect
    ellipsis
    title="This is a very very very very long text that will be cropped by ellipsis at some point"
    suffix="Nice long long long long long Suffix"
  />
  <ListItemSelect
        disabled
        ellipsis
        title="This is a very very very very long text that will be cropped by ellipsis at some point"
        suffix="Nice long long long long long Suffix"
        disabledDescription="This is disabled"
      />
  
</Layout>;
```

### Advanced example
- description: <p>All properties work together and can be combined in various ways. It can be rendered as standalone or as part of dropdown.</p>
- example: 
```jsx 
<Box height="230px">
  <DropdownLayout
    visible
    selectedId={2}
    options={[
      listItemSelectBuilder({
        id: 0,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Carmel Lloyd',
        subtitle: 'Kaplan 41',
        suffix: '31 Dec 2017',
      }),
      listItemSelectBuilder({
        id: 1,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Gracie-May Marsden',
        subtitle: 'Sderot Ben Gurion 75',
        suffix: '20 Jan 2000',
      }),
      listItemSelectBuilder({
        id: 2,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Keisha Decker',
        subtitle: 'Aminadav 18',
        suffix: '4 Nov 2010',
      }),
      listItemSelectBuilder({
        id: 3,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Ruairidh Fitzgerald',
        subtitle: 'HaYarkon 228',
        suffix: '7 Apr 2009',
        disabled: true,
        disabledDescription: 'User has unsubscribed and cannot be selected',
      }),
      listItemSelectBuilder({
        id: 4,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Sheldon Chavez',
        subtitle: 'Pinkas 2',
        suffix: '2 Dec 2019',
      }),
      listItemSelectBuilder({
        id: 5,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Brandan Gibbs',
        subtitle: 'Frishman 38',
        suffix: '1 Feb 2003',
      }),
      listItemSelectBuilder({
        id: 6,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Gordon Holmes',
        subtitle: 'HaShalom road 66',
        suffix: '19 Aug 2016',
      }),
      listItemSelectBuilder({
        id: 7,
        checkbox: true,
        prefix: <Avatar size="size30" />,
        title: 'Aaisha Rios',
        subtitle: 'Arlozorov 101',
        suffix: '22 Jul 2018',
      }),
    ]}
  />
</Box>
```




    


