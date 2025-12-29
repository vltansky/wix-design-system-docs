
## Feature Examples


### Shape
- description: <p>Use shape prop to change the shape of the composer button.</p><li><code>Square</code> is the default shape</li><li><code>Round</code> </li>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="flex-start">
<ComposerButton shape="square"><Icons.Badge /></ComposerButton>
  <ComposerButton shape ="round"><Icons.Badge /></ComposerButton>
</StorybookComponents.Stack>;
```

### Color
- description: <p>Use color prop to change button color, you can choose one of these:</p><li><code>standard</code></li><li><code>blue</code></li><li><code>cyan</code></li><li><code>purple</code></li><li><code>pink</code></li><li><code>orange</code></li><li><code>red</code></li><li><code>green</code></li><p></p>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="flex-start">
  <ComposerButton color="standard"><Icons.Badge /></ComposerButton>
  <ComposerButton color="blue"><Icons.Badge /></ComposerButton>
  <ComposerButton color="cyan"><Icons.Badge /></ComposerButton>
  <ComposerButton color="purple"><Icons.Badge /></ComposerButton>
  <ComposerButton color="pink"><Icons.Badge /></ComposerButton>
  <ComposerButton color="orange"><Icons.Badge /></ComposerButton>
  <ComposerButton color="red"><Icons.Badge /></ComposerButton>
  <ComposerButton color="green"><Icons.Badge /></ComposerButton>

</StorybookComponents.Stack>
```

### Ellipsis
- description: <p>Use <code>ellipsis</code> prop to get truncated label when it reached max width.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="150px">
  <ComposerButton label="Add a badge to your profile">
    <Icons.Badge />
  </ComposerButton>
  <ComposerButton ellipsis={false} label="Add a badge to your profile">
    <Icons.Badge />
  </ComposerButton>
</StorybookComponents.Stack>;

```

### Max lines
- description: <p>Use <code>maxLines</code> prop to limit the number of lines the button label has before getting truncated.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="150px">
  <ComposerButton label="Add a badge to your profile">
    <Icons.Badge />
  </ComposerButton>
  <ComposerButton maxLines="2" label="Add a badge to your profile">
    <Icons.Badge />
  </ComposerButton>
</StorybookComponents.Stack>;

```

### Disabled
- description: <p>To disable a composer button, use the <code>disabled</code> prop which indicates a button can't be selected.</p>
- example: 
```jsx 
<ComposerButton disabled><Icons.Badge /></ComposerButton>
```




    


## Common Use Case Examples


### Composer add panel
- description: <p>Add form fields</p>
- example: 
```jsx 
<SidePanel width="300px">
  <SidePanel.Header title="Add form fields"></SidePanel.Header>
  <SidePanel.Content noPadding>
    <Box padding="SP3" direction="vertical">
      <SectionHeader
        skin="light"
        size="small"
        horizontalPadding
        divider
        title="Contact fields"
      ></SectionHeader>
      <Box padding="SP1">
        <Layout justifyItems="center" cols="3">
          <Cell span="1">
            <ComposerButton color="blue" label="First Name">
              <Icons.UserName />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="blue" label="Last Name">
              <Icons.UserName />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="blue" label="Email">
              <Icons.Email />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="blue" label="Phone">
              <Icons.Phone />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="blue" label="Birthday">
              <Icons.Date />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="blue" label="Address">
              <Icons.Location />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="blue" label="Subscribe">
              <Icons.StatusComplete />
            </ComposerButton>
          </Cell>
        </Layout>
      </Box>
    </Box>
    <Divider />
    <Box padding="SP3" direction="vertical">
      <SectionHeader
        skin="light"
        size="small"
        horizontalPadding
        divider
        title="Buttons"
      ></SectionHeader>
      <Box padding="SP1">
        <Layout justifyItems="center" cols="3">
          <Cell span="1">
            <ComposerButton color="purple" label="Submit">
              <Icons.Button />
            </ComposerButton>
          </Cell>
        </Layout>
      </Box>
    </Box>
    <Divider />
    <Box padding="SP3" direction="vertical">
      <SectionHeader
        skin="light"
        size="small"
        horizontalPadding
        divider
        title="General fields"
      ></SectionHeader>
      <Box padding="SP1">
        <Layout justifyItems="center" cols="3">
          <Cell span="1">
            <ComposerButton color="cyan" label="Short answer">
              <Icons.Input />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="cyan" label="Long answer">
              <Icons.InputArea />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="cyan" label="Number">
              <Icons.Number />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="cyan" label="Link">
              <Icons.Link />
            </ComposerButton>
          </Cell>
          <Cell span="1">
            <ComposerButton color="cyan" label="File upload">
              <Icons.Upload />
            </ComposerButton>
          </Cell>
                    <Cell span="1">
            <ComposerButton color="cyan" label="Signature">
              <Icons.ESignature />
            </ComposerButton>
          </Cell>
        </Layout>
      </Box>
    </Box>
  </SidePanel.Content>
</SidePanel>;

```


