
## Feature Examples


### Add items
- description: <p>Let users add new parent items or child items with the <code>addItemLabel</code> prop.</p>
- example: 
```jsx 
<NestableList
  addItemLabel="Add item to level 1"
  items={[
    {
      id: 1,
      options: [{ value: <Text size="small">Item 1</Text> }],
      addItemLabel: <Text size="small">Add item to level 2</Text>,
      children: [
        { id: 2, options: [{ value: <Text size="small">Item 2</Text> }] },
      ],
    },
  ]}
  onChange={() => {}}
/>;
```

### Maximum depth
- description: <p>Define a maximum number of sub-levels that can be added to the list with the <code>maxDepth</code> prop.</p><p></p><p>By default, the maximum  <code>maxDepth</code> value is set to <code>10</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text size="small">Maximum depth of 3 levels</Text>
  <NestableList
    maxDepth={3}
    items={[
      {
        id: '1',
        options: [
          {
            value: <Text size="small">Item 1</Text>,
          },
        ],
        children: [
          {
            id: '2',
            options: [
              {
                value: <Text size="small">Item 2</Text>,
              },
            ],
            children: [
              {
                id: '3',
                options: [
                  {
                    value: <Text size="small">Item 3</Text>,
                  },
                ],
              },
            ],
          },
        ],
      },
    ]}
    onChange={() => {}}
  />
  <Text size="small">Maximum depth of 2 levels</Text>
  <NestableList
    maxDepth={2}
    items={[
      {
        id: '4',
        options: [
          {
            value: <Text size="small">Item 1</Text>,
          },
        ],
        children: [
          {
            id: '5',
            options: [
              {
                value: <Text size="small">Item 2</Text>,
              },
            ],
          },
          {
            id: '6',
            options: [
              {
                value: <Text size="small">This item can't be moved to level 3</Text>,
              },
            ],
          },
        ],
      },
    ]}
    onChange={() => {}}
  />
</StorybookComponents.Stack>;
```

### Indent size
- description: <p>Control arrow indent size with <code>indentSize</code> prop:</p><p></p><li><code>small</code> is best for very narrow layouts, such as settings panels.</li><li><code>medium</code> is for smaller layouts.</li><li><code>large</code> (default) is used for admin tables.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NestableList
    indentSize="small"
    readOnly={true}
    items={[
      {
        id: 1,
        options: [{ value: <Text size="small">Item 1</Text> }],
        children: [
          { id: 2, options: [{ value: <Text size="small">Item 2</Text> }] },
          { id: 3, options: [{ value: <Text size="small">Item 3</Text> }] },
        ],
      },
    ]}
    onChange={() => {}}
  />
  <NestableList
    indentSize="medium"
    readOnly={true}
    items={[
      {
        id: 1,
        options: [{ value: <Text size="small">Item 1</Text> }],
        children: [
          { id: 2, options: [{ value: <Text size="small">Item 2</Text> }] },
          { id: 3, options: [{ value: <Text size="small">Item 3</Text> }] },
        ],
      },
    ]}
    onChange={() => {}}
  />
  <NestableList
    indentSize="large"
    readOnly={true}
    items={[
      {
        id: 1,
        options: [{ value: <Text size="small">Item 1</Text> }],
        children: [
          { id: 2, options: [{ value: <Text size="small">Item 2</Text> }] },
          { id: 3, options: [{ value: <Text size="small">Item 3</Text> }] },
        ],
      },
    ]}
    onChange={() => {}}
  />
</StorybookComponents.Stack>;
```

### Dividers
- description: <p>Turn off dividers with <code>dividers</code> prop to give the component more minimal look, by setting the property to <code>false</code>. Dividers are on by default.</p>
- example: 
```jsx 
<NestableList
  indentSize="medium"
  dividers={false}
  readOnly={true}
  items={[
    {
      id: 1,
      options: [{ value: <Text size="small">Item 1</Text> }],
      children: [
        { id: 2, options: [{ value: <Text size="small">Item 2</Text> }] },
        { id: 3, options: [{ value: <Text size="small">Item 3</Text> }] },
      ],
    },
  ]}
  onChange={() => {}}
/>;
```

