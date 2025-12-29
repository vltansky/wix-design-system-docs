
## Feature Examples


### Skin
- description: <p>Control the appearance of the floating notification with <code>type</code> prop. It supports 7 options:</p><li><code>standard</code> (default) - use it to provide additional information relevant to current user task or an action.</li><li><code>success</code> - use it to inform users about successful operation. </li><li><code>destructive</code> - use it for error messages and information about critical issues that prevent to continue. </li><li><code>warning</code> - use it to draw the user's attention to unresolved issues that might affect the application, but doesn't block the process. </li><li><code>premium</code> - use it for premium upgrades only — packages that let accept payments, connect domain and have business email. <a href="https://docs.google.com/document/d/1mALfPW9BOZgAjaFpvor5la3WGhGkXIxpbkF2GFrapU0/edit">Read more about Premium patterns</a>.</li><li><code>preview</code> - use it to present process status or related additional data.</li><li><code>dark</code> - use it to emphasize informational messages in the context of other content.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FloatingNotification type="standard" text="Standard (default)" />
  <FloatingNotification type="success" text="Success" />
  <FloatingNotification type="warning" text="Warning" />
  <FloatingNotification type="destructive" text="Destructive" />
  <FloatingNotification type="premium" text="Premium" />
  <FloatingNotification type="preview" text="Preview" />
  <FloatingNotification type="dark" text="Dark" />
</StorybookComponents.Stack>
```

### Width
- description: <p>Control component width in pixels or percentage with <code>width</code> prop.</p><p></p><p>Set component to fill 100% of its parent container width with <code>fullWidth</code> prop. Prop has an effect on notification appearance - it removes left/right borders and corner radius, changes component  height and paddings.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FloatingNotification width="300px" text="Fixed width" />
  <FloatingNotification fullWidth text="Full width" />
</StorybookComponents.Stack>;
```

### Actions
- description: <p>Add call to actions to a notification with:</p><li><code>buttonProps</code> - use to add a primary action</li><li><code>textButtonProps</code> - use it to add a text button. Add a link to an external URL with <code>href</code> prop. </li><p> </p><p>Component can have both actions at the same time.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FloatingNotification
    text="Text message"
    buttonProps={{ label: 'Action' }}
  />
  <FloatingNotification
    text="Text message"
    showTextButton
    textButtonProps={{ label: 'Link' }}
  />
  <FloatingNotification
    text="Text message"
    buttonProps={{ label: 'Action' }}
    textButtonProps={{ label: 'Link to wix.com', as: 'a', href: 'https://www.wix.com' }}
  />
</StorybookComponents.Stack>;
```

### Close Button
- description: <p>Control whether notification can be dismissed by a user with  <code>showCloseButton</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <FloatingNotification text="Dismissable" />
  <FloatingNotification text="Non-dismissable" showCloseButton={false} />
</StorybookComponents.Stack>;
```

### Prefix
- description: <p>Add more context for the  notification purpose with <code>prefixIcon</code>. </p>
- example: 
```jsx 
<FloatingNotification
  text="Notification message here"
  prefixIcon={<Icons.InfoCircle />}
/>;
```




    


## Common Use Case Examples


### In front of content 
- description: <p>Position notification on top of content in modals to update users about the status change. </p>
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
            <FloatingNotification
              prefixIcon={<Icons.StatusAlert />}
              type="destructive"
              text="Fix email value to save account details."
              onClose={() => setState(false)}
            />
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

### Inline with content
- description: <p>Place notifications first in the section that they apply to.</p>
- example: 
```jsx 
<Card hideOverflow>
  <Card.Header
    title="Earn points"
    subtitle="These are the ways customers earn points."
  />
  <FloatingNotification
    type="warning"
    fullWidth
    prefixIcon={<Icons.StatusWarning />}
    text="You don't have ways of Earning Points enabled, so users can't collect points. Enable at least one of the way below."
  />
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


