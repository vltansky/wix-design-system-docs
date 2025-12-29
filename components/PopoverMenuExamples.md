
## Feature Examples


### Trigger element
- description: <p>Popover menus are opened by interacting with a trigger element. Common trigger elements are:</p><li><code><Button/></code><a href="https://www.wix-style-react.com/storybook/?path=/story/components-actions--button"></a></li><li><code><Text Button/></code></li><li><code><IconButton/></code></li>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="center">
  <PopoverMenu
    triggerElement={
      <Button priority="secondary" suffixIcon={<Icons.ChevronDown />}>
        More Actions
      </Button>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
  <PopoverMenu
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        More Actions
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
  <PopoverMenu
    triggerElement={
      <IconButton priority="secondary">
        <Icons.More />
      </IconButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```

### Trigger interaction
- description: <p>Popover menus are displayed when a trigger element is either clicked or hovered on.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <PopoverMenu
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>Click Here</TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
  <PopoverMenu
    triggerElement={({ toggle, open, close }) => (
      <TextButton
        onClick={toggle}
        onMouseEnter={open}
        onMouseLeave={close}
        suffixIcon={<Icons.ChevronDown />}
      >
        Hover Here
      </TextButton>
    )}
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```

### Size
- description: <p>The size of menu items can be controlled using the <code>textSize</code> prop. </p><p>There are two sizes to choose from:</p><li><code>medium</code> is the default used in common cases.</li><li><code>small</code> should be used in dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="center">
  <PopoverMenu
    textSize="medium"
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Medium Size
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Medium action 1" />
    <PopoverMenu.MenuItem text="Medium action 2" />
    <PopoverMenu.MenuItem text="Medium action 3" />
  </PopoverMenu>
  <PopoverMenu
    textSize="small"
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDownSmall />} size="small">
        View Small Size
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Small action 1" />
    <PopoverMenu.MenuItem text="Small action 2" />
    <PopoverMenu.MenuItem text="Small action 3" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>The appearance of each menu item can be controlled using the <code>skin</code> prop. </p><p>There are two skins to choose from:</p><li><code>dark</code> should be used for all common cases.</li><li><code>destructive</code> should be used to highlight destructive and permanent actions, e.g., deleting a contact.</li><p></p><p><em>Note</em>: Destructive actions should be placed last in the menu.</p>
- example: 
```jsx 
<PopoverMenu
  triggerElement={
    <TextButton suffixIcon={<Icons.ChevronDown />}>View Skins</TextButton>
  }
>
  <PopoverMenu.MenuItem skin="dark" text="Dark action" />
  <PopoverMenu.MenuItem skin="destructive" text="Destructive action" />
</PopoverMenu>;
```

### Disabled
- description: <p>Actions that are unavailable to users at that time should be marked with the <code>disabled</code> prop.</p>
- example: 
```jsx 
<PopoverMenu
  triggerElement={
    <TextButton suffixIcon={<Icons.ChevronDown />}>
      View Disabled State
    </TextButton>
  }
>
  <PopoverMenu.MenuItem text="Action 1" />
  <PopoverMenu.MenuItem text="Action 2" />
  <PopoverMenu.MenuItem text="Disabled action" disabled />
</PopoverMenu>;
```

### Prefix
- description: <p>Icons can be added to menu items using the <code>prefixIcon</code> prop. It can help users identify actions quicker.</p><p></p><p><em>Note</em>: <code>small</code> size popovers should use the small icon size, 18x18.</p>
- example: 
```jsx 
<StorybookComponents.Stack alignItems="center">
  <PopoverMenu
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>View Prefix</TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Add" prefixIcon={<Icons.Add />} />
    <PopoverMenu.MenuItem text="Edit" prefixIcon={<Icons.Edit />} />
    <PopoverMenu.MenuItem text="Delete" prefixIcon={<Icons.Delete />} />
  </PopoverMenu>
  <PopoverMenu
    textSize="small"
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDownSmall />} size="small">
        View Small Prefix
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Add" prefixIcon={<Icons.AddSmall />} />
    <PopoverMenu.MenuItem text="Edit" prefixIcon={<Icons.EditSmall />} />
    <PopoverMenu.MenuItem text="Delete" prefixIcon={<Icons.DeleteSmall />} />
  </PopoverMenu>
</StorybookComponents.Stack>;
```

### Subtitle
- description: <p>Add additional information that helps explain the purpose of a specific action using the <code>subtitle</code> prop.</p>
- example: 
```jsx 
<PopoverMenu
  triggerElement={
    <TextButton suffixIcon={<Icons.ChevronDown />}>View Subtitle</TextButton>
  }
>
  <PopoverMenu.MenuItem
    text="Action 1"
    subtitle="Subtitle that explains action 1"
  />
  <PopoverMenu.MenuItem
    text="Action 2"
    subtitle="Subtitle that explains action 2"
  />
  <PopoverMenu.MenuItem
    text="Action 3"
    subtitle="Subtitle that explains action 3"
  />
</PopoverMenu>;
```

### Divider
- description: <p>Menu items can be organized into groups by adding a <code><PopoverMenu.Divider/></code> between them.</p>
- example: 
```jsx 
<PopoverMenu
  triggerElement={
    <TextButton suffixIcon={<Icons.ChevronDown />}>View Divider</TextButton>
  }
>
  <PopoverMenu.MenuItem text="Action 1" />
  <PopoverMenu.MenuItem text="Action 2" />
  <PopoverMenu.MenuItem text="Action 3" />
  <PopoverMenu.Divider />
  <PopoverMenu.MenuItem text="Action 4" />
</PopoverMenu>;
```

### Placement
- description: <p>The placement of the menu in relation to the trigger element can be controlled using the <code>placement</code> prop. </p><p>There are four placement types to choose from:</p><li><code>top</code>, <code>top-start</code>, <code>top-end</code></li><li><code>right</code>, <code>right-start</code>, <code>right-end</code></li><li><code>bottom</code> (default), <code>bottom-start</code>, <code>bottom-end</code></li><li><code>left</code>, <code>left-start</code>, <code>left-end</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack justifyContent="center">
    <PopoverMenu
      placement="top"
      triggerElement={
        <TextButton suffixIcon={<Icons.ChevronDown />}>
          Top Placement
        </TextButton>
      }
    >
      <PopoverMenu.MenuItem text="Action 1" />
      <PopoverMenu.MenuItem text="Action 2" />
      <PopoverMenu.MenuItem text="Action 3" />
    </PopoverMenu>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack justifyContent="space-between">
    <PopoverMenu
      placement="left"
      triggerElement={
        <TextButton suffixIcon={<Icons.ChevronDown />}>
          Left Placement
        </TextButton>
      }
    >
      <PopoverMenu.MenuItem text="Action 1" />
      <PopoverMenu.MenuItem text="Action 2" />
      <PopoverMenu.MenuItem text="Action 3" />
    </PopoverMenu>
    <PopoverMenu
      placement="right"
      triggerElement={
        <TextButton suffixIcon={<Icons.ChevronDown />}>
          Right Placement
        </TextButton>
      }
    >
      <PopoverMenu.MenuItem text="Action 1" />
      <PopoverMenu.MenuItem text="Action 2" />
      <PopoverMenu.MenuItem text="Action 3" />
    </PopoverMenu>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack justifyContent="center">
    <PopoverMenu
      placement="bottom"
      triggerElement={
        <TextButton suffixIcon={<Icons.ChevronDown />}>
          Bottom Placement
        </TextButton>
      }
    >
      <PopoverMenu.MenuItem text="Action 1" />
      <PopoverMenu.MenuItem text="Action 2" />
      <PopoverMenu.MenuItem text="Action 3" />
    </PopoverMenu>
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Pointer arrow
- description: <p>By default, a pointer arrow is visible on the top edge of the menu, pointing to the trigger element. To remove the pointer, use the <code>showArrow</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <PopoverMenu
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View With Arrow
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
  <PopoverMenu
    showArrow={false}
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Without Arrow
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```

### Text overflow
- description: <p>Define what happens with menu item text when it exceeds the popover <code>maxWidth</code>.</p><p></p><p>By default, text wraps into multiple lines. To limit menu item text to a single line, use the <code>ellipsis</code> prop. The full title is revealed in a tooltip on mouse hover.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <PopoverMenu
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Wrapping Text
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Long action text here" />
    <PopoverMenu.MenuItem text="Long action text here" />
    <PopoverMenu.MenuItem text="Long action text here" />
  </PopoverMenu>
  <PopoverMenu
    ellipsis
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Text With Ellipsis
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Long action text here" />
    <PopoverMenu.MenuItem text="Long action text here" />
    <PopoverMenu.MenuItem text="Long action text here" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```

### Custom dimensions
- description: <p>Popover dimensions can be adjusted using the following props:</p><li><code>minWidth</code> - sets the minimum pixel width (default: 144 px).</li><li><code>maxWidth</code> - sets the maximum pixel width (default: 204 px).</li><li><code>maxHeight</code> - sets the maximum pixel height. When the list of actions exceeds it, a scrollbar is visible.</li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <PopoverMenu
    minWidth="240px"
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Min Width
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
  <PopoverMenu
    maxWidth="180px"
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Max Width
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Long action text here" />
    <PopoverMenu.MenuItem text="Long action text here" />
    <PopoverMenu.MenuItem text="Long action text here" />
  </PopoverMenu>
  <PopoverMenu
    maxHeight="180px"
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />}>
        View Max Height
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
    <PopoverMenu.MenuItem text="Action 4" />
    <PopoverMenu.MenuItem text="Action 5" />
    <PopoverMenu.MenuItem text="Action 6" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```




## Developer Examples


### Fluid
- description: <p>The trigger element can be resized to a specific container width using the <code>fluid</code> prop. Use it with <code>ellipsis</code> inside the trigger element to display the full label in a tooltip on hover.</p>
- example: 
```jsx 
<StorybookComponents.Stack width="150px">
  <PopoverMenu
    fluid
    triggerElement={
      <TextButton suffixIcon={<Icons.ChevronDown />} ellipsis>
        A very long trigger element title
      </TextButton>
    }
  >
    <PopoverMenu.MenuItem text="Action 1" />
    <PopoverMenu.MenuItem text="Action 2" />
    <PopoverMenu.MenuItem text="Action 3" />
  </PopoverMenu>
