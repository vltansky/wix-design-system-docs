
## Feature Examples


### Close button
- description: <p>Control if Top Banner can be closed by a users with <code>dismissible</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
<TopBanner
  dismissible={true}
  action={<TopBanner.ActionButton>Action</TopBanner.ActionButton>}
>
Banner is dismissable (default)</TopBanner>
<TopBanner
  dismissible={false}
  action={<TopBanner.ActionButton>Action</TopBanner.ActionButton>}
>
Banner is not dismissable</TopBanner>
</StorybookComponents.Stack>; 
```

### Action
- description: <p>Add button to a top banner with <code>action</code> prop. It's recommended to always provide a corresponding action if possible.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
<TopBanner
  dismissible={true}
  action={<TopBanner.ActionButton>Action</TopBanner.ActionButton>}
>
Banner has an action (default)</TopBanner>
<TopBanner
  dismissible={true}
>
Banner has no action</TopBanner>
</StorybookComponents.Stack>; 
```

### Action type
- description: <p>Control type of action Top banner has through <code>action</code> property:</p><li>Use <code><TopBanner.ActionButton/></code> to provide a main CTA (default).</li><li>Use <code><TopBanner.ActionTextButton/></code> to provide a secondary action, like "Learn more". </li><li>In specific cases, you can provide a different button styling as <code>action</code> is a node. This can also be used when more than one actions are needed. </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TopBanner
    dismissible={true}
    action={<TopBanner.ActionButton>Button</TopBanner.ActionButton>}
  >
    Banner has a button (default)
  </TopBanner>
  <TopBanner
 action={<TopBanner.ActionLink>Text button</TopBanner.ActionLink>}
 dismissible={true}>Banner has a text button</TopBanner>
  <TopBanner
 action={<Button skin="premium-light" size="small">Node </Button>}
 dismissible={true}>Banner action is a node</TopBanner>
</StorybookComponents.Stack>;
```

### Position
- description: <p>Control whether the Top Banner sticks to the top of its container using the  <code>positioning</code> prop:</p><li>Use <code>static</code>  (default) to allow the banner to scroll out of view beneath the top fold.</li><li>Use <code>sticky</code> to keep the banner visible as the user scrolls, with content moving beneath it.</li>
- example: 
```jsx 
() => {
  const [open, setOpen] = React.useState(true);

  return (
    <div style={{ height: '800px', overflow: 'scroll', position: 'relative' }}>
      <Collapse open={open} position="static">
        <TopBanner
          onDismiss={() => setOpen(false)}
          action={<TopBanner.ActionLink>Action</TopBanner.ActionLink>}
        >
          Top banner is static by default
        </TopBanner>
      </Collapse>
      <Page height="600px">
        <Page.Header
          title="Page Title"
          breadcrumbs={
            <Breadcrumbs
              items={[
                { id: 0, value: 'Page Name' },
                { id: 1, value: 'Page title' },
              ]}
            />
          }
          subtitle="I’m a relatively long subtitle to fill this space in."
          actionsBar={
            <div style={{ display: 'flex', gap: 6 }}>
              <Button skin="light">Button</Button>
              <Button skin="standard">Button</Button>
            </div>
          }
        />
        <Page.Content>
          <Card showShadow>
  <Card.Content>
    <Box height="180px" />
  </Card.Content>
</Card>
        </Page.Content>
      </Page>
    </div>
  );
};
```

### Height
- description: <p>Minimum component height is 48px. Component will grow together with the content provided. Heigh is not limited, so be cautious about providing very long texts as it will overlay content behind it.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <TopBanner
    dismissible={true}
    action={<TopBanner.ActionButton>Action</TopBanner.ActionButton>}
  >
    I am a short one line of text that does not wrap
  </TopBanner>
  <TopBanner
    dismissible={true}
    action={<TopBanner.ActionButton>Action</TopBanner.ActionButton>}
  >
    I am a longer content example that automatically wraps to a second line,
    while the top banner grows with it. The height is not limited, accommodating
    all languages and various messages. However, it may cover content on the
    page, so be cautious when writing texts.
  </TopBanner>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### In modals
- description: <p>Top banner component can be used inside of a modal or other container.</p>
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
           <Box direction="vertical">
  <TopBanner
    dismissible={true}
    action={<TopBanner.ActionButton>Upgrade</TopBanner.ActionButton>}
  >
    Upgrade your site to start accepting payments.
  </TopBanner>
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
</Box> 
          }
        />
      </Modal>
    </Card>
  );
};
```

### In pages
- description: <p>Add top banner at the top of <Page/> to promotion premium.</p>
- example: 
```jsx 
() => {
  return (
    <div style={{ height: '800px', overflow: 'scroll', position: 'relative' }}>
      <TopBanner
        position="sticky"
        action={
          <TopBanner.ActionButton as="a" href="lol">
            Upgrade
          </TopBanner.ActionButton>
        }
      >
        Upgrade your site to start accepting payments.
      </TopBanner>
      <Page>
        <Page.Header
          title="Pricing Plans"
          subtitle="Set up subscriptions, memberships or package plans to sell on your site."
          actionsBar={
            <div style={{ display: 'flex', gap: 6 }}>
              <Button  skin="standard">Button</Button>
            </div>
          }
        />
        <Page.Content>
              <EmptyState
      image={<Image width="100px" src="no_categories.png" transparent />}
      title="Add your first pricing plan"
      subtitle="Collect payments from your users. You can connect up to 5 plans to your site"
      theme="page">
      <TextButton prefixIcon={<Icons.Add />}>Add Plan</TextButton>
    </EmptyState>
        </Page.Content>
      </Page>
    </div>
  );
};
```


