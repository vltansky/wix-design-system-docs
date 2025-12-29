
## Feature Examples


### Structure
- description: <p>The custom modal layout can include the following:</p><li><code>title</code> (required)</li><li><code>subtitle</code></li><li><code>content</code> (required)</li><li><code>sideActions</code></li><li><code>footnote</code></li><p></p><p>To add supplementary actions, like a "Don't show this again" checkbox, use <code>sideActions</code>. </p><p></p><p>To include additional information, add a <code>footnote</code>, e.g., “By sending an invite, you agree to the Wix Terms of Use.”</p>
- example: 
```jsx 
<CustomModalLayout
  primaryButtonText="Save"
  secondaryButtonText="Cancel"
  onCloseButtonClick={() => {}}
  title="Title"
  subtitle="Subtitle"
  footnote={
    <StorybookComponents.Placeholder>Footnote</StorybookComponents.Placeholder>
  }
  sideActions={
    <StorybookComponents.Placeholder>
      Side actions
    </StorybookComponents.Placeholder>
  }
  content={
    <StorybookComponents.Placeholder height="240px">
      Content
    </StorybookComponents.Placeholder>
  }
/>;
```

###  Height and width
- description: <p>By default, modals grow with their content, but they'll never extend higher than the user’s viewport (with 48 px top and bottom padding).</p><p></p><p>Control a custom modal's height with these two properties:</p><li><code>height</code> fixes height in pixels.</li><li><code>maxHeight</code> sets a custom max height in pixels.</li><p></p><p>When modal content extends below the user's viewport, <code>height</code> or <code>maxHeight</code>, content scrolls vertically with a fixed header and footer.</p><p></p><p>Control a custom modal's width with <code>width</code> property.</p><p>Minimum width of a modal is 510px., maximum width is 1254px.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    secondaryButtonOnClick={() => {}}
    primaryButtonOnClick={() => {}}
    title="Auto height (default)"
    content={<Box height="180px" />}
  />

  <CustomModalLayout
    height="360px"
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    secondaryButtonOnClick={() => {}}
    primaryButtonOnClick={() => {}}
    title="Height is fixed at 360 px"
    content={<Box height="360px" />}
  />
</StorybookComponents.Stack>;
```

### Content padding
- description: <p>Remove the default 30 px left and right content padding with the <code>removeContentPadding</code> prop.</p><p></p><p>This property can be used to show components with built-in padding like <code><Page/></code> or <code><Table/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Default content padding"
    content={<StorybookComponents.Placeholder height="60px" />}
  />
  <CustomModalLayout
    removeContentPadding
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="No content padding"
    content={<StorybookComponents.Placeholder height="60px" />}
  />
</StorybookComponents.Stack>;
```

### Theme
- description: <p>Control the component style with <code>theme</code> prop:</p><li><code>standard</code> is the default used in all common cases. </li><li><code>premium</code> is used to promote Premium features.</li><li><code>destructive</code> is for actions that have a destructive effect on user data, like delete.  For short warning messages, use the <code><MessageModalLayout/></code> in a destructive theme instead. </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Standard (default)"
    content={<StorybookComponents.Placeholder height="60px" />}
  />
  <CustomModalLayout
    theme="premium"
    primaryButtonText="Upgrade"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Premium"
    content={<StorybookComponents.Placeholder height="60px" />}
  />
  <CustomModalLayout
    theme="destructive"
    primaryButtonText="Delete"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Destructive"
    content={<StorybookComponents.Placeholder height="60px" />}
  />
</StorybookComponents.Stack>;
```

### Header and footer dividers
- description: <p>Control visibility of both the header and footer dividers with the <code>showHeaderDivider</code> and <code>showFooterDivider</code> props.</p><p></p><li><code>auto</code> is the default that shows header divider only when content is scrolled and always shows the footer divider.</li><li><code>true</code> always shows the dividers.</li><li><code>false</code> always hides the dividers.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Auto (default)"
    height="240px"
    content={<StorybookComponents.Placeholder height="300px" />}
  />
  <CustomModalLayout
    showFooterDivider
    showHeaderDivider
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Always show dividers"
    height="240px"
    content={<StorybookComponents.Placeholder height="300px" />}
  />
  <CustomModalLayout
    showFooterDivider="false"
    showHeaderDivider="false"
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Hide dividers"
    height="240px"
    content={<StorybookComponents.Placeholder height="300px" />}
  />
</StorybookComponents.Stack>;
```

