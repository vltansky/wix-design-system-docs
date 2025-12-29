
## Feature Examples


### Structure
- description: <p>The component consists of 4 majors elements: <code>title</code>, children, action and close button.</p><p></p><p>Control action label with <code>actionText</code> and its interaction with <code>onAction</code> props, close button with <code>onClose</code> prop.</p>
- example: 
```jsx 
<SectionHelper title="Title" actionText="Action" onAction={() => {}} onClose={() => {}}>
  Content
</SectionHelper>

```

### Size
- description: <p>Adjust Section helper size by using the <code>size</code> prop:</p><p></p><li><code>medium</code> (default) - can be used in all common cases.</li><li><code>small</code> - best for dense layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHelper size="medium">Medium </SectionHelper>
  <SectionHelper size="small">Small </SectionHelper>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the style of the Section helper with the <code>appearance</code> prop. It supports 7 options: </p><li><code>standard</code> - use it to provide additional information relevant to current user task. </li><li><code>success</code> - use it to inform users about successful operation.</li><li><code>warning</code> (default) - use it to draw the user's attention to unresolved issues.</li><li><code>danger</code> - use it for error messages and information about critical issues.</li><li><code>premium</code> - use it for premium upgrades only — packages that let accept payments, connect domain and have business email. <a href="https://docs.google.com/document/d/1mALfPW9BOZgAjaFpvor5la3WGhGkXIxpbkF2GFrapU0/edit">Read more about Premium patterns</a>.</li><li><code>preview</code> - use it to present process status or related additional data.</li><li><code>experimentalDark</code> - use it to emphasize informational messages in the context of other content.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHelper appearance="standard">Standard </SectionHelper>
  <SectionHelper appearance="success">Success </SectionHelper>
  <SectionHelper appearance="warning">Warning </SectionHelper>
  <SectionHelper appearance="danger">Danger </SectionHelper>
  <SectionHelper appearance="premium">Premium</SectionHelper>
  <SectionHelper appearance="preview">Preview </SectionHelper>
  <SectionHelper appearance="experimentalDark">Dark </SectionHelper>
</StorybookComponents.Stack>;
```

### Prefix
- description: <li>Use <code>showPrefixIcon</code> prop to show default status icon.</li><li>Add more context for the Section helper by also using <code>prefixIcon</code> prop.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHelper showPrefixIcon prefixIcon={<Icons.EmailAlert />}>Fix email value to save account details.
 </SectionHelper>
  <SectionHelper showPrefixIcon>Warning message</SectionHelper>
</StorybookComponents.Stack>;
```

### Close button
- description: <p>Control whether Section helper can be dismissed by a user with <code>showCloseButton</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHelper>Non-dismissable</SectionHelper>
  <SectionHelper showCloseButton={true}>Dismissable</SectionHelper>
</StorybookComponents.Stack>;
```

### Border
- description: <p>Use <code>border</code> prop to choose between: </p><p></p><li><code>standard</code> (default) -  can be used in all common cases.</li><li><code>topBottom</code> - used for banner type use cases.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHelper border="standard">Standard</SectionHelper>
  <SectionHelper border="topBottom">Top bottom</SectionHelper>
</StorybookComponents.Stack>;
```

### Layout
- description: <p>Change content direction by using layout prop:</p><p></p><li><code>vertical</code> (default) arranges content horizontally.</li><li><code>horizontal</code> arranges content vertically.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
<SectionHelper
  title="Title"
  actionText="Action"
  layout="vertical"

>
  Vertical content
</SectionHelper>
  <SectionHelper
  title="Title"
  actionText="Action"
  layout="horizontal"

>
  Horizontal content