</StorybookComponents.Stack>;
```


    


## Common Use Case Examples


### Secondary actions in widgets
- description: <p>The small size popover menu should be used in dense layouts and widgets. Irreversible actions should be highlighted with a <code>destructive</code> skin.</p>
- example: 
```jsx 
<Layout>
  <Cell span={4}>
    <Card>
      <Card.Content>
        <Box direction="vertical" gap={4}>
          <Box direction="horizontal" justify-content="space-between">
            <Avatar />
            <PopoverMenu
              textSize="small"
              triggerElement={
                <IconButton priority="secondary" size="small">
                  <Icons.More />
                </IconButton>
              }
            >
              <PopoverMenu.MenuItem
                prefixIcon={<Icons.EditSmall />}
                text="Edit info"
              />
              <PopoverMenu.MenuItem
                prefixIcon={<Icons.DateAndTimeSmall />}
                text="Edit availability"
              />
              <PopoverMenu.MenuItem
                prefixIcon={<Icons.AdminAccessSmall />}
                text="Manage permissions"
              />
              <PopoverMenu.Divider />
              <PopoverMenu.MenuItem
                prefixIcon={<Icons.DeleteSmall />}
                skin="destructive"
                text="Delete"
              />
            </PopoverMenu>
          </Box>
          <Box direction="vertical">
            <Heading appearance="H4">Mike Peterson</Heading>
            <Text size="small" secondary>
              Sales associate
            </Text>
            <Box height="60px" />
          </Box>
        </Box>
      </Card.Content>
    </Card>
  </Cell>
