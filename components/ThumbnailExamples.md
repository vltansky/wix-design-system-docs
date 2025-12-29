
## Feature Examples


### Structure
- description: <p>Component consist of 3 optional content areas:</p><li><code>image</code></li><li><code>title</code></li><li><code>description</code></li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Thumbnail
    image={<Image />}
    title={
      <StorybookComponents.Placeholder>Title</StorybookComponents.Placeholder>
    }
    description={
      <StorybookComponents.Placeholder>
        Description
      </StorybookComponents.Placeholder>
    }
  />
</StorybookComponents.Stack>;
```

### Size
- description: <p>Adjust the component size using <code>size</code> prop. It supports 3 sizes:</p><li><code>medium</code> (default) - use in all common cases.</li><li><code>small</code> - use in more dense and narrow layouts.</li><li><code>tiny</code> - use in more dense and narrow layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Thumbnail size="medium" title="Medium" description="Size" />
  <Thumbnail size="small" title="Small" description="Size" />
  <Thumbnail size="tiny" title="Tiny" description="Size" />
</StorybookComponents.Stack>;
```

### Dimensions
- description: <p>Set thumbnail dimensions in pixels or percentage with <code>height</code> and <code>width</code> properties.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Thumbnail title="Title" width="50%" height="120px" />
  <Thumbnail title="Title" width="25%" height="60px" />
</StorybookComponents.Stack>;
```

### Content alignment
- description: <p>Control vertical alignment of thumbnail content with <code>contentAlignment</code> prop. It supports 2 options:</p><li><code>center</code> (default) - use in all common cases.</li><li><code>top</code> - use when thumbnail list contain items with different content lengths.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Thumbnail
    title="Center"
    description="Alignment"
    image={<Image width="90px" />}
    height={240}
    contentAlignment="center"
    width={165}
  />
  <Thumbnail
    title="Top"
    description="Alignment"
    image={<Image width="90px" />}
    height={240}
    contentAlignment="top"
    width={165}
  />
</StorybookComponents.Stack>;
```

### Text position
- description: <p>Control thumbnail text position with <code>textPosition</code> prop. Choose between:</p><li><code>inside</code> (default) - use for text only thumbnails or thumbnails that require more emphasis.</li><li><code>outside</code> - use for side panel thumbnails or large group of illustrated thumbnails.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Thumbnail
    title="Inside"
    description="Description"
    image={<Image />}
    contentAlignment="top"
    width={165}
    height={200}
  />
    <Thumbnail
    title="Outside"
    description="Alignment"
    image={<Image height="100%"/>}
    contentAlignment="top"
    textPosition="outside"
    width={165}
    height={200}
  />
</StorybookComponents.Stack>;
```

### Background image
- description: <p>Render image as a background of a thumbnail with <code>backgroundImage</code> prop.</p><p></p><p>Use it for gallery type selections, such as product cover image selection.</p>
- example: 
```jsx 
<Thumbnail
  backgroundImage="example.jpg"
  width={240}
  height={240}
  title="Title"
/>;
```

### States
- description: <p>Control the state of a component with:</p><li><code>selected</code> - use it to mark active selection.</li><li><code>disabled</code> - use it to mark item that cannot be selected or deselected.</li><p></p><p>Remove selected item checkmark icon with <code>hideSelectedIcon</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack gap="12px">
  <Thumbnail title="Default" width={140} />
  <Thumbnail title="Selected" selected width={140} />
  <Thumbnail title="Disabled" disabled width={140} />
  <Thumbnail
    title="Disabled with image"
    disabled
    image={<Image />}
    width={140}
  />
  <Thumbnail
    title="Disabled with image background"
    disabled
    backgroundImage="example.jpg"
    height={120}
    width={140}
  />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Show the status message inline, directly below the thumbnails by wrapping it in a <code><FormField/></code> and adding <code>statusMessage</code>.</p><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<FormField status="error" statusMessage="This is an error message.">
  <StorybookComponents.Stack gap="12px">
    <Thumbnail title="Option 1" width={140} />
    <Thumbnail title="Option 2" width={140} />
    <Thumbnail title="Option 3" width={140} />
  </StorybookComponents.Stack>
</FormField>;
```

