
## Feature Examples


### Size
- description: <p>Adjust the component size using the <code>size</code> prop. Choose from 3 sizes:</p><li><code>medium</code> (default) - can be used in all common cases.</li><li><code>small</code> -  best for dense layouts.</li><li><code>tiny</code> - should be used sparingly, for dense and narrow layouts.</li><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <Badge uppercase="false" size="medium">Medium</Badge>
    <Badge uppercase="false" size="small">Small</Badge>
    <Badge  uppercase="false" size="tiny">Tiny</Badge>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Type
- description: <p>Control the appearance of the badge according to its priority with the <code>type</code> prop. Choose from 3 styles:</p><li><code>solid</code> (default)</li><li><code>outlined</code></li><li><code>transparent</code></li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <Badge uppercase="false" type="solid">Solid</Badge>
    <Badge uppercase="false" type="outlined">Outlined</Badge>
    <Badge  uppercase="false"type="transparent">Transparent</Badge>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the appearance of badges with the <code>skin</code> prop. Choose from 13 skins:</p><li><code>general</code> (default) - used for default statuses.</li><li><code>standard</code>, <code>neutralStandard</code> - used for statuses that are relevant to current user task.</li><li><code>danger</code>, <code>neutralDanger</code> - used for critical issues that require user action.</li><li><code>success</code>, <code>neutralSuccess</code> - used for success or positive status.</li><li><code>neutral</code>, <code>neutralLight</code> - used for completed or pending status, when no action is needed at the moment.</li><li><code>warning</code>, <code>warningLight</code> - used for unresolved, but not critical issues.</li><li><code>urgent</code> - used for unresolved and time sensitive issues that require user action.</li><li><code>premium</code> - used for items or functions related to Premium Plans.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <Badge uppercase="false"  skin="general">General</Badge>
    <Badge uppercase="false"  skin="standard">Standard</Badge>
    <Badge uppercase="false"  skin="danger">Danger</Badge>
    <Badge uppercase="false"  skin="success">Success</Badge>
    <Badge uppercase="false" skin="neutral">Neutral</Badge>
    <Badge uppercase="false"  skin="warning">Warning</Badge>
    <Badge uppercase="false"  skin="urgent">Urgent</Badge>
    <Badge uppercase="false"  skin="premium">Premium</Badge>
  </StorybookComponents.Stack>

  <StorybookComponents.Stack flexDirection="column" margin="54px 0">
    <Badge uppercase="false"  skin="neutralStandard">Neutral Standard</Badge>
    <Badge uppercase="false"  skin="neutralDanger">Neutral Danger</Badge>
    <Badge uppercase="false"  skin="neutralSuccess">Neutral Success</Badge>
    <Badge uppercase="false"  skin="neutralLight">Neutral Light</Badge>
    <Badge uppercase="false"  skin="warningLight">Warning Light</Badge>
  </StorybookComponents.Stack>

  <StorybookComponents.Stack flexDirection="column">
    <Badge uppercase="false"  skin="general" type="outlined">
      General
    </Badge>
    <Badge uppercase="false"  skin="standard" type="outlined">
      Standard
    </Badge>
    <Badge  uppercase="false" skin="danger" type="outlined">
      Danger
    </Badge>
    <Badge  uppercase="false" skin="success" type="outlined">
      Success
    </Badge>
    <Badge uppercase="false"  skin="neutral" type="outlined">
      Neutral
    </Badge>
    <Badge uppercase="false"  skin="warning" type="outlined">
      Warning
    </Badge>
    <Badge uppercase="false"  skin="urgent" type="outlined">
      Urgent
    </Badge>
    <Badge uppercase="false"  skin="premium" type="outlined">
      Premium
    </Badge>
  </StorybookComponents.Stack>

  <StorybookComponents.Stack flexDirection="column" margin="54px 0">
    <Badge uppercase="false"  skin="neutralStandard" type="outlined">
      Neutral Standard
    </Badge>
    <Badge uppercase="false"  skin="neutralDanger" type="outlined">
      Neutral Danger
    </Badge>
    <Badge  uppercase="false" skin="neutralSuccess" type="outlined">
      Neutral Success
    </Badge>
    <Badge uppercase="false"  skin="neutralLight" type="outlined">
      Neutral Light
    </Badge>
    <Badge uppercase="false"  skin="warningLight" type="outlined">
      Warning Light
    </Badge>
  </StorybookComponents.Stack>

  <StorybookComponents.Stack flexDirection="column">
    <Badge uppercase="false"  skin="general" type="transparent">
      General
    </Badge>
    <Badge uppercase="false"  skin="standard" type="transparent">
      Standard
    </Badge>
    <Badge uppercase="false"  skin="danger" type="transparent">
      Danger
    </Badge>
    <Badge uppercase="false"  skin="success" type="transparent">
      Success
    </Badge>
    <Badge  uppercase="false" skin="neutral" type="transparent">
      Neutral
    </Badge>
    <Badge uppercase="false"  skin="warning" type="transparent">
      Warning
    </Badge>
    <Badge uppercase="false"  skin="urgent" type="transparent">
      Urgent
    </Badge>
    <Badge uppercase="false"  skin="premium" type="transparent">
      Premium
    </Badge>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Letter case