### Prevent changing depth
- description: <p>Lock the existing depth for all items in the list with the <code>preventChangeDepth</code> prop. This property allows users to change the order of items, but only at the same level of hierarchy. </p><p></p><p>By default the value of the <code>preventChangeDepth</code> property is <code>false</code>. This means users can drag and drop any item to any level.  </p>
- example: 
```jsx 
<NestableList
  preventChangeDepth={true}
  items={[
    {
      id: 1,
      options: [
        { value: <Text size="small">This item can only move in level 1</Text> },
      ],
      children: [
        {
          id: 2,
          options: [
            { value: <Text size="small">This item can only move in level 2</Text> },
          ],
        },
        {
          id: 3,
          options: [
            { value: <Text size="small">This item can only move in level 2</Text> },
          ],
        },
      ],
    },
    {
      id: 4,
      options: [
        { value: <Text size="small">This item can only move in level 1</Text> },
      ],
      children: [
        {
          id: 5,
          options: [
            { value: <Text size="small">This item can only move in level 2</Text> },
          ],
        },
      ],
    },
  ]}
  onChange={() => {}}
/>;
```

### Lock dragging
- description: <p>To lock an individual item’s position, use the <code>items</code> prop and set <code>draggable</code> to <code>false</code>.</p><p></p><p>Items that aren't locked can still freely change their position in the list.</p>
- example: 
```jsx 
<NestableList
  items={[
    {
      id: 1,
      options: [{ value: <Text size="small">This item can't be dragged</Text> }],
      draggable: false,
      children: [
        {
          id: 2,
          options: [{ value: <Text size="small">This item can't be dragged</Text> }],
          draggable: false,
        },
        {
          id: 3,
          options: [
            { value: <Text size="small">This item can be moved freely</Text> },
          ],
        },
      ],
    },
    {
      id: 4,
      options: [{ value: <Text size="small">This item can be moved freely</Text> }],
      children: [
        {
          id: 5,
          options: [
            { value: <Text size="small">This item can be moved freely</Text> },
          ],
        },
      ],
    },
  ]}
  onChange={() => {}}
/>;
```

### Read only mode
- description: <p>Prevent any reordering in the list with the <code>readOnly</code> prop. The list won't display any interactive icons.</p>
- example: 
```jsx 
<NestableList
  readOnly={true}
  items={[
    {
      id: 1,
      options: [{ value: <Text size="small">Item 1</Text> }],
      children: [
        { id: 2, options: [{ value: <Text size="small">Item 2</Text> }] },
        { id: 3, options: [{ value: <Text size="small">Item 3</Text> }] },
      ],
    },
  ]}
  onChange={() => {}}
/>;
```

### Collapse items
- description: <p>To hide children and only show the parent item, use the <code>items</code> prop and set <code>isCollapsed</code> to <code>true</code>.</p><p></p><p>By default, parent items hide their children when they're being selected and dragged.</p>
- example: 
```jsx 
() => {
  const CollapseIcon = ({ id, allItems }) => {
    const onCollapse = () => {
      setItems(
        allItems.map(item =>
          item.id === id ? { ...item, isCollapsed: !item.isCollapsed } : item,
        ),
      );
    };
    const { isCollapsed } = allItems.filter(item => item.id === id)[0];

    return (
      <Box align="right">
        <IconButton skin="light" onClick={onCollapse}>
          {isCollapsed ? <Icons.ChevronDown /> : <Icons.ChevronUp />}
        </IconButton>
      </Box>
    );
  };

  const [items, setItems] = React.useState([
    {
      id: 'item-1',
      options: [{ value: <Text size="small">Item 1</Text> }],
    },
    {
      id: 'item-2',
      isCollapsed: true,
      options: [{ value: <Text size="small">Show and hide children</Text> }],
      children: [
        {
          id: 'item-2-child-1',
          options: [{ value: <Text size="small">Child 1</Text> }],
        },
        {
          id: 'item-2-child-2',
          options: [{ value: <Text size="small">Child 2</Text> }],
        },
        {
          id: 'item-2-child-3',
          options: [{ value: <Text size="small">Child 3</Text> }],
        },
      ],
    },
    {
      id: 'item-3',
      options: [{ value: <Text size="small">Item 3</Text> }],
    },
  ]);

  const itemsWithUpdatedControls = items.map(item => {
    return {
      ...item,
      options: item.children
        ? [
            item.options[0],
            {
              value: <CollapseIcon id={item.id} allItems={items} />,
            },
          ]
        : [item.options[0]],
    };
  });

  return (
    <NestableList
      items={itemsWithUpdatedControls}
      onChange={onChangeData => setItems(onChangeData.items)}
    />
  );
};
```

