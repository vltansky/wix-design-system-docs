
## Feature Examples


### Shape
- description: Control the form of the avatar with a shape prop. It supports 2 shapes:<br/>
        &emsp;- `circle` (default) -  use it to represent a user.<br/>
        &emsp;- `square` - use it to represent an entity such as a company or organization.<br/>
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar shape="circle" />
  <Avatar shape="square" />
</StorybookComponents.Stack>;

```

### Content states
- description: Component has 3 states:<br/>
        &emsp;- Loads image when image URL is provided.<br/>
        &emsp;- Falls back to the placeholder when provided image URL is broken or not given.<br/>
        &emsp;- Display initials when image URL is broken or not given, but avatar name is defined.
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar imgProps={{ src: 'AvatarExample4.jpg' }} />
  <Avatar imgProps={{ src: 'NotFoundImage.jpg' }} />
  <Avatar name="Anne Rikki" imgProps={{ src: 'NotFoundImage.jpg' }} />
</StorybookComponents.Stack>;

```

### Size
- description: Adjust the avatar size using size prop. It supports 8 sizes:<br/>
        &emsp;- `size90`<br/>
        &emsp;- `size72`<br/>
        &emsp;- `size60`<br/>
        &emsp;- `size48` (default)<br/>
        &emsp;- `size36`<br/>
        &emsp;- `size30`<br/>
        &emsp;- `size24`<br/>
        &emsp;- `size18`<br/>
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar size="size90" name="Anne Rikki" />
  <Avatar size="size72" name="Anne Rikki" />
  <Avatar size="size60" name="Anne Rikki" />
  <Avatar size="size48" name="Anne Rikki" />
  <Avatar size="size36" name="Anne Rikki" />
  <Avatar size="size30" name="Anne Rikki" />
  <Avatar size="size24" name="Anne Rikki" />
  <Avatar size="size18" name="Anne Rikki" />
</StorybookComponents.Stack>;

```

### Color
- description: <p>Control avatar color with color prop. It supports 6 colors:</p><li> <code>A1</code> blue</li><li> <code>A2</code>  arctic blue</li><li> <code>A3</code> purple</li><li> <code>A4</code> green</li><li> <code>A5</code> magenta</li><li> <code>A6</code> yellow</li>
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar color="A1" name="A 1" />
  <Avatar color="A2" name="A 2" />
  <Avatar color="A3" name="A 3" />
  <Avatar color="A4" name="A 4" />
  <Avatar color="A5" name="A 5" />
  <Avatar color="A6" name="A 6" />
</StorybookComponents.Stack>;

```

### Presence
- description: Use the presence prop to indicate the status of a user. It supports 3 statuses:<br/>
        &emsp;- `online` - indicates that user is online.<br/>
        &emsp;- `offline` - indicates that user is not available.<br/>
        &emsp;- `busy` - indicates that user is online, but is busy, so might not be accessible.<br/>
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar presence="online" />
  <Avatar presence="offline" />
  <Avatar presence="busy" />
</StorybookComponents.Stack>;

```

### Placeholder
- description: Display a placeholder when component has no image and no name. 
        When required, override default placeholders to any custom elements by passing required content to `placeholder` prop.
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar />
  <Avatar shape="square" />
  <Avatar
    shape="square"
    placeholder={
      <Box color="B20">
        <Icons.Toolbox />
      </Box>
    }
  />
</StorybookComponents.Stack>;

```

### Indication
- description: Render any indicator via `customIndication` prop. It accepts any component or a set of them within a restricted dimensions:<br/>
        &emsp;- 30x30px container for avatar in `size90`, `size72`.<br/>
        &emsp;- 24x24px container for avatar in `size60`, `size48`.<br/>
        Smaller avatar sizes cannot have custom indicators.
- example: 
```jsx 

() => {
  const CustomIndication = () => (
    <Box
      backgroundColor="D80"
      borderRadius={24}
      color="#4267B2"
      width="max-content"
    >
      <Icons.Facebook />
    </Box>
  );

  return (
    <StorybookComponents.Stack>
      <Avatar
        name="Anne Rikki"
        size="size90"
        customIndication={<CustomIndication />}
      />
      <Avatar
        name="Anne Rikki"
        size="size72"
        customIndication={<CustomIndication />}
      />
      <Avatar
        name="Anne Rikki"
        size="size60"
        customIndication={<CustomIndication />}
      />
      <Avatar
        name="Anne Rikki"
        size="size48"
        customIndication={<CustomIndication />}
      />
    </StorybookComponents.Stack>
  );
};

```

### Action button
- description: Render related action such as image upload as an icon button with `indication` prop.
        This prop applies for 4 largest avatar sizes only: size90, size72, size60 and size48.
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar name="Anne Rikki" size="size90" indication={<Icons.PhotoCamera />} />
  <Avatar name="Anne Rikki" size="size72" indication={<Icons.PhotoCamera />} />
  <Avatar name="Anne Rikki" size="size60" indication={<Icons.PhotoCamera />} />
  <Avatar name="Anne Rikki" size="size48" indication={<Icons.PhotoCamera />} />
</StorybookComponents.Stack>;

```

### Show action on hover
- description: Reveal action button on avatar hover only with `showIndicationOnHover` prop.
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar
    name="Anne Rikki"
    size="size90"
    indication={<Icons.PhotoCamera />}
    showIndicationOnHover
  />
  <Avatar
    name="Anne Rikki"
    size="size72"
    indication={<Icons.PhotoCamera />}
    showIndicationOnHover
  />
  <Avatar
    name="Anne Rikki"
    size="size60"
    indication={<Icons.PhotoCamera />}
    showIndicationOnHover
  />
  <Avatar
    name="Anne Rikki"
    size="size48"
    indication={<Icons.PhotoCamera />}
    showIndicationOnHover
  />
</StorybookComponents.Stack>;

```

