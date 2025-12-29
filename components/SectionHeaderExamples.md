
## Feature Examples


### Size
- description: <p>Control the size of a section header with the <code>size</code> prop:</p><li><code>medium</code> (default)  is the standard used in common cases.</li><li><code>small</code> is used in dense layouts and panels.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader title="Medium" size="medium" />
  <SectionHeader title="Small" size="small" />
</StorybookComponents.Stack>;
```

### Horizontal padding
- description: <p>Adjust the <code>horizontalPadding</code> of a section header according to the content padding inside the following section:</p><li><code>large</code> (default)</li><li><code>medium</code></li><li><code>small</code></li><li><code>tiny</code></li><li><code>xTiny</code></li><li><code>xxTiny</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader title="Large" horizontalPadding="large" />
  <SectionHeader title="Medium" horizontalPadding="medium" />
  <SectionHeader title="Small" horizontalPadding="small" />
  <SectionHeader title="Tiny" horizontalPadding="tiny" />
  <SectionHeader title="Extra tiny" horizontalPadding="xTiny" />
  <SectionHeader title="Extra-extra tiny" horizontalPadding="xxTiny" />
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the style of a section header using the <code>skin</code> prop:</p><li><code>standard</code> is the default and is used in most cases.</li><li><code>neutral</code> is used to minimize the component’s visual weight.</li><li><code>light</code> is used as a completely minimal header that blends in with rest of the content.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader title="Standard" skin="standard" />
  <SectionHeader title="Neutral" skin="neutral" />
 <SectionHeader title="Light" skin="light" />
</StorybookComponents.Stack>;
```

### Dividers
- description: <p>Control which dividers are visible with the <code>divider</code> prop:</p><li>By default, a section header has both top and bottom dividers.</li><li>Use <code>top</code> when there is already a divider at the bottom of a component.</li><li>Use <code>bottom</code> when there is already a divider at the top of a component.</li><li>Use <code>none</code> when there are already dividers at the top and bottom of a component.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader title="Default" />
  <SectionHeader title="Top" divider="top" />
  <SectionHeader title="Bottom" divider="bottom" />
  <SectionHeader title="No dividers" divider="none" />
</StorybookComponents.Stack>;
```

### Suffix
- description: <p>Use a <code>suffix</code> container to add info or actions that relate to the content below a section header.</p><p></p><p>A variety of components can be used in the suffix:</p><li><code><InfoIcon/></code></li><li><code><TextButton/></code></li><li><code><Button/></code></li><li><code><IconButton/></code></li><li><code><Text/></code> or others</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader
    suffix={
      <InfoIcon
        size="small"
        content="Info icon gives more information about a section."
      />
    }
  />
  <SectionHeader
    suffix={
      <TextButton
        size="tiny"
        priority="secondary"
        prefixIcon=<Icons.AddSmall />
      >
        Suffix
      </TextButton>
    }
  />
  <SectionHeader
    suffix={
      <Button size="tiny" priority="secondary">
        Suffix
      </Button>
    }
  />
  <SectionHeader
    suffix={
      <IconButton size="tiny" priority="secondary">
        <Icons.MoreSmall />
      </IconButton>
    }
  />
  <SectionHeader suffix={<Text size="tiny">Suffix</Text>} />
</StorybookComponents.Stack>;
```

### Title
- description: <p>Use the <code>title</code> prop to describe the content that appears below the section header.</p><p></p><p>The default is a text value, but the container can accept any component.</p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader title="Default" />
  <SectionHeader
    title={
      <Text weight="bold" size="small">
        Custom title
      </Text>
    }
  />
  <SectionHeader title=<StorybookComponents.Placeholder height="24px" /> />
</StorybookComponents.Stack>;
```

### Title alignment
- description: <p>Control the title's position with the <code>align</code> prop:</p><li>Use <code>start</code> (default) for left-aligned lists.</li><li>Use <code>center</code> in settings panels.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHeader title="Start" align="start" />
  <SectionHeader title="Center" align="center" />
</StorybookComponents.Stack>;
```

### Title overflow
- description: <p>Title text that does not fit in one line gets truncated with an ellipsis.</p><p></p><p>The full text appears in a tooltip when hovering over the truncated text. </p><p></p>
- example: 
```jsx 
<SectionHeader title="A very long section title goes into a title container in this case. It even has multiple sentences inside. It will be truncated by ellipses once it reaches the second line" />;
```




    


## Common Use Case Examples


### Group content in cards
- description: <p>Use section headers to organize card info into separate categories.</p><p></p><p>This makes the whole card easier to scan.</p>
- example: 
```jsx 
() => {
  const items = [
    {
      sectionTitle: 'Monday, Feb 7',
    },
    {
      time: '7:00 PM - 9:00 PM',
      event: 'Registration & reception',
    },
    {
      sectionTitle: 'Tuesday, Feb 8',
    },
    {
      time: '8:00 AM - 10:00 AM',
      event: 'Keynote address by Steven H. Kastner',
      divider: true,
    },
    {
      time: '10:00 AM - 1:00 PM',
      event: 'Break & networking',
      divider: true,
    },
    {
      time: '1:00 PM - 3:00 PM',
      event: 'Keynote address by Linda Contreras',
      divider: true,
    },
    {
      time: '7:00 PM - 9:00 PM',
      event: 'Evening reception',
    },
    {
      sectionTitle: 'Wednesday, Feb 9',
    },
    {
      time: '8:00 AM - 10:00 AM',
      event: 'Keynote address by Susan W. Eaton',
      divider: true,
    },
    {
      time: '10:00 AM - 1:00 PM',
      event: 'Keynote address by Bjorn Rettig',
    },
  ];

  const pirmaryAction = {
    text: 'Edit',
  };

  const secondaryActions = [
    {
      text: 'Hide',
      icon: <Icons.HiddenSmall />,
      onClick: () => ({}),
    },
    {
      text: 'Cancel',
      icon: <Icons.BlockSmall />,
      onClick: () => ({}),
    },
    {
      text: 'Delete',
      icon: <Icons.DeleteSmall />,
      onClick: () => ({}),
    },
  ];

  const actionsList = (
    <TableActionCell
      primaryAction={pirmaryAction}
      secondaryActions={secondaryActions}
      numOfVisibleSecondaryActions={0}
      size="small"
    />
  );

  const primaryAction = (
    <Button size="small" priority="secondary" prefixIcon={<Icons.AddSmall />}>
      Add Item
    </Button>
  );

  return (
    <Card hideOverflow>
      <Card.Header
        title="Event schedule"
        subtitle="Build a schedule to keep guests informed throughout your event."
        suffix={primaryAction}
      />
      {items.map((params) => {
        if (params.sectionTitle) {
          return <SectionHeader title={params.sectionTitle} size="small" />;
        }
        return (
          <TableListItem
            showDivider={params.divider}
            onClick={() => {}}
            options={[
              { value: <Text size="small">{params.time}</Text>, width: '25%' },
              { value: <Text size="small">{params.event}</Text>, width: '50%' },
              { value: actionsList },
            ]}
          />
        );
      })}
    </Card>
  );
};
```


