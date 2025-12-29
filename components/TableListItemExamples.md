
## Feature Examples


### Structure
- description: <p>Table list item organizes different sets of information into columns. It can have any number of columns, which can be added through <code>options</code>. </p><p></p><p>Add any content to the column with the <code>value</code> prop. </p><p></p><p>Note that column width and alignment can be controlled separately.</p>
- example: 
```jsx 
<TableListItem
  options={[
    {
      value: (
        <StorybookComponents.Placeholder>
          Column 1
        </StorybookComponents.Placeholder>
      ),
    },
    {
      value: (
        <StorybookComponents.Placeholder>
          Column 2
        </StorybookComponents.Placeholder>
      ),
    },
    {
      value: (
        <StorybookComponents.Placeholder>
          Column 3
        </StorybookComponents.Placeholder>
      ),
    },
    {
      value: (
        <StorybookComponents.Placeholder>
          Column 4
        </StorybookComponents.Placeholder>
      ),
    },
  ]}
/>;
```

### Padding
- description: <p>Adjust vertical spacing by using <code>verticalPadding</code> and <code>horizontalPadding</code> props. It supports 6 options:</p><p></p><li><code>xxTiny</code></li><li><code>xTiny</code></li><li><code>tiny</code> </li><li><code>small</code> (default)</li><li><code>medium</code></li><li><code>large</code> </li><p></p><p>Use tiny size set for compact lists that display more items in smaller space.</p><p>Small (default) is a standard list size for most common cases.</p><p>While medium and large are used to emphasize a few items.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem
    horizontalPadding="xxTiny"
    verticalPadding="xxTiny"
    options={[{ value: <Text>xxTiny</Text> }]}
  />
  <TableListItem
    horizontalPadding="xTiny"
    verticalPadding="xTiny"
    options={[{ value: <Text>xTiny</Text> }]}
  />
    <TableListItem
    horizontalPadding="tiny"
    verticalPadding="tiny"
    options={[{ value: <Text>Tiny</Text> }]}
  />
  <TableListItem
    horizontalPadding="small"
    verticalPadding="small"
    options={[{ value: <Text>Small (default)</Text> }]}
  />
  <TableListItem
    horizontalPadding="medium"
    verticalPadding="medium"
    options={[{ value: <Text>Medium</Text> }]}
  />
    <TableListItem
    horizontalPadding="large"
    verticalPadding="large"
    options={[{ value: <Text>Large</Text> }]}
  />
</StorybookComponents.Stack>;
```

### Drag handle size
- description: <p>Control a drag handle size with <code>dragHandleSize</code> prop. It supports two sizes: </p><li><code>small</code> is used for more compact lists</li><li><code>large</code> (default) is used for tables and more spacious UI layouts</li><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem
    draggable
    dragHandleSize="large"
    showDivider
    verticalPadding="tiny"
    options={[
      {
        value: <Text size="medium">Large drag handle (default)</Text>,
      },
    ]}
  />
  <TableListItem
    draggable
    dragHandleSize="small"
    showDivider
    horizontalPadding="tiny"
    verticalPadding="xTiny"
    options={[
      { width: 'auto' },
      {
        value: <Text size="small">Small drag handle</Text>,
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Draggable item indication
- description: <p>Control a drag grip icon with props:</p><li><code>draggable</code> marks that the component can be dragged.</li><li><code>dragging</code> indicates that the component is being dragged.</li><li><code>showDragHandleOnHover</code> shows handle only on hover</li><li><code>dragDisabled</code> show that the component can't be dragged.</li><p></p><p>Note, drag and drop logic is not part of this component. For this solution, go to <code><NestableList/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem draggable options={[{ value: <Text>Draggable</Text> }]} />
  <TableListItem
    draggable
    dragging
    options={[{ value: <Text>Draggable active</Text> }]}
  />
   <TableListItem
    draggable
    showDragHandleOnHover
    options={[{ value: <Text>Draggable on hover</Text> }]}
  />
  <TableListItem
    draggable
    dragDisabled
    options={[{ value: <Text>Draggable disabled</Text> }]}
  />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Control the appearance of the component using the <code>border</code> prop.</p><p>Use this property to emphasize the separation between items in a list.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem
    showDivider
    verticalPadding="tiny"
    options={[
      {
        value: <Text size="small">No border (default)</Text>,
      },
      
            ]}
          />
      
  <TableListItem
    border={true}
    showDivider
    verticalPadding="tiny"
    options={[
      {
        value: <Text size="small">Border</Text>,
      },
      
    ]}
  />
</StorybookComponents.Stack>;

```

###  Expandable
- description: <p>Give an ability to make an item expandable with <code>expanded</code> prop. </p>
- example: 
```jsx 
() => {
  const [isExpanded, setIsExpanded] = React.useState(false);

  return (
    <>
      <TableListItem
        expanded={isExpanded}
        expandable
        draggable
        dragHandleSize="small"
        showDivider
        horizontalPadding="tiny"
        verticalPadding="xTiny"
        onClickExpand={() => setIsExpanded(!isExpanded)}
        options={[
          {
            value: <Text size="small">Expandable</Text>,
          },
        
        ]}
      />
      {isExpanded && (
        <StorybookComponents.Placeholder>
          <Box verticalAlign="middle" align="center">
            <Text size="small">Content</Text>
          </Box>
        </StorybookComponents.Placeholder>
      )}
    </>
  );
};
```

