
## Feature Examples


### Vertical padding
- description: <p>Control vertical padding of accordion items with <code>size</code> prop:</p><li><code>large</code> is a larger size that emphasizes a few items.</li><li><code>medium</code> (default) is a standard size for common cases.</li><li><code>small</code> and <code>tiny</code> are compact sizes that display more items in a smaller space.</li><p></p><p>Note that <code>size</code> prop only controls the padding of accordion items (and not their inner content).</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    size="large"
    items={[
      accordionItemBuilder({
        title: 'Large',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Large',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    size="medium"
    items={[
      accordionItemBuilder({
        title: 'Medium',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Medium',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    size="small"
    items={[
      accordionItemBuilder({
        title: 'Small',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Small',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    size="tiny"
    items={[
      accordionItemBuilder({
        title: 'Tiny',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Tiny',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Horizontal padding
- description: <p>Control horizontal padding of accordion items and their inner content with <code>horizontalPadding</code> prop:</p><li><code>large</code> (default) is a standard size for common cases.</li><li><code>medium</code> is a more compact size.</li><li><code>small</code> and <code>tiny</code> are the most compact sizes used to display more content in narrow spaces.</li><li><code>none</code> has no horizontal padding.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    horizontalPadding="large"
    items={[
      accordionItemBuilder({
        title: 'Large',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Large',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    horizontalPadding="medium"
    items={[
      accordionItemBuilder({
        title: 'Medium',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Medium',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    horizontalPadding="small"
    items={[
      accordionItemBuilder({
        title: 'Small',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Small',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    horizontalPadding="tiny"
    items={[
      accordionItemBuilder({
        title: 'Tiny',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Tiny',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    horizontalPadding="none"
    items={[
      accordionItemBuilder({
        title: 'None',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'None',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the appearance of the accordion with <code>skin</code> prop:</p><li><code>standard</code> (default) is used to visually separate accordion items from their inner content.</li><li><code>light</code> is used when both items and their inner content need to be white.</li><li><code>neutral</code> is used to emphasize accordion items over their inner content.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    skin="standard"
    items={[
      accordionItemBuilder({
        title: 'Standard',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Standard',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    skin="light"
    items={[
      accordionItemBuilder({
        title: 'Light',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Light',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    skin="neutral"
    items={[
      accordionItemBuilder({
        title: 'Neutral',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Neutral',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Shadow
- description: <p>Hide the inner content shadow with <code>hideShadow</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    hideShadow={false}
    skin="light"
    items={[
      accordionItemBuilder({
        title: 'With shadow',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'With shadow',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    hideShadow={true}
    skin="light"
    items={[
      accordionItemBuilder({
        title: 'No shadow',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'No shadow',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Title and subtitle
- description: <p>Describe accordion items using <code>title</code> and <code>subtitle</code> props.</p><p></p><p>These containers also accept any component or a composition of multiple elements.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Title',
        subtitle: 'Subtitle',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Title',
        subtitle: (
          <Box gap="SP1">
            <Text size="small">Subtitle</Text>
            <TextButton size="small" underline="always">
              Learn More
            </TextButton>
          </Box>
        ),
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: <StorybookComponents.Placeholder height="18px" />,
        subtitle: <StorybookComponents.Placeholder height="18px" />,
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Prefix icon
- description: <p>Add a prefix icon in front of an accordion item with <code>icon</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'With icon',
        icon: <Icons.Location />,
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'With icon',
        icon: <Icons.Location />,
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Sections
- description: <p>Organize accordion items into groups using <code>accordionSectionItemBuilder</code>.</p>
- example: 
```jsx 
<Accordion
  size="small"
  items={[
    accordionSectionItemBuilder({
      title: 'Section A',
    }),
    accordionItemBuilder({
      title: 'First item',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
    accordionItemBuilder({
      title: 'Second item',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
    accordionSectionItemBuilder({
      title: 'Section B',
    }),
    accordionItemBuilder({
      title: 'Third item',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
    accordionItemBuilder({
      title: 'Fourth item',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
  ]}
/>;
```

### Show/hide button
- description: <p>Define the show/hide action at the end of accordion item with <code>buttonType</code> prop. It can be:</p><li>Default chevron icon.</li><li><code>textButton</code>.</li><li><code>button</code>.</li><li>or a custom control (<code>node</code>).</li><p></p><p>Provide the labels for these actions, such as 'Show' and 'Hide' with <code>expandLabel</code> and <code>collapseLabel</code> props.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Default',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Default',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Text button',
        showLabel: 'always',
        buttonType: 'textButton',
        expandLabel: 'Show',
        collapseLabel: 'Hide',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Text button',
        showLabel: 'always',
        buttonType: 'textButton',
        expandLabel: 'Show',
        collapseLabel: 'Hide',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Button',
        buttonType: 'button',
        expandLabel: 'Show',
        collapseLabel: 'Hide',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Button',
        buttonType: 'button',
        expandLabel: 'Show',
        collapseLabel: 'Hide',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Custom control',
        buttonType: 'node',
        showLabel: 'always',
        expandLabel: (
          <IconButton skin="standard" priority="secondary" size="small">
            <Icons.ChevronDown />
          </IconButton>
        ),
        collapseLabel: (
          <IconButton skin="standard" priority="secondary" size="small">
            <Icons.X />
          </IconButton>
        ),
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Custom control',
        buttonType: 'node',
        showLabel: 'always',
        expandLabel: (
          <IconButton skin="standard" priority="secondary" size="small">
            <Icons.ChevronDown />
          </IconButton>
        ),
        collapseLabel: (
          <IconButton skin="standard" priority="secondary" size="small">
            <Icons.X />
          </IconButton>
        ),
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Initially open
- description: <p>By default, all accordion items are closed until expanded by the user.</p><p></p><p>Open one or multiple accordion items from the start with <code>initiallyOpen</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Default',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Initially open',
        initiallyOpen: 'true',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Open multiple items
- description: <p>By default, only one accordion item can be open at a time.</p><p></p><p>Allow opening multiple items at once with <code>multiple</code> prop. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Accordion
    items={[
      accordionItemBuilder({
        title: 'Default',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Default',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
  <Accordion
    multiple="true"
    items={[
      accordionItemBuilder({
        title: 'Multiple items open',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
      accordionItemBuilder({
        title: 'Multiple items open',
        children: (
          <StorybookComponents.Placeholder>
            <Box verticalAlign="middle" align="center">
              <Text size="small">Item content</Text>
            </Box>
          </StorybookComponents.Placeholder>
        ),
      }),
    ]}
  />
</StorybookComponents.Stack>;
```

### Disabled item
- description: <p>Disable an accordion item with <code>disabled</code> prop.</p><p></p><p>Users will not be able to expand or collapse it.</p>
- example: 
```jsx 
<Accordion
  items={[
    accordionItemBuilder({
      title: 'Default',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
    accordionItemBuilder({
      title: 'Disabled',
      disabled: true,
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
    accordionItemBuilder({
      title: 'Disabled open',
      disabled: true,
      initiallyOpen: true,
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
  ]}
/>;
```




## Developer Examples


### Using item builders
- description: <p>Accordion is composed from a list of items that share expand/collapse feature. To create them in the most efficient way, use <code>accordionItemBuilder</code>.</p><p></p><p>Note: presenting accordion items as plain objects is still available as a legacy pattern, but it shouldn't be used in any new projects.</p>
- example: 
```jsx 
<Accordion
  items={[
    accordionItemBuilder({
      title: 'First item',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
    accordionItemBuilder({
      title: 'Second item',
      children: (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Item content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      ),
    }),
  ]}
/>;
```

### Controlled
- description: <p>Component can be used in controlled mode by passing <code>open</code> and <code>onToggle</code> props to accordionItemBuilder.</p>
- example: 
```jsx 
() => {
  const [isOpen, setIsOpen] = React.useState(false);
  return (
    <Accordion
      items={[
        accordionItemBuilder({
          title: 'First item',
          onToggle: () => setIsOpen(!isOpen),
          open: isOpen,
          children: (
            <StorybookComponents.Placeholder>
              <Box verticalAlign="middle" align="center">
                <Text size="small">Item content</Text>
              </Box>
            </StorybookComponents.Placeholder>
          ),
        }),
      ]}
    />
  );
};

```


    


## Common Use Case Examples


### In a side panel
- description: <p>Accordion in a side panel allows for efficient use of space.</p><p></p><p>Allow to open only one accordion item at a time. This will minimise the cognitive load and scrolling required by the user.</p>
- example: 
```jsx 
() => {
  const checkboxes = [
    {
      id: '1',
      label: '2023 Winter',
      initialState: true,
    },
    {
      id: '2',
      label: '2023 Spring',
      initialState: true,
    },
    {
      id: '3',
      label: '2022 Winter',
      initialState: false,
    },
    {
      id: '4',
      label: '2022 Spring',
      initialState: false,
    },
  ];

  const [checkboxesList, setCheckboxesList] = React.useState(checkboxes);

  const isAllSelected = checkboxesList.every((item) => item.isChecked);
  const isAllDeselected = checkboxesList.every((item) => !item.isChecked);

  const toggleCheckedAll = (checked) => {
    const updatedCheckboxes = checkboxesList.map((item) => ({
      ...item,
      isChecked: checked,
    }));
    setCheckboxesList(updatedCheckboxes);
  };

  const toggleCheckbox = (id) => {
    const updatedCheckboxes = checkboxesList.map((item) =>
      item.id === id ? { ...item, isChecked: !item.isChecked } : item,
    );
    setCheckboxesList(updatedCheckboxes);
  };

  const renderCheckboxes = () =>
    checkboxesList.map((item) => (
      <Checkbox
        key={item.id}
        id={item.id}
        checked={item.isChecked}
        onChange={() => toggleCheckbox(item.id)}
      >
        {item.label}
      </Checkbox>
    ));

  const [selected, setSelected] = React.useState(1);

  const [value, setValue] = React.useState({ min: 1, max: 3 });
  const marks = {
    0: '$0',
    1: '$50',
    2: '$100',
    3: '$150',
    4: '$200',
  };

  return (
    <Box height="720px">
      <SidePanel title="Filter" onCloseButtonClick={() => {}}>
        <SidePanel.Header title="Filter" />
        <Accordion
          skin="light"
          hideShadow
          size="small"
          items={[
            accordionItemBuilder({
              title: 'Collection',
              children: (
                <Box direction="vertical" gap="12px">
                  <Checkbox
                    checked={isAllSelected}
                    indeterminate={!isAllSelected && !isAllDeselected}
                    onChange={() => toggleCheckedAll(!isAllSelected)}
                  >
                    All collections
                  </Checkbox>
                  {renderCheckboxes()}
                </Box>
              ),
            }),
            accordionItemBuilder({
              title: 'Inventory',
              children: (
                <RadioGroup value={selected} onChange={setSelected}>
                  <RadioGroup.Radio value={1}>All products</RadioGroup.Radio>
                  <RadioGroup.Radio value={2}>In stock</RadioGroup.Radio>
                  <RadioGroup.Radio value={3}>Out of stock</RadioGroup.Radio>
                </RadioGroup>
              ),
            }),
            accordionItemBuilder({
              title: 'Price',
              children: (
                <Slider
                  onChange={(val) => setValue({ min: val[0], max: val[1] })}
                  marks={marks}
                  min={0}
                  max={4}
                  step={1}
                  value={[value.min, value.max]}
                />
              ),
            }),
          ]}
        />
        <SidePanel.Footer>
          <Button priority="secondary" fullWidth>
            Apply
          </Button>
        </SidePanel.Footer>
      </SidePanel>
    </Box>
  );
};
```

### In FAQs
- description: <p>Use accordion in FAQs or similar content-heavy sections. It improves scanning and navigation across related content sections.</p>
- example: 
```jsx 
<Layout>
  <Cell span={12}>
    <Card hideOverflow>
      <Card.Header title="FAQ"></Card.Header>
      <Card.Divider />
      <Accordion
        size="tiny"
        skin="light"
        hideShadow
        items={[
          accordionItemBuilder({
            title: (
              <Text size="small" weight="normal">
                What are Core Web Vitals?
              </Text>
            ),
            children: (
              <Box direction="vertical" width="100%" gap="SP1">
                <Text size="small" secondary>
                  Core Web Vitals are three performance factors Google takes
                  into account for SEO ranking: Largest Contentful Paint,
                  Cumulative Layout Shift, and First Input Delay. When measured
                  in a lab, they don’t affect your SEO directly.
                </Text>
                <TextButton
                  size="small"
                  suffixIcon={<Icons.ExternalLinkSmall />}
                  underline="onHover"
                >
                  Learn more about Core Web Vitals
                </TextButton>
              </Box>
            ),
          }),
          accordionItemBuilder({
            title: (
              <Text size="small" weight="normal">
                Why are my scores different for desktop and mobile?
              </Text>
            ),
            children: (
              <Box direction="vertical" width="100%" gap="SP1">
                <Text size="small" secondary>
                  PageSpeed scores for mobile are often lower than for desktop.
                  That’s because mobile devices have slower processors and take
                  more time to resize texts and images. Lab settings are another
                  reason: Google’s mobile test is on a simulated 3G connection,
                  which is different from the 4G and Wifi connections most
                  visitors use to access your site.
                </Text>
                <TextButton
                  size="small"
                  suffixIcon={<Icons.ExternalLinkSmall />}
                  underline="onHover"
                >
                  Learn more about scores
                </TextButton>
              </Box>
            ),
          }),
          accordionItemBuilder({
            title: (
              <Text size="small" weight="normal">
                Why is Google’s simulation different from real visitor
                experience?
              </Text>
            ),
            children: (
              <Text size="small" secondary>
                The measurements above are based on the experience of people who
                have actually visited your site over the last 30 day period.
                What Google does is check your site’s average metrics in lab
                conditions, using a very basic network and device. This means
                Google’s estimate is probably different from what your actual
                site visitors experience.
              </Text>
            ),
          }),
          accordionItemBuilder({
            title: (
              <Text size="small" weight="normal">
                Why does my score change from one test to another?
              </Text>
            ),
            children: (
              <Box direction="vertical" width="100%" gap="SP1">
                <Text size="small" secondary>
                  This can be due to a number of factors, including local
                  networks and CPU load at the time of the test, as well as
                  changes to your site's home page. In most cases, changes to
                  the score are minimal.
                </Text>
                <TextButton
                  size="small"
                  suffixIcon={<Icons.ExternalLinkSmall />}
                  underline="onHover"
                >
                  Learn more about scores
                </TextButton>
              </Box>
            ),
          }),
          accordionItemBuilder({
            title: (
              <Text size="small" weight="normal">
                Does my PageSpeed score affect my SEO ranking?
              </Text>
            ),
            children: (
              <Box direction="vertical" width="100%" gap="SP1">
                <Text size="small" secondary>
                  Not exactly. Even though site speed is one of the many factors
                  affecting your SEO ranking, only data collected from real user
                  sessions counts. The PageSpeed score you see here is based on
                  a lab test and doesn’t affect your site’s SEO directly.
                </Text>
                <TextButton
                  size="small"
                  suffixIcon={<Icons.ExternalLinkSmall />}
                  underline="onHover"
                >
                  Learn more about SEO ranking
                </TextButton>
              </Box>
            ),
          }),
        ]}
      />
    </Card>
  </Cell>
</Layout>;
```


