
## Feature Examples


### Structure
- description: <p>Render any kind of content inside of a box. Boxes must include at least one element, and can wrap multiple child elements.</p>
- example: 
```jsx 
<Box>
  <StorybookComponents.Placeholder>Content</StorybookComponents.Placeholder>
</Box>;
```

### Dimensions
- description: <p>Control the component size by setting its <code>width</code> and <code>height</code> in pixels or percentage. The box container size will automatically equal the size of content added inside if these values are not specified.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box width="100%" height="100px">
    <StorybookComponents.Placeholder>
      Width 100%, Height 100px
    </StorybookComponents.Placeholder>
  </Box>
  <Box width="50%" height="50px">
    <StorybookComponents.Placeholder>
      Width 50%, Height 50px
    </StorybookComponents.Placeholder>
  </Box>
</StorybookComponents.Stack>;
```

### Direction
- description: <p>Control the <code>direction</code> in which child elements will be listed inside a box. There are 2 types of directions supported:</p><li><code>horizontal</code> lists items in a single row.</li><li><code>vertical</code> lists items in a single column. This layout will automatically extend each item to the full width of the box.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box direction="horizontal">
    <StorybookComponents.Placeholder>
      Horizontal
    </StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>
      Horizontal
    </StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>
      Horizontal
    </StorybookComponents.Placeholder>
  </Box>
  <Box direction="vertical">
    <StorybookComponents.Placeholder>Vertical</StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>Vertical</StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>Vertical</StorybookComponents.Placeholder>
  </Box>
</StorybookComponents.Stack>;
```

### Gap
- description: <p>Control the space between elements contained inside a box with <code>gap</code> prop. WSR spacing tokens and values are shown in pixels.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Box gap="SP1">
    <StorybookComponents.Placeholder>6px gap</StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>6px gap</StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>6px gap</StorybookComponents.Placeholder>
  </Box>
  <Box gap="48px">
    <StorybookComponents.Placeholder>48px gap</StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>48px gap</StorybookComponents.Placeholder>
    <StorybookComponents.Placeholder>48px gap</StorybookComponents.Placeholder>
  </Box>
</StorybookComponents.Stack>;
```

### Horizontal alignment
- description: <p>Align child elements of an X-axis inside a box with <code>align</code> prop as follows:</p><li><code>left</code></li><li><code>center</code></li><li><code>right</code></li><li><code>space-between</code>distributes child items evenly.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Placeholder>
    <Box align="left">Left</Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder>
    <Box align="center">Center</Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder>
    <Box align="right">Right</Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder>
    <Box align="space-between">
      <Box>Space</Box>
      <Box>Between</Box>
    </Box>
  </StorybookComponents.Placeholder>
</StorybookComponents.Stack>;
```

### Vertical alignment
- description: <p>Align child elements of a Y-axis inside a box with <code>verticalAlign</code> prop as follows:</p><li><code>top</code></li><li><code>middle</code></li><li><code>bottom</code></li><li><code>space-between</code> distributes child items evenly.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Placeholder height="50px">
    <Box verticalAlign="top" height="100%">
      Top
    </Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder height="50px">
    <Box verticalAlign="middle" height="100%">
      Middle
    </Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder height="50px">
    <Box verticalAlign="bottom" height="100%">
      Bottom
    </Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder height="50px">
    <Box verticalAlign="space-between" direction="vertical" height="100%">
      <Box>Space</Box>
      <Box>Between</Box>
    </Box>
  </StorybookComponents.Placeholder>
</StorybookComponents.Stack>;
```

### Padding
- description: <p>Control the amount of white space around child elements inside a box. Padding can be defined by:</p><li><code>padding</code> which defines the amount of white space from all sides.</li><li><code>paddingTop</code>, <code>paddingRight</code>, <code>paddingBottom</code>, and<code>paddingLeft</code> which define the amount of white space from a specific side only.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Placeholder>
    <Box padding="SP4">Equal padding</Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder>
    <Box
      paddingTop="SP2"
      paddingRight="SP10"
      paddingBottom="SP2"
      paddingLeft="SP10"
    >
      Different side paddings
    </Box>
  </StorybookComponents.Placeholder>
  <StorybookComponents.Placeholder>
    <Box>No padding</Box>
  </StorybookComponents.Placeholder>
</StorybookComponents.Stack>;
```

### Margin
- description: <p>Control the amount of white space around the box component itself with different properties. </p><li>Define the amount of space from all sides with <code>margin</code>.</li><li>Define the amount of space for a specific side only with <code>marginTop</code>, <code>marginRight</code>, <code>marginBottom</code> or <code>marginLeft</code> .</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Box height="18px" width="100%">
    <StorybookComponents.Placeholder>No margin</StorybookComponents.Placeholder>
  </Box>
  <Box height="18px" width="100%" margin="SP6 SP2">
    <StorybookComponents.Placeholder>
      With margin
    </StorybookComponents.Placeholder>
  </Box>
