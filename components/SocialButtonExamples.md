
## Feature Examples


### Text
- description: <p>Give users additional explanation  by  using <code>text</code> prop to show label under the button.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SocialButton text="Share on Facebook" icon="facebook" />
  <SocialButton icon="facebook" />
</StorybookComponents.Stack>

```

### Icon
- description: <p>Theme component to match social networks by using the icon prop with one of the following themes.</p><li><code>facebook</code></li><li><code>twitter</code></li><li><code>linkedIn</code></li><li><code>instagram</code></li><li><code>pinterest</code></li><li><code>youtube</code></li><li><code>xcorp</code></li>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SocialButton icon="facebook" />
  <SocialButton icon="twitter" />
  <SocialButton icon="linkedin" />
  <SocialButton icon="instagram" />
  <SocialButton icon="pinterest" />
  <SocialButton icon="youtube" />
  <SocialButton icon="xcorp" />
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Indicate that action is available but can not be performed at the moment by using <code>disabled</code> property.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <SocialButton icon="facebook" disabled />
  <SocialButton icon="twitter" disabled />
  <SocialButton icon="linkedin" disabled />
  <SocialButton icon="instagram" disabled />
  <SocialButton icon="pinterest" disabled />
  <SocialButton icon="youtube" disabled />
  <SocialButton icon="xcorp" disabled />
</StorybookComponents.Stack>;

```




    


## Common Use Case Examples


### Sharing
- description: <p>Use <a href="https://www.wix-style-react.com/storybook/?path=/story/components-overlays-modal--announcementmodallayout" data-story=AnnouncementModalLayout>&#60;AnnouncementModalLayout&#47;></a> to give enough open space to promote social sharing with <a href="https://www.wix-style-react.com/storybook/?path=/story/components-actions--socialbutton" data-story=SocialButton>&#60;SocialButton&#47;></a> actions, that are larger and more prominent than regular buttons.</p>
- example: 
```jsx 
<AnnouncementModalLayout
  title="Share Your Campaign"
  onCloseButtonClick={() => {}}
>
  <Box direction="vertical" gap="40px" margin="3px">
    <Text>
      Give more people interacting with your campaign by sharing it on your
      social networks.
    </Text>
    <Box align="space-between" verticalAlign="center">
      <SocialButton text="Share on Facebook" icon="facebook" />
      <SocialButton text="Share on Twitter" icon="twitter" />
      <SocialButton text="Share on Pinterest" icon="pinterest" />
    </Box>
    <Box>
      <Divider />
    </Box>
    <FormField label="Campaign URL">
      <Input
        suffix={
          <Box verticalAlign="middle" marginRight="SP1">
            <TextButton size="small" prefixIcon={<Icons.DuplicateSmall />}>
              {'Copy'}
            </TextButton>
          </Box>
        }
      />
    </FormField>
  </Box>
</AnnouncementModalLayout>

```


