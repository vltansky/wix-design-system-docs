
## Feature Examples


### Structure
- description: <p>Toolbars consist of 2 empty <code><TableToolbar.ItemGroup/></code> containers.</p><p>To add content like filter dropdowns or search inputs use the <code><TableToolbar.Item/></code> wrapper. The required margins will automatically be applied.</p>
- example: 
```jsx 
<Card>
  <TableToolbar>
    <TableToolbar.ItemGroup>
      <TableToolbar.Item>
        <StorybookComponents.Placeholder>
          Left aligned content
        </StorybookComponents.Placeholder>
      </TableToolbar.Item>
    </TableToolbar.ItemGroup>
    <TableToolbar.ItemGroup>
      <TableToolbar.Item>
        <StorybookComponents.Placeholder>
          Right aligned content
        </StorybookComponents.Placeholder>
      </TableToolbar.Item>
    </TableToolbar.ItemGroup>
  </TableToolbar>
</Card>;
```

### Title
- description: <p>Add titles to describe the table content using <code><TableToolbar.Title/></code>.</p>
- example: 
```jsx 
<Card>
  <TableToolbar>
    <TableToolbar.ItemGroup>
      <TableToolbar.Item>
        <TableToolbar.Title>Title</TableToolbar.Title>
      </TableToolbar.Item>
    </TableToolbar.ItemGroup>
  </TableToolbar>
</Card>;
```

### Label
- description: <p>Use <code><TableToolbar.Label/></code> to add a text label for filter options or a count of existing items.</p>
- example: 
```jsx 
<Card>
  <TableToolbar>
    <TableToolbar.ItemGroup>
      <TableToolbar.Item>
        <TableToolbar.Label>12 products</TableToolbar.Label>
      </TableToolbar.Item>
    </TableToolbar.ItemGroup>
  </TableToolbar>
</Card>;
```

### Main toolbar
- description: <p>The main toolbar appears above each table. It consists of descriptive info and optional data filters which can be easily edited to fit the user's goals.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Title>Title</TableToolbar.Title>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Title>Title</TableToolbar.Title>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Title>Title</TableToolbar.Title>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Title>Title</TableToolbar.Title>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Title>Title</TableToolbar.Title>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Button
            priority="secondary"
            prefixIcon={<Icons.ContentFilterSmall />}
            size="small"
          >
            Filter
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Label>3 items</TableToolbar.Label>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Label>3 items</TableToolbar.Label>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Label>3 items</TableToolbar.Label>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Label>3 items</TableToolbar.Label>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <TableToolbar.Label>3 items</TableToolbar.Label>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Button
            priority="secondary"
            prefixIcon={<Icons.ContentFilterSmall />}
            size="small"
          >
            Filter
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Dropdown
            size="small"
            border="round"
            selectedId={0}
            options={[
              { id: 0, value: 'All options' },
              { id: 1, value: 'Option 1' },
              { id: 2, value: 'Option 2' },
              { id: 3, value: 'Option 3' },
            ]}
          />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <FormField labelPlacement="left" label="Label">
            <Dropdown
              size="small"
              border="round"
              selectedId={0}
              options={[
                { id: 0, value: 'All options' },
                { id: 1, value: 'Option 1' },
                { id: 2, value: 'Option 2' },
                { id: 3, value: 'Option 3' },
              ]}
            />
          </FormField>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <FormField labelPlacement="left" label="Label">
            <Dropdown
              size="small"
              border="round"
              selectedId={0}
              options={[
                { id: 0, value: 'All options' },
                { id: 1, value: 'Option 1' },
                { id: 2, value: 'Option 2' },
                { id: 3, value: 'Option 3' },
              ]}
            />
          </FormField>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <FormField labelPlacement="left" label="Label">
            <Dropdown
              size="small"
              border="round"
              selectedId={0}
              options={[
                { id: 0, value: 'All options' },
                { id: 1, value: 'Option 1' },
                { id: 2, value: 'Option 2' },
                { id: 3, value: 'Option 3' },
              ]}
            />
          </FormField>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
      <TableToolbar.ItemGroup>
        <TableToolbar.Item>
          <Search size="small" />
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
</StorybookComponents.Stack>;
```

### Actions toolbar
- description: <p>The actions toolbar only appears in tables with an enabled item selection. It replaces the main toolbar when at least one item is selected.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <Text size="small" weight="normal">
            3 selected
          </Text>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.DuplicateSmall />}
          >
            Duplicate
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <PopoverMenu
            triggerElement={
              <Button
                skin="inverted"
                size="small"
                suffixIcon={<Icons.ChevronDownSmall />}
              >
                More Actions
              </Button>
            }
          >
            <PopoverMenu.MenuItem
              prefixIcon={<Icons.Discount />}
              text="Add discount"
            />
            <PopoverMenu.MenuItem
              prefixIcon={<Icons.Collections />}
              text="Add to collection"
            />
            <PopoverMenu.MenuItem prefixIcon={<Icons.Delete />} text="Delete" />
          </PopoverMenu>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
  <Card>
    <TableToolbar>
      <TableToolbar.ItemGroup position="start">
        <TableToolbar.Item>
          <Box gap="12px">
            <Box gap="3px">
              <Text size="small" weight="bold">
                3
              </Text>
              <Text size="small">out of 96 selected</Text>
            </Box>
            <TextButton size="small" weight="normal">
              Select All
            </TextButton>
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item>
          <Box height="18px">
            <Divider direction="vertical" />
          </Box>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.UploadExportSmall />}
          >
            Export
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <Button
            skin="inverted"
            size="small"
            prefixIcon={<Icons.DuplicateSmall />}
          >
            Duplicate
          </Button>
        </TableToolbar.Item>
        <TableToolbar.Item layout="button">
          <PopoverMenu
            triggerElement={
              <Button
                skin="inverted"
                size="small"
                suffixIcon={<Icons.ChevronDownSmall />}
              >
                More Actions
              </Button>
            }
          >
            <PopoverMenu.MenuItem
              prefixIcon={<Icons.Discount />}
              text="Add discount"
            />
            <PopoverMenu.MenuItem
              prefixIcon={<Icons.Collections />}
              text="Add to collection"
            />
            <PopoverMenu.MenuItem prefixIcon={<Icons.Delete />} text="Delete" />
          </PopoverMenu>
        </TableToolbar.Item>
      </TableToolbar.ItemGroup>
    </TableToolbar>
  </Card>
</StorybookComponents.Stack>;
```




    