- description: <p>Decide whether a badge is written in all uppercase letters  or in sentence case with the <code>uppercase</code> prop.</p><p></p><p>By default, badges are written in lowercase.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <Badge>Upper case</Badge>
    <Badge uppercase={false}>Lower case</Badge>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;

```

### Affix
- description: <p>Add more context to a badge with affix icons: </p><li><code>prefixIcon</code> - used to emphasize status message.</li><li><code>suffixIcon</code> - used to emphasize statuses that trigger popovers.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column">
    <Badge uppercase="false"  prefixIcon={<Icons.LockLockedSmall />}>Prefix icon</Badge>
    <Badge uppercase="false" suffixIcon={<Icons.ChevronDownSmall />}>Suffix icon</Badge>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;

```




    


## Common Use Case Examples


### Item status
- description: <p>Use badges to communicate item status. Highlight items that require user attention. </p>
- example: 
```jsx 
() => {
  const records = [
    {
      number: '#1439',
      total: '$105.55',
      status: (
        <Badge size="small" skin="neutralLight">
          Paid
        </Badge>
      ),
    },
    {
      number: '#4152',
      total: '$928.41',
      status: (
        <Badge size="small" skin="neutralLight">
          Paid
        </Badge>
      ),
    },
    {
      number: '#9261',
      total: '$710.68',
      status: (
        <Badge size="small" skin="neutralLight">
          Paid
        </Badge>
      ),
    },
    {
      number: '#9359',
      total: '$219.78',
      status: (
        <Badge size="small" skin="danger">
          Overdue
        </Badge>
      ),
    },
    {
      number: '#5560',
      total: '$782.01',
      status: (
        <Badge size="small" skin="urgent">
          Partially paid
        </Badge>
      ),
    },
    {
      number: '#6690',
      total: '$406.27',
      status: (
        <Badge size="small" skin="neutralLight">
          Paid
        </Badge>
      ),
    },
    {
      number: '#5948',
      total: '$475.22',
      status: (
        <Badge size="small" skin="success">
          Sent
        </Badge>
      ),
    },
  ];

  const secondaryAction = [
    {
      icon: <Icons.DuplicateSmall />,
      text: 'Duplicate',
      onClick: () => {},
    },
    {
      icon: <Icons.DeleteSmall />,
      text: 'Delete',
      onClick: () => {},
    },
  ];

  const columns = [
    {
      title: 'Number',
      render: row => row.number,
      width: '30%',
    },
    {
      title: 'Total',
      render: row => row.total,
      width: '30%',
      align: 'start',
    },
    {
      title: 'Status',
      render: row => row.status,
      width: '30%',
      align: 'start',
    },
    {
      render: row => (
        <TableActionCell size="small" secondaryActions={secondaryAction} />
      ),
      width: '10%',
    },
  ];

  return (
    <Card>
      <Table data={records} columns={columns} showSelection>
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <TableToolbar.Label>7 invoices</TableToolbar.Label>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};
```

### Promote
- description: <p>Use badges to draw more attention to new or recommended features and tools.</p>
- example: 
```jsx 
<Card>
  <MarketingLayout
    title="Get listed on Google Search"
    description="Continue with your SEO setup checklist and connect to Google Search Console."
    actions={<Button size="small">Go for It</Button>}
    size="tiny"
    badge={<Badge size="small">Recommended</Badge>}
    image={
      <Box width="100%" align="right">
        <Image
          width="120px"
          src="PromotionalPromoteMarketingHomeSEO.svg"
          transparent
        />
      </Box>
    }
  />
</Card>;
```