### Help and close buttons
- description: <p>Add a help button with the <code>onHelpButtonClick</code> prop. Use it to direct users to support sources, for example, the Wix Help Center.</p><p></p><p>The close button is required for all modals.</p>
- example: 
```jsx 
<CustomModalLayout
  primaryButtonText="Save"
  secondaryButtonText="Cancel"
  onCloseButtonClick={() => {}}
  onHelpButtonClick={() => {}}
  title="Title"
  content={<StorybookComponents.Placeholder height="60px" />}
/>;
```

### Side actions
- description: <p>Add supplementary actions in the <code>sideActions</code> container.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    sideActions={
      <StorybookComponents.Placeholder>
        Side actions
      </StorybookComponents.Placeholder>
    }
    content={<StorybookComponents.Placeholder height="60px" />}
  />
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    sideActions={<Checkbox>Don’t show this again</Checkbox>}
    content={<StorybookComponents.Placeholder height="60px" />}
  />
  <CustomModalLayout
    onCloseButtonClick={() => {}}
    title="Title"
    sideActions={
      <StorybookComponents.Stack justifyContent="space-between">
        <Button priority="secondary" size="small">
          Cancel
        </Button>
        <StorybookComponents.Stack gap="8px" justifyContent="flex-end">
          <Button
            priority="secondary"
            size="small"
            prefixIcon={<Icons.DismissSmall />}
          >
            Reject
          </Button>
          <Button
            priority="secondary"
            size="small"
            prefixIcon={<Icons.TimeSmall />}
          >
            Keep for later
          </Button>
          <Button
            priority="secondary"
            size="small"
            prefixIcon={<Icons.ConfirmSmall />}
          >
            Approve
          </Button>
        </StorybookComponents.Stack>
      </StorybookComponents.Stack>
    }
    content={<StorybookComponents.Placeholder height="60px" />}
  />
</StorybookComponents.Stack>;
```

### Footnote
- description: <p>Add supplementary text and links into the <code>footnote</code> container.</p><p></p><p>Footnote also has a <code>footnoteSkin</code> property, that provides a <code>light</code> skin, that can be used fore busier modal layouts.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    footnote={ 
      <StorybookComponents.Placeholder>
        Footnote
      </StorybookComponents.Placeholder>
    }
    content={<StorybookComponents.Placeholder height="60px" />}
  />

  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    footnote={
      <Text size="small">
        By continuing, you agree to the <a>Wix Terms of Use</a>
      </Text>
    }
    content={<StorybookComponents.Placeholder height="60px" />}
  />
    <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
      footnoteSkin="light"
    footnote={
      <Text size="small">
        By continuing, you agree to the <a>Wix Terms of Use</a>
      </Text>
    }
    content={<StorybookComponents.Placeholder height="60px" />}
  />
</StorybookComponents.Stack>;
```

### Title and subtitle
- description: <p>Add short text to summarize modal content with the <code>title</code> and <code>subtitle</code> props.</p><p></p><p>Both <code>title</code> and <code>subtitle</code> are nodes, so they can contain other components. For example, add inline <code><TextButton/></code> linking to relevant information in a subtitle.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title (required)"
    subtitle="Subtitle (optional)"
    content={<StorybookComponents.Placeholder height="60px" />}
  />
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    subtitle={
      <StorybookComponents.Stack gap="6px">
        <Text secondary>Subtitle</Text>
        <TextButton underline="always">Inline text button</TextButton>
      </StorybookComponents.Stack>
    }
    content={<StorybookComponents.Placeholder height="60px" />}
  />
</StorybookComponents.Stack>;
```

### Action buttons
- description: <p>Specify labels for primary and secondary actions with <code>primaryButtonText</code> and <code>secondaryButtonText</code> props.</p><p></p><p>For additional styling, like adding a prefix icon, use any available <code><Button/></code> <a href="https://www.wix-style-react.com/storybook/?path=/story/components-actions--button"></a>props via the <code>primaryButtonProps</code> and <code>secondaryButtonProps</code>.</p>
- example: 
```jsx 
<CustomModalLayout
  primaryButtonText="Approve"
  primaryButtonProps={{ prefixIcon: <Icons.ConfirmSmall /> }}
  secondaryButtonText="Reject"
  secondaryButtonProps={{ prefixIcon: <Icons.DismissSmall /> }}
  onCloseButtonClick={() => {}}
  title="Title"
  content={<StorybookComponents.Placeholder height="60px" />}