### Bottom border
- description: <p>Add a bottom border to the last item in the list with the <code>withBottomBorder</code> prop. The default value is set to <code>false</code>.</p><p></p><p>Use the border when the list is outside the card or modal, for example, in the sidebar and on white backgrounds.  </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NestableList
    items={[
      {
        id: 1,
        options: [{ value: <Text size="small">Item 1</Text> }],
      },
      {
        id: 2,
        options: [{ value: <Text size="small">Item 2</Text> }],
      },
      {
        id: 3,
        options: [
          { value: <Text size="small">No bottom border (default)</Text> },
        ],
      },
    ]}
    onChange={() => {}}
  />

  <NestableList
    withBottomBorder
    items={[
      {
        id: 4,
        options: [{ value: <Text size="small">Item 1</Text> }],
      },
      {
        id: 5,
        options: [{ value: <Text size="small">Item 2</Text> }],
      },
      {
        id: 6,
        options: [{ value: <Text size="small">With bottom border</Text> }],
      },
    ]}
    onChange={() => {}}
  />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Sort items into sub-categories
- description: <p>Use nestable lists to let the users organize their items (posts, articles, products, etc.) into categories and subcategories.</p><p></p><p>Use any necessary <code><TableListItem/></code> props to format the style and content inside the list of items.</p>
- example: 
```jsx 
() => {
  const CollapseIcon = ({ id, allItems }) => {
    const onCollapse = () => {
      setItems(
        allItems.map(item =>
          item.id === id ? { ...item, isCollapsed: !item.isCollapsed } : item,
        ),
      );
    };
    const { isCollapsed } = allItems.filter(item => item.id === id)[0];

    return (
      <Box align="right">
        <IconButton skin="light" onClick={onCollapse}>
          {isCollapsed ? <Icons.ChevronDown /> : <Icons.ChevronUp />}
        </IconButton>
      </Box>
    );
  };

  const ItemText = ({ title, description }) => (
    <Box direction="vertical">
      <Text weight="normal">{title}</Text>
      {description && (
        <Text size="small" secondary>
          {description}
        </Text>
      )}
    </Box>
  );

  const [items, setItems] = React.useState([
    {
      id: 'item-1',
      addItemLabel: 'Add Step',
      options: [
        {
          value: (
            <ItemText
              title="Step 1"
              description="Research"
            />
          ),
        },
      ],
      children: [
        {
          id: 'item-1-child-1',
          options: [
            { value: <ItemText title="Collect data" /> },
          ],
        },
        {
          id: 'item-1-child-2',
          options: [
            { value: <ItemText title="Analyze data" /> },
          ],
        },
      ],
    },
    {
      id: 'item-2',
      isCollapsed: true,
      addItemLabel: 'Add Step',
      options: [
        {
          value: (
            <ItemText
              title="Step 2"
              description="Plan"
            />
          ),
        },
      ],
      children: [
        {
          id: 'item-2-child-1',
          options: [
            { value: <ItemText title="Consult experts" /> },
          ],
        },
        {
          id: 'item-2-child-2',
          options: [{ value: <ItemText title="Create plan" /> }],
        },
      ],
    },
    {
      id: 'item-3',
      isCollapsed: true,
      addItemLabel: 'Add Step',
      options: [
        {
          value: (
            <ItemText
              title="Step 3"
              description="Launch"
            />
          ),
        },
      ],
      children: [
        {
          id: 'item-3-child-1',
          options: [{ value: <ItemText title="Start with a soft launch" /> }],
        },
      ],
    },
  ]);

  const itemsWithUpdatedControls = items.map(item => {
    return {
      ...item,
      options: item.children
        ? [
            item.options[0],
            {
              value: <CollapseIcon id={item.id} allItems={items} />,
            },
          ]
        : [item.options[0]],
    };
  });

  return (
    <Card>
      <Card.Header
        title="Starting a business"
        suffix={
          <PopoverMenu
            triggerElement={
              <Button
                priority="secondary"
                prefixIcon={<Icons.Add />}
                size="small"
              >
                Add
              </Button>
            }
          >
            <PopoverMenu.MenuItem text="Add Step" />
            <PopoverMenu.MenuItem text="Add Section" />
          </PopoverMenu>
        }
      />
      <Card.Divider />
      <Box minHeight="1px" />
      <NestableList
        items={itemsWithUpdatedControls}
        onChange={onChangeData => setItems(onChangeData.items)}
        addItemLabel="Add Section"
      />
    </Card>
  );
};
```