</StorybookComponents.Stack>;
```

### Color
- description: <p>Control the background and text color of a component with:</p><li><code>backgroundColor</code> to specify the background fill color.</li><li><code>color</code> to specify the text color.</li><p></p><p>Properties include WSR color variables and natively supported values, such as HEX, RGB, etc.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Box padding="SP4" margin="SP2" backgroundColor="D80" color="D10">
    Dark text
  </Box>
  <Box padding="SP4" margin="SP2" backgroundColor="D10" color="D80">
    Light text
  </Box>
  <Box padding="SP4" margin="SP2" backgroundColor="B10" color="D80">
    Light text
  </Box>
  <Box padding="SP4" margin="SP2" backgroundColor="G10" color="D80">
    Light text
  </Box>
  <Box padding="SP4" margin="SP2" backgroundColor="Y10" color="D10">
    Dark text
  </Box>
</StorybookComponents.Stack>;
```

### Border
- description: <p>Control the style of a border with the following properties:</p><li><code>border</code> enables a border and sets its width and style. This prop does not include WSR color variable keys.</li><li><code>borderColor</code> specifies the border color.</li><li><code>borderTopColor</code>, <code>borderRightColor</code>, <code>borderBottomColor</code>, <code>borderLeftColor</code> specifies the border color per edge.</li><li><code>borderRadius</code> specifies the corner radius.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <Box
    padding="SP6"
    margin="SP1"
    border="1px solid"
    borderColor="D50"
    borderRadius={0}
  ></Box>
  <Box
    padding="SP6"
    margin="SP1"
    border="2px dotted"
    borderColor="D40"
    borderRadius={6}
  ></Box>
  <Box
    padding="SP6"
    margin="SP1"
    border="3px dashed"
    borderColor="D30"
    borderRadius={12}
  ></Box>
  <Box
    padding="SP6"
    margin="SP1"
    border="6px solid"
    borderColor="D20"
    borderRadius={72}
  ></Box>
</StorybookComponents.Stack>;
```

### Inline
- description: <p>Define how a box behaves as an inline element when placed next to other components.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text>
    This is a sentence with an action at the end of it.
    <Box>
      <TextButton>Add link</TextButton>
    </Box>
  </Text>
  <Text>
    This is a sentence with an action at the end of it.
    <Box inline>
      <TextButton>Add link</TextButton>
    </Box>
  </Text>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Content arrangement
- description: <p>Use a box to arrange elements inside of other components in a desired way.</p>
- example: 
```jsx 
() => {
  const options = [
    {
      value: (
        <Box verticalAlign="middle">
          <Image width="48px" height="48px" />
          <Box marginLeft="SP3" direction="vertical">
            <Heading size="small">Structured data</Heading>
            <Text size="small" secondary>
              Make your product eligible for rich results in search engines.
            </Text>
          </Box>
        </Box>
      ),
      width: '80%',
    },
    {
      value: (
        <IconButton skin="inverted">
          <Icons.ChevronDown />
        </IconButton>
      ),
      align: 'right',
    },
  ];

  return <TableListItem options={options} />;
};
```

### List item
- description: <p>A combination of boxes can be used to construct custom widgets and list items.</p>
- example: 
```jsx 
() => (
  <Box height={160}>
    <Box align="center" verticalAlign="middle" width={180}>
      <Image
        height="180px"
        borderRadius="8px 0px 0px 8px"
        src="running_man.png"
      />
    </Box>
    <Box
      direction="vertical"
      borderRadius="0px 8px 8px 0px"
      verticalAlign="space-between"
      padding="18px 24px"
      backgroundColor="D80"
      flexGrow={1}
    >
      <Box verticalAlign="space-between" flexGrow={1}>
        <Box direction="vertical" gap="3px">
          <Heading size="small">Get running!</Heading>
          <Text size="small" secondary>
            Scheduled for April 26, 2021
          </Text>
        </Box>
      </Box>
      <Box align="space-between">
        <Box gap="24px">
          <Box verticalAlign="middle" gap="0px">
            <Icons.LockUnlockedSmall />
            <Box marginLeft={1}>
              <Text size="small">Public</Text>
            </Box>
          </Box>
          <Box verticalAlign="middle">
            <Box marginLeft={1}>
              <Text size="small">Join for Free</Text>
            </Box>
          </Box>
        </Box>
        <Box>
          <Box verticalAlign="middle">
            <Box gap="SP2">
              <IconButton priority="secondary" size="small">
                <Icons.MoreSmall />
              </IconButton>
              <Button priority="secondary" size="small">
                Edit
              </Button>
            </Box>
          </Box>
        </Box>
      </Box>
    </Box>
  </Box>
);
```