### Selectable
- description: <p>Make an item selectable with the following props:</p><li>Use <code>checkbox</code> to enable the checkbox and show that the item can be selected.</li><li><code>checked </code>changes the checkbox's default state to selected.</li><li><code>showSelectionBorder</code> allows to turn off the blue strip indication when the item is selected</li><li><code>checkboxDisabled</code> disables the checkbox.</li><li><code>selectable</code> enables the selected state on the item</li>
- example: 
```jsx 
() => {
  const [checked, setChecked] = React.useState(false);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <TableListItem checkbox options={[{ value: <Text>Checkbox</Text> }]} />

      <TableListItem
        checkbox
        checked
        options={[{ value: <Text>Selected checkbox</Text> }]}
      />
      
            <TableListItem
        checkbox
        showSelectionBorder={false}
        checked
        options={[{ value: <Text>Selected checkbox without border</Text> }]}
      />
 
      <TableListItem
        checkbox
        checkboxDisabled
        options={[{ value: <Text>Disabled checkbox</Text> }]}
      />
      <TableListItem
        selectable
        onClick={() => setChecked((prev) => !prev)}
        checked={checked}
        options={[
          {
            value: <Text>Selectable</Text>,
          },
        ]}
      />
    </StorybookComponents.Stack>
  );
};

```

### Divider
- description: <p>Enable the bottom divider with <code>showDivider</code>, which visually separates the items.</p><p></p><p>Note that the last item on the list shouldn't have a bottom divider.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap={0}>
    <TableListItem options={[{ value: <Text>Divider off</Text> }]} />
    <TableListItem options={[{ value: <Text>Divider off</Text> }]} />
    <TableListItem options={[{ value: <Text>Divider off</Text> }]} />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap={0}>
    <TableListItem showDivider options={[{ value: <Text>Divider on</Text> }]} />
    <TableListItem showDivider options={[{ value: <Text>Divider on</Text> }]} />
    <TableListItem options={[{ value: <Text>Divider off</Text> }]} />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Column width
- description: <p>Control the width of columns with the <code>width</code> prop. It supports all CSS <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-columns">grid-column-template</a> values.</p>
- example: 
```jsx 
<TableListItem
  options={[
    {
      value: (
        <StorybookComponents.Placeholder>
          Width depends on content
        </StorybookComponents.Placeholder>
      ),
      width: 'max-content',
    },
    {
      value: (
        <StorybookComponents.Placeholder>
          Fills available space
        </StorybookComponents.Placeholder>
      ),
      width: '1fr',
    },
  ]}
/>;
```

