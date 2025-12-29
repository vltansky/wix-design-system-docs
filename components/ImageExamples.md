
## Feature Examples


### Dimensions
- description: <p>Specify image dimensions in pixels or percentage with <code>width</code> and <code>height</code> props.</p>
- example: 
```jsx 
<Image width="33%" height="180px" />;
```

### Border
- description: <p>To separate images from backgrounds, enable the image border<code>showBorder</code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="25%">
  <Image showBorder />
</StorybookComponents.Stack>;
```

### Border radius
- description: <p>Control the rounded corners of the image box with the <code>borderRadius</code> prop. Radius levels can be specified for every corner.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Image />
  <Image borderRadius={'24px'} />
  <Image borderRadius={'36px 0px 0px 36px'} />
</StorybookComponents.Stack>;
```

### States
- description: <p>Use the <code>src</code> prop to display a link to a media file. If the <code>src</code> prop is added without a link, the default placeholder shows.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Image />
  <Image src="example.jpg" />
</StorybookComponents.Stack>;
```

### Background fill
- description: <p>To remove the background color for PNG images or vector graphics, use the <code>transparent</code> prop. </p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Image fit="contain" height="240" src="example.jpg" />
  <Image fit="contain" height="240" src="example.jpg" transparent />
  <Image fit="contain" src="PromotionalPromoteMarketingHomeEmail.svg" />
  <Image
    fit="contain"
    src="PromotionalPromoteMarketingHomeEmail.svg"
    transparent
  />
</StorybookComponents.Stack>;
```

### Fit mode
- description: <p>Control how images are displayed when their dimensions don't match the size of their containers with the <code>fit</code> prop. It supports all default <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit">object-fit</a> values, but there are four that are most commonly used:  </p><p></p><li><code>contain</code>  maintains the aspect ratio while fitting images within containers.</li><li><code>cover</code>  maintains the aspect ratio and clips images to fill containers.</li><li><code>none</code>  loads the original image size and positions it in the center of the container.</li><li><code>tile</code>  repeats images when their dimensions are smaller than the containers.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Image fit="contain" height="300" src="example.jpg" />
  <Image fit="cover" height="300" src="example.jpg" />
  <Image fit="none" height="300" src="example.jpg" />
</StorybookComponents.Stack>;
```

### Position
- description: <p>Control image placement inside of a bounding box with the <code>position</code> property.  Specify the starting position of the image from where its fit will be defined.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Image src="example.jpg" fit="none" position="top" />
  <Image src="example.jpg" fit="none" position="center left" />
  <Image src="example.jpg" fit="none" position="bottom right" />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Mixed border radius
- description: <p>Use images with mixed corner radius levels in cases when they touch the edges of cards.</p>
- example: 
```jsx 
() => {
  const renderImage = () => (
    <Image
      src="TravelExample7.jpg"
      borderRadius="15px 0px 0px 15px"
      height="200px"
      width="230px"
    />
  );

  const renderContent = () => (
    <Box
      direction="vertical"
      verticalAlign="space-between"
      padding="24px 29px 27px"
      backgroundColor="D80"
      flexGrow={1}
    >
      <Box direction="vertical">
        <Text weight="bold">Sunset</Text>
        <Text size="tiny" weight="thin" secondary>
          Jul 15, 2021 7:30pm, Cypher City
        </Text>
      </Box>
      <Box align="right" verticalAlign="middle" minWidth={115} gap="12px">
        <IconButton priority="secondary" size="small">
          <Icons.More />
        </IconButton>
        <Button priority="secondary" size="small">
          Edit
        </Button>
      </Box>
    </Box>
  );

  return (
    <Box minHeight={200}>
      {renderImage()}
      {renderContent()}
    </Box>
  );
};
```

### Product list
- description: <p>Use images to display product thumbnails in lists and widgets.</p>
- example: 
```jsx 
() => {
  const records = [
    {
      name: 'Hoodie',
      sku: 25232564,
      inStock: true,
      price: '$14.00',
      image: <Image src="ProductExample1.jpg" />,
    },
    {
      name: 'Watch',
      sku: 35246432,
      inStock: true,
      price: '$29.00',
      image: <Image src="ProductExample2.jpg" />,
    },
    {
      name: 'Glasses',
      sku: 4864310,
      inStock: false,
      price: '$69.00',
      image: <Image src="ProductExample3.jpg" />,
    },
    {
      name: 'Leather shoes',
      sku: 125156422,
      inStock: true,
      price: '$7.00',
      image: <Image src="ProductExample4.jpg" />,
    },
  ];

  const Status = ({ isInStock }) => (
    <Text size="small" secondary>
      {isInStock ? 'In Stock' : 'Out Of Stock'}
    </Text>
  );

  const secondaryAction = [
    {
      icon: <Icons.Duplicate />,
      text: 'Duplicate',
      onClick: () => {},
    },
    {
      icon: <Icons.Delete />,
      text: 'Delete',
      onClick: () => {},
    },
  ];

  const columns = [
    {
      title: '',
      render: row => row.image,
      width: '60px',
    },
    {
      title: 'Name',
      render: row => row.name,
      width: '30%',
    },
    {
      title: 'SKU',
      render: row => row.sku,
      width: '20%',
      align: 'start',
    },
    {
      title: 'Stock',
      render: row => <Status isInStock={row.inStock} />,
      width: '20%',
      align: 'start',
    },
    {
      title: 'Price',
      render: row => row.price,
      width: '10%',
      align: 'start',
    },
    {
      render: row => <TableActionCell secondaryActions={secondaryAction} />,
      width: '10%',
    },
  ];

  return (
    <Card>
      <Table data={records} columns={columns}>
        <TableToolbar>
          <TableToolbar.ItemGroup position="start">
            <TableToolbar.Item>
              <TableToolbar.Title>Products</TableToolbar.Title>
            </TableToolbar.Item>
          </TableToolbar.ItemGroup>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};
```