/>;
```

### Disabled primary action
- description: <p>Disable a primary action using the <code>disabled</code> prop in <code>primaryButtonProps</code>.</p><p></p><p>Add an explanation in a tooltip about why this action is not allowed with <code>primaryButtonTooltipProps</code>.</p><p></p><p>Use any of the <code><Tooltip/></code> props to style the tooltip.</p>
- example: 
```jsx 
<CustomModalLayout
  primaryButtonText="Save"
  primaryButtonProps={{ disabled: true }}
  primaryButtonTooltipProps={{ content: 'Tells users why they cannot Save' }}
  secondaryButtonText="Cancel"
  onCloseButtonClick={() => {}}
  title="Title"
  content={<StorybookComponents.Placeholder height="60px" />}
/>;
```




## Developer Examples


### Vertical overflow
- description: <p>Modal headers and footers can cut content outlines when placed next to the top or bottom content areas.</p><p></p><p>Set vertical <code>overflowY</code> prop to <code>none</code> to show the full outline.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    content={<Input placeholder="Click here to see the default outlines" />}
  />
  <CustomModalLayout
    primaryButtonText="Save"
    secondaryButtonText="Cancel"
    onCloseButtonClick={() => {}}
    title="Title"
    overflowY="none"
    content={
      <Input placeholder="Click here to see the outlines with overflowY prop" />
    }
  />
</StorybookComponents.Stack>;
```

### Modal with overlays
- description: <p>By default, modals do not allow content to overflow.</p><p></p><p>Use <code>popoverProps</code>, <code>appendTo</code> and <code>dynamicWidth</code> props to display overlays as intended. For more guidance, read about the <code><Popover/></code> component.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);

  return (
    <Card>
      <Card.Header
        title="Allow using coupons"
        subtitle="Let visitors use coupons to get discounts & special deals."
        suffix={
          <Button
            size="small"
            priority="secondary"
            onClick={() => setShown(true)}
          >
            Apply Coupon
          </Button>
        }
      />
      <Modal
        isOpen={shown}
        onRequestClose={() => setShown(false)}
        shouldCloseOnOverlayClick
        screen="desktop"
      >
        <CustomModalLayout
          primaryButtonText="Apply"
          primaryButtonOnClick={() => setShown(false)}
          secondaryButtonText="Cancel"
          secondaryButtonOnClick={() => setShown(false)}
          onCloseButtonClick={() => setShown(false)}
          title="Apply a coupon"
          overflowY="none"
          content={
            <FormField label="Select coupon">
              <Dropdown
                popoverProps={{
                  appendTo: 'scrollParent',
                  dynamicWidth: 'true',
                }}
                options={[
                  { id: 0, value: 'None' },
                  { id: 1, value: 'SUMMER15' },
                  { id: 2, value: 'BACKTOSCHOOL' },
                  { id: 3, value: 'AUGUST10' },
                  { id: 4, value: 'OUTWITHTHEOLD' },
                ]}
                placeholder="Select from the list"
              />
            </FormField>
          }
        />
      </Modal>
    </Card>
  );
};
```


    


## Common Use Case Examples


### Modal with no content padding
- description: <p>Remove default content padding when displaying a <code><Table/></code>, <code><Page/></code> or other content with built-in or custom padding.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);
  const [copy, setCopy] = React.useState(false);

  const data = [
    { name: 'User 1', plan: 'Gold', email: 'user1@mail.com' },
    { name: 'User 2', plan: 'Silver', email: 'user2@mail.com' },
    { name: 'User 3', plan: 'Gold', email: 'user3@mail.com' },
    { name: 'User 4', plan: 'Gold', email: 'user4@mail.com' },
    { name: 'User 5', plan: 'Bronze', email: 'user5@mail.com' },
    { name: 'User 6', plan: 'Bronze', email: 'user6@mail.com' },
    { name: 'User 7', plan: 'Gold', email: 'user7@mail.com' },
    { name: 'User 8', plan: 'Bronze', email: 'user8@mail.com' },
  ];
  const columns = [
    { title: 'Name', render: row => row.name },
    { title: 'Plan', render: row => row.plan },
    { title: 'Email', render: row => row.email },
  ];

  return (
    <Card>
      <Card.Header
        title="Send coupons to your members"
        subtitle="Select members who will receive a new coupon via email."
        suffix={
          <Button
            size="small"
            priority="secondary"
            onClick={() => setShown(true)}
          >
            Send Coupons
          </Button>
        }
      />
      <Modal
        isOpen={shown}
        onRequestClose={() => setShown(false)}
        shouldCloseOnOverlayClick
        screen="desktop"
      >
        <CustomModalLayout
          title="Send coupons to members"
          subtitle="Select members who will receive coupons via email."
          onCloseButtonClick={() => setShown(false)}
          primaryButtonOnClick={() => setShown(false)}
          secondaryButtonOnClick={() => setShown(false)}
          width="720px"
          maxHeight="480px"
          removeContentPadding
          primaryButtonText="Send"
          secondaryButtonText="Cancel"
          sideActions={
            <Checkbox
              size="small"
              checked={copy}
              onChange={() => setCopy(!copy)}
            >
              Send copy Email to myself
            </Checkbox>
          }
          content={
            <Table data={data} columns={columns} showSelection>
              <Table.Content />
            </Table>
          }
        />
      </Modal>
    </Card>
  );
};
```