</SectionHelper>
</StorybookComponents.Stack>;
```

### Content width
- description: <p>Enable content width to be 100% wide with <code>fullWidth</code> prop.</p><p></p><p>By default component's title and content are limited to maximum width of 420 pixels to improve text reading experience.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SectionHelper
    title="The Life and Strange Surprizing Adventures of Robinson Crusoe, Of York,
    Mariner: Who lived Eight and Twenty Years, all alone in an un-inhabited
    Island on the Coast of America, near the Mouth of the Great River of
    Oroonoque;"
  >
    Having been cast on Shore by Shipwreck, wherein all the Men perished but
    himself. With An Account how he was at last as strangely deliver'd by
    Pyrates.
  </SectionHelper>
  <SectionHelper
    fullWidth
    title="The Life and Strange Surprizing Adventures of Robinson Crusoe, Of York,
    Mariner: Who lived Eight and Twenty Years, all alone in an un-inhabited
    Island on the Coast of America, near the Mouth of the Great River of
    Oroonoque;"
  >
    Having been cast on Shore by Shipwreck, wherein all the Men perished but
    himself. With An Account how he was at last as strangely deliver'd by
    Pyrates.
  </SectionHelper>
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Application error
- description: <p>Errors  occur because of breaches in application logic or conditions, for example when users reach storage limits or their payment method has expired. These errors can occur before users even open the application or a specific page, making it essential for them to be visible upon arrival.</p><p></p><p>Place application errors first in the page, below the page header using the error banner.</p>
- example: 
```jsx 
<Page>
  <Page.Header
    title="Online Programs"
    subtitle="Build and market multi-step courses."
    actionsBar={
      <Box gap="SP2">
        <Button prefixIcon={<Icons.Add />}>Create New</Button>
      </Box>
    }
  />
  <Page.Content>
    <Layout>
      <Cell>
        <SectionHelper
          appearance="danger"
          title="Payment method expired"
          actionText="Update Payment Method"
          onAction={() => {}}
          onClose={() => {}}
        >
          The payment method linked to your account expired two days ago. To
          continue receiving payments for your online program, updated your
          payment details.
        </SectionHelper>
      </Cell>
      <Cell>
        <Card>
          <Card.Content>
            <Box height="120px" />
          </Card.Content>
        </Card>
      </Cell>
      <Cell>
        <Card>
          <Card.Content>
            <Box height="120px" />
          </Card.Content>
        </Card>
      </Cell>
    </Layout>
  </Page.Content>
</Page>;

```

### Inline with content
- description: <p>Place Section helper first in the section that they apply to.</p>
- example: 
```jsx 
<Card hideOverflow>
  <Card.Header
    title="Earn points"
    subtitle="These are the ways customers earn points."
  />
  <SectionHelper
    fullWidth
    size="small"
    border="topBottom"
    showCloseButton
    showPrefixIcon
    layout="horizontal"
  >
    You don't have ways of Earning Points enabled, so users can't collect
    points. Enable at least one of the way below.
  </SectionHelper>

  <TableListItem
    showDivider
    options={[
      {
        value: (
          <FormField label="Inactive" labelPlacement="right">
            <ToggleSwitch size="medium" />
          </FormField>
        ),
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text size="small" weight="bold">
              Make a Restaurant Order
            </Text>
            <Text size="small">Give 1 points for every 1$ spent.</Text>
          </Box>
        ),
      },
      {
        value: (
          <IconButton priority="secondary" size="small">
            <Icons.MoreSmall />
          </IconButton>
        ),
        width: 'auto',
      },
    ]}
  />
  <TableListItem
    options={[
      {
        value: (
          <FormField label="Inactive" labelPlacement="right">
            <ToggleSwitch size="medium" />
          </FormField>
        ),
        width: 'auto',
      },
      {
        value: (
          <Box direction="vertical">
            <Text size="small" weight="bold">
              Sign Up to the Site
            </Text>
            <Text size="small">Give 100 points after sign up.</Text>
          </Box>
        ),
      },
      {
        value: (
          <IconButton priority="secondary" size="small">
            <Icons.MoreSmall />
          </IconButton>
        ),
        width: 'auto',
      },
    ]}
  />
</Card>;

```

### In front of content
- description: <p>Position Section helper on top of content in modals to update users about the status change.</p>
- example: 
```jsx 
() => {
  const [state, setState] = React.useState(true);
  return (
    <CustomModalLayout
      title="Account details"
      subtitle="Manage name and email details."
      secondaryButtonText="Cancel"
      primaryButtonText="Save"
      showHeaderDivider
      overflowY={false}
      onCloseButtonClick={() => setState(true)}
      primaryButtonOnClick={() => setState(true)}
      secondaryButtonOnClick={() => setState(true)}
    >
      <Layout>
        {state && (
          <Box
            position="absolute"
            top="24px"
            left="50%"
            transform="translateX(-50%)"
          >
            <SectionHelper
              appearance="danger"
              size="small"
              showCloseButton
              showPrefixIcon
              layout="horizontal"
              onClose={() => setState(false)}
            >
              Fix email value to save account details.
            </SectionHelper>
          </Box>
        )}
        <Cell span={6}>
          <FormField label="First name">
            <Input defaultValue="John" />
          </FormField>
        </Cell>
        <Cell span={6}>
          <FormField label="Last name">
            <Input defaultValue="Smith" />
          </FormField>
        </Cell>
        <Cell>
          <FormField
            label="Email address"
            status="error"
            statusMessage='Provide the email in format "your@email.com"'
          >
            <Input defaultValue="asfljaokfjalk" type="email" />
          </FormField>
        </Cell>
      </Layout>
    </CustomModalLayout>
  );
};

```


