
## Feature Examples


### Size
- description: <p>Control the size of primary and secondary actions displayed in a table cell with the <code>size</code> prop. Component supports 2 sizes:</p><li><code>medium</code> - use in all common cases</li><li><code>small</code> - use for dense tables</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem
    onClick={() => {}}
    options={[
      {
        value: (
          <TableActionCell
            size="medium"
            primaryAction={{
              text: 'Medium',
            }}
          />
        ),
      },
    ]}
  />
  <TableListItem
    onClick={() => {}}
    options={[
      {
        value: (
          <TableActionCell
            size="small"
            primaryAction={{
              text: 'Small',
            }}
          />
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Primary action
- description: <p>Define a main action of a cell with the <code>primaryAction</code> prop. Action will be revealed on table row hover only.</p>
- example: 
```jsx 
<TableListItem
  onClick={() => {}}
  options={[
    {
      value: (
        <TableActionCell
          primaryAction={{
            text: 'Primary Action',
          }}
        />
      ),
    },
  ]}
/>;
```

### Primary action visibility
- description: <p>Control the appearance of a primary action with the <code>visibility</code> prop. It supports 2 options:</p><li><code>onHover</code> (default) - button is only visible when the mouse hovers over  item.</li><li><code>always</code> - button is always visible and appears as a secondary button.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem
    onClick={() => {}}
    options={[
      {
        value: (
          <TableActionCell
            primaryAction={{
              text: 'On Hover',
              visibility: 'onHover',
            }}
          />
        ),
      },
    ]}
  />
  <TableListItem
    onClick={() => {}}
    options={[
      {
        value: (
          <TableActionCell
            primaryAction={{
              text: 'Always',
              visibility: 'always',
            }}
          />
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Primary action icon affix
- description: <p>Give more context to the primary action by adding an icon affix. It can be added to 2 locations:</p><li><code>prefixIcon</code> - use to add a descriptive icon in front of a label</li><li><code>suffixIcon</code> - use to add a directional icon at the end of a label</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TableListItem
    onClick={() => {}}
    options={[
      {
        value: (
          <TableActionCell
            primaryAction={{
              text: 'Add Members',
              prefixIcon: <Icons.UserAdd />,
            }}
          />
        ),
      },
    ]}
  />
  <TableListItem
    onClick={() => {}}
    options={[
      {
        value: (
          <TableActionCell
            primaryAction={{
              text: 'View',
              suffixIcon: <Icons.ChevronRight />,
            }}
          />
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Secondary actions
- description: <p>Define an array of additional actions for each row with the <code>secondaryActions</code> prop. Icon and text label are required to be specified. Actions will be listed in a popover menu.</p><p>Add the label for an icon button that opens up a popover menu using <code>moreActionsTooltipText</code>. Recommended label text: 'More actions'. It will be shown in a tooltip on hover or focus.</p>
- example: 
```jsx 
<TableListItem
  onClick={() => {}}
  options={[
    {
      value: (
        <TableActionCell
          secondaryActions={[
            {
              text: 'Star',
              icon: <Icons.FavoriteSmall />,
              onClick: () => {},
            },
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
              text: 'Print',
              icon: <Icons.PrintSmall />,
              onClick: () => {},
            },
          ]}
          moreActionsTooltipText="More actions"
        />
      ),
    },
  ]}
/>;
```

### Number of visible secondary actions
- description: <p>Display a selected number of secondary actions as icon buttons with the <code>numOfVisibleSecondaryActions</code> prop. By default actions will be revealed on hover only. </p><p></p><p>To display the icons all the time use the <code>alwaysShowSecondaryActions</code> prop.</p>
- example: 
```jsx 
() => {
  const secondaryActions = [
    {
      text: 'Star',
      icon: <Icons.Favorite />,
      onClick: () => {},
    },
    {
      text: 'Download',
      icon: <Icons.DownloadImport />,
      onClick: () => {},
    },
    {
      text: 'Duplicate',
      icon: <Icons.DuplicateSmall />,
      onClick: () => {},
    },
    {
      text: 'Print',
      icon: <Icons.PrintSmall />,
      onClick: () => {},
    },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <TableListItem
        onClick={() => {}}
        options={[
          {
            value: (
              <TableActionCell
                secondaryActions={secondaryActions}
                numOfVisibleSecondaryActions={2}
              />
            ),
          },
        ]}
      />
      <TableListItem
        onClick={() => {}}
        options={[
          {
            value: (
              <TableActionCell
                secondaryActions={secondaryActions}
                numOfVisibleSecondaryActions={2}
                alwaysShowSecondaryActions
              />
            ),
          },
        ]}
      />
    </StorybookComponents.Stack>
  );
};
```

### Divider
- description: <p>Add a separating line to group related actions or distinguish destructive actions from the rest. Do it in a popover menu by rendering <code>divider</code> as a separate action in the <code>secondaryActions</code> array. </p><p></p><p></p>
- example: 
```jsx 
() => {
  const secondaryActions = [
    {
      text: 'Star',
      icon: <Icons.FavoriteSmall />,
      onClick: () => {},
    },
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
      divider: true,
    },
    {
      text: 'Delete',
      icon: <Icons.DeleteSmall />,
      onClick: () => {},
    },
  ];

  return (
    <TableListItem
      onClick={() => {}}
      options={[
        {
          value: <TableActionCell secondaryActions={secondaryActions} />,
        },
      ]}
    />
  );
};
```

### Disabled
- description: <p>Disable all interactions for primary or secondary actions with the <code>disabled</code> prop. Use it to highlight unavailable functions.</p><p>Always provide an explanation for the user why actions cannot be accessed. Use <code>disabledDescription</code> prop to show a descriptive message in a tooltip.</p><p><em>Note</em>: at the moment description can be added to visible secondary actions only.</p>
- example: 
```jsx 
() => {
  const primaryAction = {
    text: 'Edit',
    disabled: true,
  };

  const secondaryActions = [
    {
      text: 'Star',
      icon: <Icons.Star />,
      onClick: () => {},
      disabled: true,
      disabledDescription:
        'Message that explains why user cannot access this action',
    },
    {
      text: 'Download',
      icon: <Icons.Download />,
      onClick: () => {},
      disabled: true,
      disabledDescription:
        'Message that explains why user cannot access this action',
    },
    {
      text: 'Duplicate',
      icon: <Icons.DuplicateSmall />,
      onClick: () => {},
      disabled: true,
    },
    {
      text: 'Print',
      icon: <Icons.PrintSmall />,
      onClick: () => {},
      disabled: true,
    },
  ];

  return (
    <TableListItem
      onClick={() => {}}
      options={[
        {
          value: (
            <TableActionCell
              primaryAction={primaryAction}
              secondaryActions={secondaryActions}
              numOfVisibleSecondaryActions={2}
            />
          ),
        },
      ]}
    />
  );
};
```

### Popover menu
- description: <p>Customize the appearance of secondary actions popover menu with <code>popoverMenuProps</code>.</p><p>Check <code><PopoverMenu/></code> API for a full list of available properties.</p>
- example: 
```jsx 
() => {
  const secondaryActions = [
    {
      text: 'Mark as favorite',
      icon: <Icons.FavoriteSmall />,
      onClick: () => {},
    },
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
      divider: true,
    },
    {
      text: 'Delete',
      icon: <Icons.DeleteSmall />,
      onClick: () => {},
    },
  ];

  return (
    <TableListItem
      onClick={() => {}}
      options={[
        {
          value: (
            <TableActionCell
              popoverMenuProps={{
                placement: 'bottom',
                showArrow: false,
                textSize: 'small',
                maxWidth: '90px',
                ellipsis: true,
              }}
              secondaryActions={secondaryActions}
            />
          ),
        },
      ]}
    />
  );
};
```




    


## Common Use Case Examples


### Row actions
- description: <p>Use table action cell to display row actions in the last column of a data table. </p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: `Light grey hoodie`,
      SKU: '00224239',
      price: '$59.00',
      inventory: 'In stock',
    },
    {
      name: `Black watch`,
      SKU: '00352464',
      price: '$229.00',
      inventory: 'In stock',
    },
    {
      name: 'Reading glasses',
      SKU: '00486430',
      price: '$69.00',
      inventory: 'In stock',
    },
    {
      name: 'Leather shoes',
      SKU: '00515642',
      price: '$129.00',
      inventory: 'Out of stock',
    },
  ];

  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'SKU', render: row => row.SKU },
    { title: 'Inventory', render: row => row.inventory },
    { title: 'Price', render: row => row.price },
    {
      render: () => (
        <TableActionCell
          onClick={() => {}}
          primaryAction={{
            text: 'Edit',
          }}
          secondaryActions={[
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
        />
      ),
    },
  ];

  return (
    <Card>
      <Table data={records} columns={columns} onRowClick={() => {}}>
        <TableToolbar>
          <TableToolbar.Title>Products</TableToolbar.Title>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Groups
- description: <p>Use dividers to group large lists of actions in a secondary actions menu.</p>
- example: 
```jsx 
() => {
  const data = [
    {
      imageSrc: 'TravelExample1.jpg',
      title: 'Weekend by the Lake Como',
      subtitle: 'Jun 1, 2020 • Matthew W.',
      translations: 'English, Lithuanian',
    },
    {
      imageSrc: 'TravelExample2.jpg',
      title: 'Top 10 Restaurants in London Chinatown',
      subtitle: 'Jun 1, 2020 • Matthew W.',
      translations: 'English',
    },
    {
      imageSrc: 'TravelExample7.jpg',
      title: 'Bucket List: Indonesia',
      subtitle: 'Jun 1, 2020 • Matthew W.',
      translations: 'English',
    },
  ];

  const [activeSearch, setActiveSearch] = React.useState('');
  const [filteredData, setFilteredData] = React.useState(data);

  const renderDescription = (title, subtitle) => (
    <Box direction="vertical" verticalAlign="middle">
      <Text size="medium" weight="normal">
        {title}
      </Text>
      <Text size="tiny" secondary>
        {subtitle}
      </Text>
    </Box>
  );

  const records = filteredData.map(
    ({ imageSrc, title, subtitle, translations }) => ({
      image: <Image width="90px" height="60px" src={imageSrc} />,
      name: (
        <Box direction="vertical" verticalAlign="middle">
          <Text size="medium" weight="normal">
            {title}
          </Text>
          <Text size="tiny" secondary>
            {subtitle}
          </Text>
        </Box>
      ),
      translations,
    }),
  );

  const findFilteredData = activeSearch => {
    setFilteredData(
      data.filter(({ title, subtitle, translations }) => {
        const searchData = [title, subtitle, translations]
          .join(' ')
          .toLowerCase();

        const searchQuery = activeSearch.trim().toLowerCase();

        if (searchQuery && searchData.indexOf(searchQuery) === -1) {
          return false;
        }

        return true;
      }),
    );

    setActiveSearch(activeSearch);
  };

  const columns = [
    { title: '', width: '90px', render: row => row.image },
    { title: 'Name', width: '40%', render: row => row.name },
    { title: 'Translations', render: row => row.translations },
    {
      render: () => (
        <TableActionCell
          onClick={() => {}}
          popoverMenuProps={{
            maxWidth: 'max-content',
          }}
          secondaryActions={[
            {
              text: 'View post',
              icon: <Icons.VisibleSmall />,
              onClick: () => {},
            },
            {
              text: 'Share post',
              icon: <Icons.ShareSmall />,
              onClick: () => {},
            },
            {
              text: 'View post report',
              icon: <Icons.StatisticsSmall />,
              onClick: () => {},
            },
            {
              divider: true,
            },
            {
              text: 'Add to a subscription plan',
              icon: <Icons.PaymentSmall />,
              onClick: () => {},
            },
            {
              text: 'Translate post',
              icon: <Icons.LanguagesSmall />,
              onClick: () => {},
            },
            {
              text: 'Change language',
              icon: <Icons.ReplaceSmall />,
              onClick: () => {},
            },
            {
              divider: true,
            },
            {
              text: 'Duplicate post',
              icon: <Icons.DuplicateSmall />,
              onClick: () => {},
            },
            {
              text: 'Revert to draft',
              icon: <Icons.RefreshSmall />,
              onClick: () => {},
            },
            {
              text: 'Move to trash',
              icon: <Icons.DeleteSmall />,
              onClick: () => {},
            },
          ]}
        />
      ),
    },
  ];

  return (
    <Card>
      <Table data={records} columns={columns}>
        <TableToolbar>
          <TableToolbar.ItemGroup>
            <TableToolbar.Item>
              <Text size="small" secondary>
                3 posts
              </Text>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
          <TableToolbar.ItemGroup>
            <TableToolbar.Item>
              <Search
                size="small"
                value={activeSearch}
                onChange={event => findFilteredData(event.target.value)}
              />
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};
```