### Custom content
- description: <p>Render any component or set of them as a child item to the thumbnail content area.</p><p></p><p>When passed, a title will be displayed below the thumbnail.</p>
- example: 
```jsx 
<Thumbnail title="Title" width="50%">
  <StorybookComponents.Stack padding="24px">
    <StorybookComponents.Placeholder>Content</StorybookComponents.Placeholder>
  </StorybookComponents.Stack>
</Thumbnail>;
```




    


## Common Use Case Examples


### List of options
- description: Use a thumbnail to list down a larger list of options using icons as visual clues.
- example: 
```jsx 

() => {
  const [selected, setSelected] = React.useState(0);

  const renderCell = ({ id, title, src }) => (
    <Cell span={2}>
      <Thumbnail
        size="small"
        title={<Text>{title}</Text>}
        selected={selected === id}
        onClick={() => setSelected(id)}
      >
        <Proportion>
          <Box height="100%" width="100%" align="center" verticalAlign="middle">
            <Image src={src} height="24px" width="24px" transparent />
          </Box>
        </Proportion>
      </Thumbnail>
    </Cell>
  );

  return (
    <Card>
      <Card.Header title="Add label to contact" />
      <Divider />
      <Card.Content>
        <Layout>
          <Cell span={12}>
            <Text>Decide how you want to respond to the trigger</Text>
          </Cell>
          {renderCell({
            id: 0,
            title: 'Send email to contacts',
            src: 'contacts.svg',
          })}
          {renderCell({
            id: 1,
            title: 'Send a chat message',
            src: 'chat_message.svg',
          })}
          {renderCell({
            id: 2,
            title: 'Get notified by email',
            src: 'email_notify.svg',
          })}
          {renderCell({
            id: 3,
            title: 'Create a task',
            src: 'task.svg',
          })}
        </Layout>
      </Card.Content>
    </Card>
  );
};

```

### Gallery selection
- description: <p>Use a thumbnail with <code>backgroundImage</code> to construct gallery type selections.</p>
- example: 
```jsx 
() => {
  const [selected, setSelected] = React.useState(0);

  return (
    <Layout cols={1}>
      <FormField label="Cover Image">
        <Box gap="12px">
          <Thumbnail
            backgroundImage="TravelExample1.jpg"
            width={64}
            height={64}
            selected={selected === 0}
            onClick={() => setSelected(0)}
          />
          <Thumbnail
            backgroundImage="TravelExample2.jpg"
            width={64}
            height={64}
            selected
            selected={selected === 1}
            onClick={() => setSelected(1)}
          />
          <Thumbnail
            backgroundImage="TravelExample3.jpg"
            width={64}
            height={64}
            selected={selected === 2}
            onClick={() => setSelected(2)}
          />
          <Thumbnail
            backgroundImage="TravelExample4.jpg"
            width={64}
            height={64}
            selected={selected === 3}
            onClick={() => setSelected(3)}
          />
          <Thumbnail
            backgroundImage="TravelExample5.jpg"
            width={64}
            height={64}
            selected={selected === 4}
            onClick={() => setSelected(4)}
          />
        </Box>
      </FormField>
    </Layout>
  );
};
```

