
## Feature Examples


### Structure
- description: <p>The component consists of 2 core parts:</p><li>A <code><Layout/></code> wrapper that defines the total number of columns in the container, the default is 12 columns.</li><li>A <code><Cell/></code> that contains any type of content (for example, a form field). The user can define how many columns and rows it spans, the default is 12 columns and 1 row.</li>
- example: 
```jsx 
<Layout>
  <Cell>
    <StorybookComponents.Placeholder>Cell</StorybookComponents.Placeholder>
  </Cell>
</Layout>;
```

### Columns
- description: <p>Use <code>span </code>to control the width of a content <code><Cell/></code>,by specifying the number of grid columns a cell will occupy. If not specified, it will occupy all 12 columns (full width).</p>
- example: 
```jsx 
<Layout>
  <Cell>
    <StorybookComponents.Placeholder>12 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>6 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>6 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={4}>
    <StorybookComponents.Placeholder>4 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={4}>
    <StorybookComponents.Placeholder>4 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={4}>
    <StorybookComponents.Placeholder>4 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={3}>
    <StorybookComponents.Placeholder>3 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={3}>
    <StorybookComponents.Placeholder>3 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={3}>
    <StorybookComponents.Placeholder>3 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={3}>
    <StorybookComponents.Placeholder>3 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={2}>
    <StorybookComponents.Placeholder>2 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={2}>
    <StorybookComponents.Placeholder>2 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={2}>
    <StorybookComponents.Placeholder>2 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={2}>
    <StorybookComponents.Placeholder>2 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={2}>
    <StorybookComponents.Placeholder>2 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={2}>
    <StorybookComponents.Placeholder>2 cols</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={1}>
    <StorybookComponents.Placeholder>1 col</StorybookComponents.Placeholder>
  </Cell>
</Layout>;
```

### Rows
- description: <p>Use <code>rows</code> to specify the number of grid rows the <code><Cell/></code> occupies, the default is 1 row.</p>
- example: 
```jsx 
<Layout>
  <Cell span={6} rows={6}>
    <StorybookComponents.Placeholder>6 rows</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
  </Cell>
  <Cell span={6}>
    <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
  </Cell>
</Layout>;
```

### Row height
- description: <p>The height of rows inside a layout can be set individually or altogether:</p><li>By default, each row is sized separately. The height is determined by the item of the greatest height within the row.</li><li>To size all rows equally, choose to set them according to the item of the greatest height within the layout by setting all of them to <code>rowHeight=1fr </code>or set them in pixels, with <code>rowHeight</code>.</li>
- example: 
```jsx 
<Layout cols={1} gap="60px">
  <Layout>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        This layout uses the default sizing which stretches cells vertically to match the item of
        greatest height in the row. The height of the first row
        is different than the second row, because of the text in this cell.
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
  </Layout>
  <Layout rowHeight="1fr">
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Here all the rows are sized equally, according to the item with the greatest height in the layout. All of the rows are 
        set to 1fr and have the same height.
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
  </Layout>
  <Layout rowHeight="60px">
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Here the row height is set in pixels, all cells in all rows have the same height.
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>1 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>2 row</StorybookComponents.Placeholder>
    </Cell>
  </Layout>
</Layout>;
```

### Gap
- description: <p>Control the space between content cells with <code>gap</code> property. The same gap is applied horizontally and vertically (between rows and columns).</p><p></p><p>The default gap value is 24px.</p>
- example: 
```jsx 
<Layout cols={2}>
  <Layout gap="24px">
    <Cell>
      <StorybookComponents.Placeholder>
        24px gap (default)
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell>
      <StorybookComponents.Placeholder>
        24px gap
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell>
      <StorybookComponents.Placeholder>
        24px gap
      </StorybookComponents.Placeholder>
    </Cell>
  </Layout>
  <Layout gap="0px">
    <Cell>
      <StorybookComponents.Placeholder>No gap</StorybookComponents.Placeholder>
    </Cell>
    <Cell>
      <StorybookComponents.Placeholder>No gap</StorybookComponents.Placeholder>
    </Cell>
    <Cell>
      <StorybookComponents.Placeholder>No gap</StorybookComponents.Placeholder>
    </Cell>
  </Layout>
</Layout>;
```

### Align items
- description: <p>By default, all cells inside of the row stretch vertically according to the cell of the greatest height in the row.</p><p></p><p>Size each cell separately according to its content and align it vertically with <code>alignItems</code>, it supports all <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/align-items">CSS values.</a></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Layout>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Stretched
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Stretched
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder height="120px">
        Stretched
      </StorybookComponents.Placeholder>
    </Cell>
  </Layout>
  <Layout alignItems="flex-start">
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Top aligned
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Top aligned
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder height="120px">
        Top aligned
      </StorybookComponents.Placeholder>
    </Cell>
  </Layout>
</StorybookComponents.Stack>;
```

### Justify items
- description: <p>By default, cells inside of the row stretch horizontally.</p><p></p><p>Size each cell separately according to its content and align it horizontally with <code>justifyItems</code> prop.</p><p></p><p>It supports all <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/justify-items">CSS values</a>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Layout>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Stretched
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Stretched
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        Stretched
      </StorybookComponents.Placeholder>
    </Cell>
  </Layout>
  <Layout justifyItems="end">
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        End Aligned
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        End Aligned
      </StorybookComponents.Placeholder>
    </Cell>
    <Cell span={4}>
      <StorybookComponents.Placeholder>
        End Aligned
      </StorybookComponents.Placeholder>
    </Cell>
  </Layout>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Card layout
- description: <p>Use layout to arrange content in columns and rows inside of cards and widgets.</p>
- example: 
```jsx 
() => {
  const [checked, setChecked] = React.useState(true);
  return (
    <Card>
      <Card.Header title="Menu info" />
      <Card.Divider />
      <Card.Content>
        <Layout>
          <Cell span={8}>
            <FormField label="Name">
              <Input />
            </FormField>
          </Cell>
          <Cell span={8}>
            <FormField label="Description">
              <InputArea
                minHeight={120}
                resizable
                placeholder="Get people excited about your menu and food"
              />
            </FormField>
          </Cell>
          <Cell>
            <Box>
              <FormField label="Visible for customers" labelPlacement="right">
                <ToggleSwitch
                  checked={checked}
                  onChange={() => setChecked(!checked)}
                  size="medium"
                />
              </FormField>
            </Box>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};
```

### Page layout
- description: <p>Use layout to arrange content inside of a page. Check <code><Page/></code> for all common layouts.</p>
- example: 
```jsx 
<Page>
  <Page.Header title="Main Menu"></Page.Header>
  <Page.Content>
    <Layout>
      <Cell>
        <Layout>
          <Cell span={8}>
            <Card>
              <Card.Header
                title="Sections"
                suffix={
                  <Button size="small" prefixIcon={<Icons.AddSmall />}>
                    New Section
                  </Button>
                }
              />
              <Card.Divider />
              <Box height="480px" />
            </Card>
          </Cell>
          <Cell span={4}>
            <Card>
              <Card.Header
                title="Menu info"
                suffix={
                  <Button
                    size="small"
                    priority="secondary"
                    prefixIcon={<Icons.EditSmall />}
                  >
                    Edit
                  </Button>
                }
              />
              <Card.Divider />
              <Box height="240px" />
            </Card>
          </Cell>
        </Layout>
      </Cell>
    </Layout>
  </Page.Content>
</Page>;
```