### Modal with multiple actions
- description: <p>If a modal has more than two actions, use <code>sideActions</code> container to group them.</p><p></p><p>Cancel button is required and should always be positioned on the left side of the action list.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);

  return (
    <Layout>
      <Cell span={6}>
        <Card>
          <Box
            direction="vertical"
            gap="1"
            paddingTop="2"
            paddingLeft="4"
            paddingRight="4"
            paddingBottom="2"
          >
            <Text secondary>From name:</Text>
            <Text weight="bold">User 1</Text>
            <Text secondary>Reply-to email:</Text>
            <Text weight="bold">User1@mail.com</Text>
          </Box>
          <Divider />
          <Box
            paddingTop="2"
            paddingLeft="4"
            paddingRight="4"
            paddingBottom="2"
            align="center"
          >
            <TextButton onClick={() => setShown(true)}>
              Confirm Email
            </TextButton>
          </Box>
          <Modal
            isOpen={shown}
            onRequestClose={() => setShown(false)}
            shouldCloseOnOverlayClick
            screen="desktop"
          >
            <CustomModalLayout
              primaryButtonText="Confirm"
              secondaryButtonText="Change Details"
              onCloseButtonClick={() => setShown(false)}
              secondaryButtonOnClick={() => setShown(false)}
              primaryButtonOnClick={() => setShown(false)}
              overflowY="none"
              width="600px"
              title="Confirm your email address"
              content={
                <Layout>
                  <Cell>
                    <Text>
                      To make changes to your sender details, please confirm
                      your email address.
                      <br />A confirmation code was sent to <b>user1@mail.com</b>
                      .
                    </Text>
                  </Cell>
                  <Cell span={6}>
                    <FormField label="Confirmation Code">
                      <Input placeholder="XX-XXX-XX" />
                    </FormField>
                  </Cell>
                  <Cell>
                    <Text>
                      Didn't get the code? <a>Send again</a>
                    </Text>
                  </Cell>
                </Layout>
              }
              sideActions={
                <Button
                  onClick={() => setShown(false)}
                  priority="secondary"
                  size="small"
                >
                  Cancel
                </Button>
              }
            />
          </Modal>
        </Card>
      </Cell>
    </Layout>
  );
};
```

### Modal with a page inside
- description: <p>When a <code><Page/></code> can be accessed from multiple entry points, show it in a modal to keep users in the main flow.</p><p></p><p>Make the modal as large as possible and structure content within cards. If other modals can be triggered, make them significantly smaller to communicate their hierarchy.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);

  return (
    <Card>
      <Card.Header
        title="Pricing plans"
        subtitle="Let clients book this service with a plan."
        suffix={
          <Button
            size="small"
            priority="secondary"
            prefixIcon={<Icons.AddSmall />}
            onClick={() => setShown(true)}
          >
            Create New Plan
          </Button>
        }
      />
      <Modal
        isOpen={shown}
        onRequestClose={() => setShown(false)}
        shouldCloseOnOverlayClick
        screen="desktop"
      >
        <CustomModalLayout
          primaryButtonText="Create Plan"
          secondaryButtonText="Cancel"
          onCloseButtonClick={() => setShown(false)}
          onHelpButtonClick={() => {}}
          secondaryButtonOnClick={() => setShown(false)}
          primaryButtonOnClick={() => setShown(false)}
          removeContentPadding
          title="Create new pricing plan"
          content={
            <Page>
              <Page.Content>
                <Box marginTop={5} display="block">
                  <Layout>
                    <Cell span="12">
                      <Card>
                        <Card.Header
                          title="Plan info"
                          subtitle="Give your plan a name and tell customers what it includes"
                        />
                        <Card.Divider />
                        <Card.Content>
                          <Layout>
                            <Cell span="6">
                              <FormField
                                label="Name this plan"
                                required
                                charCount="20"
                              >
                                <Input placeholder="e.g., Silver Membership" />
                              </FormField>
                            </Cell>
                            <Cell span="6">
                              <FormField label="Add a tagline" charCount="60">
                                <Input placeholder="e.g., Perfect for beginners" />
                              </FormField>
                            </Cell>
                            <Cell span="12">
                              <AddItem size="tiny">
                                Add what this plan includes
                              </AddItem>
                            </Cell>
                          </Layout>
                        </Card.Content>
                      </Card>
                    </Cell>
                    <Cell span="12">
                      <Card>
                        <Card.Header
                          title="Connect and manage benefits"
                          subtitle="Set up how your benefits work in this plan."
                        />
                        <Card.Divider />
                        <Box
                          display="block"
                          borderRadius={8}
                          paddingBottom="8px"
                        >
                          <SelectableAccordion
                            type="checkbox"
                            items={[
                              {
                                title: 'Bookings Services',
                                subtitle:
                                  'Offer services as a membership or package with this plan.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Booking Services content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                              {
                                title: 'Video Channels',
                                subtitle:
                                  'Offer access to your Video Channel with this plan.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Video Channels content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                              {
                                title: 'Blog Subscriptions',
                                subtitle: 'Give exclusive access to posts.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Blog Subscriptions content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                              {
                                title: 'Forum Subscriptions',
                                subtitle:
                                  'Give exclusive access to forum categories.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Forum Subscriptions content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                              {
                                title: 'Events Memberships',
                                subtitle:
                                  'Add ticket discount and ticket limit for your events.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Events Memberships content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                              {
                                title: 'Online Programs',
                                subtitle:
                                  'Allow participation in different programs with this plan.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Online Programs content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                              {
                                title: 'Groups',
                                subtitle:
                                  'Give clients access to exclusive groups.',
                                content: (
                                  <StorybookComponents.Placeholder>
                                    Groups content
                                  </StorybookComponents.Placeholder>
                                ),
                              },
                            ]}
                          />
                        </Box>
                      </Card>
                    </Cell>
                  </Layout>
                </Box>
              </Page.Content>
            </Page>
          }
        />
      </Modal>
    </Card>
  );
};
```