### Rearrange the order of items
- description: <p>Use nestable lists to allow quick rearrangement of list items.</p><p></p><p>In <code><SidePanel/></code> or on other white backgrounds, use the <code>withBottomBorder</code> prop to add a border divider at the end of the list.</p>
- example: 
```jsx 
<SidePanel>
  <SidePanel.Header title="Site pages" />
  <Box gap="SP1" direction="vertical" height="502px">
    <Box margin="SP4 SP4 0 SP4">
      <SectionHelper
        title="Manage menus"
        onClose={() => {}}
        appearance="standard"
      >
        Go to any menu to customize which pages and links are displayed.
        <TextButton skin="dark" size="small" underline="always">
          More on menus
        </TextButton>
      </SectionHelper>
    </Box>
    <NestableList
      withBottomBorder
      items={[
        {
          id: 1,
          options: [{ value: <Text size="small">Home</Text> }],
        },
        {
          id: 2,
          options: [{ value: <Text size="small">About</Text> }],
        },
        {
          id: 3,
          options: [{ value: <Text size="small">Shop</Text> }],
        },
        {
          id: 4,
          options: [{ value: <Text size="small">Contact</Text> }],
        },
      ]}
      onChange={() => {}}
    />
  </Box>
  <SidePanel.Footer>
    <Box align="right">
      <Button prefixIcon={<Icons.Add />}>Add Page</Button>
    </Box>
  </SidePanel.Footer>
</SidePanel>;
```

### In panels
- description: <p>Use it to help manage complex lists</p>
- example: 
```jsx 
() => {
  const commonItemProps = {
    verticalPadding: 'tiny',
    dragHandleSize: 'small',
    horizontalPadding: 'small',
  };

  const Value = ({ children }) => {
    return (
      <Box gap="6px">
        <Icons.FolderSmall />
        <Text size="small">{children}</Text>
      </Box>
    );
  };

  const [items, setItems] = React.useState([
    {
      ...commonItemProps,
      id: 'item-1',
      options: [{ value: <Value>Item 1</Value> }],
    },
    {
      ...commonItemProps,
      id: 'item-2',
      isCollapsed: true,
      options: [{ value: <Value>Show and hide children</Value> }],
      children: [
        {
          ...commonItemProps,
          id: 'item-2-child-1',
          options: [{ value: <Value>Child 1</Value> }],
        },
        {
          ...commonItemProps,
          id: 'item-2-child-2',
          options: [{ value: <Value>Child 2</Value> }],
          children: [
            {
              ...commonItemProps,
              id: 'item-2-child-2-child-1',
              options: [{ value: <Value>Child 3</Value> }],
            },
          ],
        },
      ],
    },
    {
      ...commonItemProps,
      id: 'item-3',
      options: [{ value: <Value>Item 3</Value> }],
    },
  ]);

  const updateItemsWithControls = (items) => {
    return items.map((item) => {
      const newItem = {
        ...item,
        expandable: !!item.children,
        onClickExpand: () => onCollapse(item.id),
      };
      if (item.children) {
        newItem.children = updateItemsWithControls(item.children);
      }
      return newItem;
    });
  };

  const onCollapse = (id) => {
    setItems((allItems) =>
      allItems.map((item) =>
        item.id === id
          ? {
              ...item,
              isCollapsed: !item.isCollapsed,
              isExpanded: !item.isExpanded,
            }
          : {
              ...item,
              children: item.children
                ? toggleChildrenCollapse(item.children, id)
                : item.children,
            },
      ),
    );
  };

  const toggleChildrenCollapse = (children, id) => {
    return children.map((child) =>
      child.id === id
        ? {
            ...child,
            isCollapsed: !child.isCollapsed,
            isExpanded: !child.isExpanded,
          }
        : {
            ...child,
            children: child.children
              ? toggleChildrenCollapse(child.children, id)
              : child.children,
          },
    );
  };

  const itemsWithUpdatedControls = updateItemsWithControls(items);

  return (
    <SidePanel
      onCloseButtonClick={() => {}}
      skin="floating"
      width="288px"
      height="576px"
    >
      <SidePanel.Header title="Manage list" />
      <SidePanel.Content noPadding>
        <NestableList

        indentSize="medium"
          dividers={false}
          items={itemsWithUpdatedControls}
          onChange={(onChangeData) => setItems(onChangeData.items)}
        />
      </SidePanel.Content>
      <SidePanel.Footer>
        <Box direction="vertical" align="center">
          <Button size="small">Add Item</Button>
        </Box>
      </SidePanel.Footer>
    </SidePanel>
  );
};
```