</Layout>;
```

### Secondary page actions
- description: <p>Popover menus can be used to display a list of secondary page actions.</p><p>Use <code><PopoverMenu.Divider/></code> to organize actions into groups.</p><p></p><p>To make sure action titles will not wrap to multiple lines, set the <code>minWidth</code> value to <code>max-content</code>.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="Services"
    subtitle="Create and edit courses, classes or appointments"
    actionsBar={
      <Box direction="horizontal" gap="SP2">
        <PopoverMenu
          minWidth="max-content"
          triggerElement={
            <Button priority="secondary" suffixIcon={<Icons.ChevronDown />}>
              More Actions
            </Button>
          }
        >
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Settings />}
            text="Update booking settings"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Payment />}
            text="Accept payments"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Users />}
            text="Manage staff"
          />
          <PopoverMenu.Divider />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Coupon />}
            text="Create coupon"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Google />}
            text="Get booked on Google"
          />
        </PopoverMenu>
        <Button prefixIcon={<Icons.Add />}>New Service</Button>
      </Box>
    }
  />
  <Page.Content>
    <Card>
      <Box height="360px" />
    </Card>
  </Page.Content>
</Page>;
```

### Disabled action explanation
- description: <p>A <code>subtitle</code> should be used to explain disabled actions in a popover menu.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="Contacts"
    subtitle="Sort and keep track of the people who interact with your site"
    actionsBar={
      <Box direction="horizontal" gap="SP2">
        <PopoverMenu
          minWidth="max-content"
          triggerElement={
            <Button priority="secondary" suffixIcon={<Icons.ChevronDown />}>
              More Actions
            </Button>
          }
        >
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.DownloadImport />}
            text="Import contacts"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.UploadExport />}
            text="Export contacts"
            subtitle="Only site owners can export contacts"
            disabled
          />
          <PopoverMenu.Divider />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Adjust />}
            text="Manage custom fields"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Tag />}
            text="Manage labels"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Visible />}
            text="Privacy and GDPR"
          />
          <PopoverMenu.Divider />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Play />}
            text="Watch demo video"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Play />}
            text="Discover CRM tools"
          />
          <PopoverMenu.MenuItem
            prefixIcon={<Icons.Chat />}
            text="Send feedback"
          />
        </PopoverMenu>
        <Button prefixIcon={<Icons.Add />}>New Contact</Button>
      </Box>
    }
  />
  <Page.Content>
    <Card>
      <Box height="360px" />
    </Card>
  </Page.Content>
</Page>;
```


