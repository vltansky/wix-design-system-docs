
## Feature Examples


### Theme
- description: <p>Use different <code>theme</code> according to the nature of the modal:</p><li>For default cases use <code>standard</code>.</li><li>Promote Premium features with <code>premium</code>.</li><li>To inform users of the negative implications of an action, like loss of data, use <code>destructive</code> .</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <MessageModalLayout
    onCloseButtonClick={() => {}}
    primaryButtonText="Leave Page"
    secondaryButtonText="Cancel"
    title="Leave page?"
    content={
      <Text>When you leave this page, you'll lose unsaved changes.</Text>
    }
  />
  <MessageModalLayout
    theme={'premium'}
    onCloseButtonClick={() => {}}
    primaryButtonText="Upgrade"
    secondaryButtonText="Not Now"
    title="Upgrade to accept payments"
    content={
      <Text>To accept payments, upgrade to the Business Basic plan.</Text>
    }
  />
  <MessageModalLayout
    theme={'destructive'}
    onCloseButtonClick={() => {}}
    primaryButtonText="Delete"
    secondaryButtonText="Cancel"
    title="Delete category?"
    content={
      <Text>
        You're about to delete the <b>Yoga</b> category. Posts inside this
        category will also be deleted.
      </Text>
    }
  />
</StorybookComponents.Stack>;
```

### Help and close buttons
- description: <p>Add a help button with the <code>onHelpButtonClick</code> prop. Use it to direct users to support.</p><p></p><p>Close button is required for all modals. Control its function with the<code>onCloseButtonClick</code> prop.</p>
- example: 
```jsx 
<MessageModalLayout
  onCloseButtonClick={() => {}}
  onHelpButtonClick={() => {}}
  primaryButtonText="Leave Page"
  secondaryButtonText="Cancel"
  title="Leave page?"
  content={<Text>When you leave this page, you'll lose unsaved changes.</Text>}
/>;
```

### Illustration
- description: <p>Add visuals to the left side of the content to support main modal messages using the <code>illustration</code> prop.</p><p></p><p>Use 120x120 px illustrations and coordinate the skin with the theme of the modal.  </p><p></p><p><em>Note</em>: For Wix products, browse all available illustrations or request a new one on <a href="https://www.wixuxillustrations.com/">Wix UX Illustrations</a>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <MessageModalLayout
    illustration="generic_report.svg"
    onCloseButtonClick={() => {}}
    primaryButtonText="Report"
    secondaryButtonText="Cancel"
    title="Report as spam?"
    content={<Text>Messages marked as spam are blocked from your inbox.</Text>}
  />
  <MessageModalLayout
    illustration="generic_upgrade.svg"
    theme={'premium'}
    onCloseButtonClick={() => {}}
    primaryButtonText="Upgrade"
    secondaryButtonText="Not Now"
    title="Start accepting online payments"
    content={
      <Text>
        Upgrade your site to a Business Basic plan to start accepting payments.
      </Text>
    }
  />
  <MessageModalLayout
    illustration="generic_trash.svg"
    theme={'destructive'}
    onCloseButtonClick={() => {}}
    primaryButtonText="Delete"
    secondaryButtonText="Cancel"
    title="Delete category"
    content={
      <Text>
        You're about to delete the <b>Yoga</b> category. Posts inside this
        category will also be deleted.
      </Text>
    }
  />
</StorybookComponents.Stack>;
```

### Side actions
- description: <p>Add supplementary actions in the <code>sideActions</code> container.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <MessageModalLayout
    onCloseButtonClick={() => {}}
    primaryButtonText="Leave Page"
    secondaryButtonText="Cancel"
    title="Leave page?"
    content={
      <Text>When you leave this page, you'll lose unsaved changes.</Text>
    }
    sideActions={
      <StorybookComponents.Placeholder>
        Side actions
      </StorybookComponents.Placeholder>
    }
  />
  <MessageModalLayout
    onCloseButtonClick={() => {}}
    primaryButtonText="Leave Page"
    secondaryButtonText="Cancel"
    title="Leave page?"
    content={
      <Text>When you leave this page, you'll lose unsaved changes.</Text>
    }
    sideActions={<Checkbox>Don't show this again</Checkbox>}
  />
</StorybookComponents.Stack>;
```

### Footnote
- description: <p>Add supplementary text and/or links into the <code>footnote</code> container.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <MessageModalLayout
    onCloseButtonClick={() => {}}
    primaryButtonText="Invite All"
    secondaryButtonText="Cancel"
    title="Invite all site members"
    content={<Text>You're about to send invites to all site members.</Text>}
    footnote={
      <StorybookComponents.Placeholder>
        Footnote
      </StorybookComponents.Placeholder>
    }
  />
  <MessageModalLayout
    onCloseButtonClick={() => {}}
    primaryButtonText="Invite All"
    secondaryButtonText="Cancel"
    title="Invite all site members"
    content={<Text>You're about to send invites to all site members.</Text>}
    footnote={
      <Text size="small">
        By sending an invite, you agree to the <a>Wix Terms of Use.</a>
      </Text>
    }
  />
</StorybookComponents.Stack>;
```

### Title
- description: <p>Add short text to summarize modal content using the <code>title</code> prop.</p>
- example: 
```jsx 
<MessageModalLayout
  onCloseButtonClick={() => {}}
  primaryButtonText="Leave Page"
  secondaryButtonText="Cancel"
  title="Leave page?"
  content={<Text>When you leave this page, you'll lose unsaved changes.</Text>}
/>;
```

### Action buttons
- description: <p>Specify labels for primary and secondary actions with <code>primaryButtonText</code> and <code>secondaryButtonText</code> props.</p><p></p><p>For additional styling, like adding a prefix icon, use any available <code><Button/></code> props in <code>primaryButtonProps</code> and <code>secondaryButtonProps</code>.</p>
- example: 
```jsx 
<MessageModalLayout
  onCloseButtonClick={() => {}}
  primaryButtonText="Invite All"
  primaryButtonProps={{ prefixIcon: <Icons.EmailSendSmall /> }}
  secondaryButtonText="Cancel"
  title="Invite all site members"
  content={<Text>You're about to send invites to all site members.</Text>}
/>;
```




    


## Common Use Case Examples


### Warn about destructive changes
- description: <p>Use the <code>destructive</code> theme to bring more attention to modals that confirm irreversible actions.  </p><p></p><p>Use the <code><Text/></code><a href="https://www.wix-style-react.com/storybook/?path=/story/components-typography-text--text"></a> component props to style the modal content.</p>
- example: 
```jsx 
<MessageModalLayout
  theme={'destructive'}
  onCloseButtonClick={() => {}}
  primaryButtonText="Delete"
  secondaryButtonText="Cancel"
  title="Delete category?"
>
  <Text>
    You're about to delete the <b>Yoga</b> category. Posts inside this category
    will also be deleted.
  </Text>
</MessageModalLayout>;
```

### Alert users to unsaved changes
- description: <p>Use a message modal to inform users that their changes won't be saved if the action is taken. </p>
- example: 
```jsx 
<MessageModalLayout
  primaryButtonText="Leave Page"
  secondaryButtonText="Cancel"
  title="Leave page?"
  onCloseButtonClick={() => {}}
>
  <Text>When you leave this page, you'll lose unsaved changes.</Text>
</MessageModalLayout>;
```

### Promote Premium features
- description: <p>Use the <code>illustration</code> prop to support upgrade messages. Illustrations can showcase the features available with upgrades.</p>
- example: 
```jsx 
<MessageModalLayout
  onCloseButtonClick={() => {}}
  theme={'premium'}
  primaryButtonText="Upgrade"
  secondaryButtonText="Not Now"
  title="Upgrade to accept payments"
  illustration={'generic_upgrade.svg'}
>
  <Text>
    Upgrade your site to a Business Basic plan to start accepting payments.
  </Text>
</MessageModalLayout>;
```