### Custom content
- description: <p>Render custom content inside of a thumbnail to provide more details about the selection option.</p><p></p><p>In example, add graphics, images or custom actions such as links to read more. </p>
- example: 
```jsx 

() => {
  const [selected, setSelected] = React.useState(0);

  const renderThumbnail = ({ title, subtitle, id }) => (
    <Thumbnail selected={selected === id} onClick={() => setSelected(id)}>
      <Box padding="18px">
        <Box gap="12px" verticalAlign="middle">
          <Icons.Public />
          <Box direction="vertical">
            <Text size="medium" weight="bold">
              {title}
            </Text>
            <Box>
              <Text size="small" secondary>
                {subtitle}
              </Text>
            </Box>
          </Box>
        </Box>
      </Box>
    </Thumbnail>
  );

  return (
    <Card>
      <Card.Header title="Group info" />
      <Card.Divider />
      <Card.Content>
        <Layout cols={12}>
          <Cell span={8}>
            <Layout cols={1}>
              <FormField label="Name">
                <Input placeholder="Enter group name" />
              </FormField>
              <FormField
                label="Privacy"
                infoContent="Choose who can see and join this group"
              >
                <Layout cols={1} gap="12px">
                  {renderThumbnail({
                    title: 'Public',
                    subtitle: 'Anyone can view this group',
                    id: 0,
                  })}
                  {renderThumbnail({
                    title: 'Private',
                    subtitle: 'Only approved members can view this group',
                    id: 1,
                  })}
                  {renderThumbnail({
                    title: 'Hidden',
                    subtitle: 'Group is hidden and requires an invite to join',
                    id: 2,
                  })}
                </Layout>
              </FormField>
            </Layout>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};

```

### In settings panel
- description: <p>Use thumbnails with illustrations  to visually clarify the result of the selection the user makes.</p>
- example: 
```jsx 
() => {
  const [selectedDirection, setSelectedDirection] = React.useState(0);
  const [selectedAlignment, setSelectedAlignment] = React.useState(1);

  return (
    <SidePanel onCloseButtonClick={() => {}} skin="floating" width="288px">
      <SidePanel.Header title="Text Input Layout" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FieldSet
            legend="Direction"
            direction="horizontal"
            columns="auto auto"
          >
            <Thumbnail
              size="tiny"
              selected={selectedDirection === 0}
              onClick={() => setSelectedDirection(0)}
              hideSelectedIcon
              height={54}
              noPadding
              image={
                <Image
                  src="ThumbnailIllustration_LTR.svg"
                  transparent
                  fit="none"
                />
              }
              noPadding
              title="Left to right"
              textPosition="outside"
            />
            <Thumbnail
              size="tiny"
              selected={selectedDirection === 1}
              onClick={() => setSelectedDirection(1)}
              hideSelectedIcon
              height={54}
              noPadding
              image={
                <Image
                  src="ThumbnailIllustration_RTL.svg"
                  transparent
                  fit="none"
                />
              }
              noPadding
              title="Right to left"
              textPosition="outside"
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            legend="Alignment"
            direction="horizontal"
            columns="38px 38px 38px"
          >
            <Thumbnail
              size="tiny"
              selected={selectedAlignment === 0}
              onClick={() => setSelectedAlignment(0)}
              hideSelectedIcon
              height={38}
              noPadding
              image={
                <Image
                  src="ThumbnailIllustration_AlignLeft.svg"
                  transparent
                  fit="none"
                />
              }
              noPadding
              textPosition="outside"
            />
            <Thumbnail
              size="tiny"
              selected={selectedAlignment === 1}
              onClick={() => setSelectedAlignment(1)}
              hideSelectedIcon
              height={38}
              noPadding
              image={
                <Image
                  src="ThumbnailIllustration_AlignCenter.svg"
                  transparent
                  fit="none"
                />
              }
              noPadding
              textPosition="outside"
            />
            <Thumbnail
              size="tiny"
              selected={selectedAlignment === 2}
              onClick={() => setSelectedAlignment(2)}
              hideSelectedIcon
              height={38}
              noPadding
              image={
                <Image
                  src="ThumbnailIllustration_AlignRight.svg"
                  transparent
                  fit="none"
                />
              }
              noPadding
              textPosition="outside"
            />
          </FieldSet>
        </SidePanel.Field>
      </SidePanel.Content>
    </SidePanel>
  );
};
```