### Modal with marketing layout
- description: <p>Focus users’ attention on feature promotions with modals. Use them sparingly and only after users intentionally open the promotional content. </p><p></p><p>For example, use a custom modal layout with a <code><MarketingLayout/></code> inside.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);

  return (
    <Card>
      <Card.Header
        title="Add Logo to your website"
        subtitle="Customize your website to match the colors and style of your logo."
        suffix={
          <Button
            size="small"
            priority="secondary"
            onClick={() => setShown(true)}
          >
            Connect Website
          </Button>
        }
      />
      <Modal
        isOpen={shown}
        onRequestClose={() => setShown(false)}
        shouldCloseOnOverlayClick
        screen="desktop"
      >
        <CustomModalLayout
          width="720px"
          removeContentPadding
          onCloseButtonClick={() => setShown(false)}
          content={
            <Card>
              <MarketingLayout
                size="medium"
                title="Wix unlimited website Premium plan"
                description="Get a customizable website, designed to match the colors and style of your logo."
                actions={
                  <Button onClick={() => setShown(false)}>Add to Cart</Button>
                }
                image={
                  <Box height="156px">
                    <Image src="MarketingIllustration1.png" transparent />
                  </Box>
                }
              />
            </Card>
          }
        />
      </Modal>
    </Card>
  );
};
```