### Loader
- description: Render related action such as image upload as an icon button with `indication` prop.
        This prop applies for 4 largest avatar sizes only: size90, size72, size60 and size48.
- example: 
```jsx 

<StorybookComponents.Stack>
  <Avatar
    name="Anne Rikki"
    size="size90"
    indication={<Icons.PhotoCamera />}
    loading
  />
  <Avatar
    name="Anne Rikki"
    size="size72"
    indication={<Icons.PhotoCamera />}
    loading
  />
  <Avatar
    name="Anne Rikki"
    size="size60"
    indication={<Icons.PhotoCamera />}
    loading
  />
  <Avatar
    name="Anne Rikki"
    size="size48"
    indication={<Icons.PhotoCamera />}
    loading
  />
</StorybookComponents.Stack>;

```




    


## Common Use Case Examples


### Users list
- description: Use \<Avatar/> as a first data column in a table to visually represent your customers.
- example: 
```jsx 

() => {
  const records = [
    {
      image: <Avatar size="size36" name="Sara Porter" />,
      name: 'Sara Porter',
      country: 'Canada',
      orders: 2,
      lastActivity: 'Sep 9, 2020',
    },
    {
      image: <Avatar size="size36" name="Michael Baldwin" />,
      name: 'Michael Baldwin',
      country: 'Germany',
      orders: 43,
      lastActivity: 'Sep 7, 2020',
    },
    {
      image: <Avatar size="size36" name="Alex Halifax" />,
      name: 'Alex Halifax',
      country: 'United Kingdom',
      orders: 12,
      lastActivity: 'Jun 30, 2020',
    },
    {
      image: <Avatar size="size36" name="Paul Sheffield" />,
      name: 'Paul Sheffield',
      country: 'US',
      orders: 0,
      lastActivity: 'Sep 18, 2019',
    },
  ];

  const columns = [
    { title: '', width: '36px', render: row => row.image },
    { title: 'Name', render: row => row.name },
    { title: 'Country', render: row => row.country },
    { title: 'Orders', render: row => row.orders },
    { title: 'Last Activity', render: row => row.lastActivity },
    {
      render: () => (
        <TableActionCell
          primaryAction={{
            text: 'Edit',
            onClick: () => {},
          }}
        />
      ),
    },
  ];

  return (
    <Card>
      <Table data={records} columns={columns}>
        <TableToolbar>
          <TableToolbar.Title>Customers</TableToolbar.Title>
        </TableToolbar>
        <Table.Content />
      </Table>
    </Card>
  );
};

```

### Prefix
- description: Use \<Avatar/> as a prefix item to build user selections.
- example: 
```jsx 

<Dropdown
  placeholder="Select staff member"
  valueParser={option => option.value({ selected: option.id }).props.title}
  fixedFooter={<ListItemAction title="Add New Staff Member" />}
  options={[
    listItemSelectBuilder({
      id: 0,
      prefix: <Avatar size="size24" color="A1" name="Carmel Lloyd" />,
      title: 'Carmel Lloyd',
    }),
    listItemSelectBuilder({
      id: 1,
      prefix: <Avatar size="size24" color="A2" name="Gracie-May Marsden" />,
      title: 'Gracie-May Marsden',
    }),
    listItemSelectBuilder({
      id: 2,
      prefix: <Avatar size="size24" color="A3" name="Keisha Decker" />,
      title: 'Keisha Decker',
    }),
    listItemSelectBuilder({
      id: 3,
      prefix: <Avatar size="size24" color="A4" name="Ruairidh Fitzgerald" />,
      title: 'Ruairidh Fitzgerald',
    }),
    listItemSelectBuilder({
      id: 4,
      prefix: <Avatar size="size24" color="A5" name="Sheldon Chavez" />,
      title: 'Sheldon Chavez',
    }),
  ]}
/>;

```

### Upload photo
- description: Use an `indication` prop to display a button allowing users to manually upload a photo to avatar
- example: 
```jsx 

<Card>
  <Card.Content>
    <Layout gap="18px">
      <Cell>
        <Box verticalAlign="middle" align="space-between">
          <Box verticalAlign="middle">
            <FileUpload>
              {({ openFileUploadDialog }) => (
                <Avatar
                  name="Anne Rikki"
                  size="size60"
                  onIndicationClick={openFileUploadDialog}
                  indication={<Icons.PhotoCamera size="24" />}
                />
              )}
            </FileUpload>
            <Box direction="vertical" padding="0 24px">
              <Heading size="large">Anne Rikki</Heading>
              <TextButton weight="normal" size="small">
                Edit Contact
              </TextButton>
            </Box>
          </Box>
          <Button>Send Message</Button>
        </Box>
      </Cell>
      <Cell>
        <Divider />
      </Cell>
      <Cell>
        <Box gap="60px">
          <Box direction="vertical">
            <Text size="tiny" secondary light>
              Email
            </Text>
            <Text size="small">anne.rikki@email.com</Text>
          </Box>
          <Box direction="vertical">
            <Text size="tiny" secondary light>
              Phone
            </Text>
            <Text size="small">+44 734 349973</Text>
          </Box>
          <Box direction="vertical">
            <Text size="tiny" secondary light>
              Billing Address
            </Text>
            <Text size="small">2549 Perine Street, Vermont</Text>
          </Box>
        </Box>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;


```