### Column alignment
- description: <p>Align content inside of column cells using the <code>align</code> prop. It supports 3 values:</p><li><code>left</code> </li><li><code>center</code> </li><li><code>right</code> </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap={0}>
  <TableListItem
    showDivider
    options={[
      {
        value: <Text>Left</Text>,
        align: 'left',
      },
      {
        value: <Text>Center</Text>,
        align: 'center',
      },
      {
        value: <Text>Right</Text>,
        align: 'right',
      },
    ]}
  />
  <TableListItem
    options={[
      {
        value: <Text>Left with longer text</Text>,
        align: 'left',
      },
      {
        value: <Text>Center with longer text</Text>,
        align: 'center',
      },
      {
        value: <Text>Right with longer text</Text>,
        align: 'right',
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Actionable
- description: <p>Make an item actionable with the <code>onClick</code> prop. Once enabled, the item becomes interactive.</p><p></p><p>The <code><TableActionCell/></code> displays main and secondary actions.</p>
- example: 
```jsx 
<TableListItem
  onClick={() => {}}
  options={[
    { value: <Text>Actionable item</Text> },
    {
      value: (
        <TableActionCell
          primaryAction={{
            text: 'Click me',
            onClick: () => {},
          }}
        />
      ),
      align: 'right',
    },
  ]}
/>;
```




    


## Common Use Case Examples


### Grouped list
- description: <p>The <code>TableListItem</code> can be used to build lists that splits items into stages or categories. </p><p></p><p>Use <code><TableListHeader/></code> component to display titles for different sections. </p>
- example: 
```jsx 
<Box direction="vertical">
  <TableListHeader options={[{ value: 'In review' }]} />
  <TableListItem
    showDivider
    verticalPadding="tiny"
    onClick={() => {}}
    options={[
      {
        value: <Image width="90px" height="60px" src="TravelExample1.jpg" />,
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text weight="normal">Weekend by the Lake Como</Text>
            <Text size="small" secondary>
              Sep 23, 2022
            </Text>
          </Box>
        ),
      },
      {
        value: <Badge skin="warningLight">In review</Badge>,
        width: 'auto',
      },
      {
        value: (
          <TableActionCell
            size="small"
            primaryAction={{
              text: 'View',
              skin: 'standard',
              onClick: () => {},
            }}
            secondaryActions={[
              {
                text: 'Download',
                icon: <Icons.DownloadImportSmall />,
                onClick: () => {},
              },
              {
                text: 'Duplicate',
                icon: <Icons.DuplicateSmall />,
                onClick: () => {},
              },
              {
                text: 'Delete',
                icon: <Icons.DeleteSmall />,
                onClick: () => {},
              },
            ]}
            numOfVisibleSecondaryActions={0}
          />
        ),
        width: 'auto',
      },
    ]}
  />
  <TableListItem
    verticalPadding="tiny"
    onClick={() => {}}
    options={[
      {
        value: <Image width="90px" height="60px" src="TravelExample2.jpg" />,
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text weight="normal">Top 10 Restaurants in London Chinatown</Text>
            <Text size="small" secondary>
              Jun 1, 2022
            </Text>
          </Box>
        ),
      },
      {
        value: <Badge skin="warningLight">In review</Badge>,
        width: 'auto',
      },
      {
        value: (
          <TableActionCell
            size="small"
            primaryAction={{
              text: 'View',
              skin: 'standard',
              onClick: () => {},
            }}
            secondaryActions={[
              {
                text: 'Download',
                icon: <Icons.DownloadImportSmall />,
                onClick: () => {},
              },
              {
                text: 'Duplicate',
                icon: <Icons.DuplicateSmall />,
                onClick: () => {},
              },
              {
                text: 'Delete',
                icon: <Icons.DeleteSmall />,
                onClick: () => {},
              },
            ]}
            numOfVisibleSecondaryActions={0}
          />
        ),
        width: 'auto',
      },
    ]}
  />
  <TableListHeader options={[{ value: 'Approved' }]} />
  <TableListItem
    showDivider
    verticalPadding="tiny"
    onClick={() => {}}
    options={[
      {
        value: <Image width="90px" height="60px" src="TravelExample7.jpg" />,
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text weight="normal">Bucket List: Indonesia</Text>
            <Text size="small" secondary>
              Apr 13, 2022
            </Text>
          </Box>
        ),
      },
      {
        value: <Badge skin="neutralSuccess">Approved</Badge>,
        width: 'auto',
      },
      {
        value: (
          <TableActionCell
            size="small"
            primaryAction={{
              text: 'View',
              skin: 'standard',
              onClick: () => {},
            }}
            secondaryActions={[
              {
                text: 'Download',
                icon: <Icons.DownloadImportSmall />,
                onClick: () => {},
              },
              {
                text: 'Duplicate',
                icon: <Icons.DuplicateSmall />,
                onClick: () => {},
              },
              {
                text: 'Delete',
                icon: <Icons.DeleteSmall />,
                onClick: () => {},
              },
            ]}
            numOfVisibleSecondaryActions={0}
          />
        ),
        width: 'auto',
      },
    ]}
  />
  <TableListItem
    showDivider
    verticalPadding="tiny"
    onClick={() => {}}
    options={[
      {
        value: <Image width="90px" height="60px" src="TravelExample4.jpg" />,
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text weight="normal">A weekend in a desert</Text>
            <Text size="small" secondary>
              May 19, 2022
            </Text>
          </Box>
        ),
      },
      {
        value: <Badge skin="neutralSuccess">Approved</Badge>,
        width: 'auto',
      },
      {
        value: (
          <TableActionCell
            size="small"
            primaryAction={{
              text: 'View',
              skin: 'standard',
              onClick: () => {},
            }}
            secondaryActions={[
              {
                text: 'Download',
                icon: <Icons.DownloadImportSmall />,
                onClick: () => {},
              },
              {
                text: 'Duplicate',
                icon: <Icons.DuplicateSmall />,
                onClick: () => {},
              },
              {
                text: 'Delete',
                icon: <Icons.DeleteSmall />,
                onClick: () => {},
              },
            ]}
            numOfVisibleSecondaryActions={0}
          />
        ),
        width: 'auto',
      },
    ]}
  />
  <TableListItem
    showDivider
    verticalPadding="tiny"
    onClick={() => {}}
    options={[
      {
        value: <Image width="90px" height="60px" src="TravelExample5.jpg" />,
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text weight="normal">Top places to visit in Portugal</Text>
            <Text size="small" secondary>
              Mar 30, 2022
            </Text>
          </Box>
        ),
      },
      {
        value: <Badge skin="neutralSuccess">Approved</Badge>,
        width: 'auto',
      },
      {
        value: (
          <TableActionCell
            size="small"
            primaryAction={{
              text: 'View',
              skin: 'standard',
              onClick: () => {},
            }}
            secondaryActions={[
              {
                text: 'Download',
                icon: <Icons.DownloadImportSmall />,
                onClick: () => {},
              },
              {
                text: 'Duplicate',
                icon: <Icons.DuplicateSmall />,
                onClick: () => {},
              },
              {
                text: 'Delete',
                icon: <Icons.DeleteSmall />,
                onClick: () => {},
              },
            ]}
            numOfVisibleSecondaryActions={0}
          />
        ),
        width: 'auto',
      },
    ]}
  />
</Box>;
```


