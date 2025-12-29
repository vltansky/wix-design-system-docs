
## Feature Examples


### Skin
- description: <p>Change the appearance of the card interaction with a skin prop.</p><p></p><li><code>standard</code> is the default skin for clickable card.</li><li><code>shadow</code> can be used to to highlight card from a light surface.</li><li><code>outline</code> can used when environment has too many shadows.</li><li><code>filled</code> can be use to make card even more permanent.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ClickableCard skin="standard">
    <StorybookComponents.Placeholder>Standard</StorybookComponents.Placeholder>
  </ClickableCard>
  <ClickableCard skin="shadow">
    <StorybookComponents.Placeholder>Shadow</StorybookComponents.Placeholder>
  </ClickableCard>
  <ClickableCard skin="outline">
    <StorybookComponents.Placeholder>Outline</StorybookComponents.Placeholder>
  </ClickableCard>
  <ClickableCard skin="filled">
    <StorybookComponents.Placeholder>Filled</StorybookComponents.Placeholder>
  </ClickableCard>
</StorybookComponents.Stack>;

```

### Padding
- description: <p>To remove card paddings, use <code>hasPadding</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ClickableCard hasPadding={false} skin="standard">
    <StorybookComponents.Placeholder>No paddings</StorybookComponents.Placeholder>
  </ClickableCard>
</StorybookComponents.Stack>
```

### Disabled
- description: <p>To disable a ClickableCard, use the <code>disabled</code> prop which indicates card is no longer interactive.</p>
- example: 
```jsx 
 <ClickableCard disabled>
    <StorybookComponents.Placeholder>Disabled</StorybookComponents.Placeholder>
  </ClickableCard>
```




    


## Common Use Case Examples


### App market card
- description: <p>For card in app market, do not create from scratch, reuse premade <a href="https://bo.wix.com/pages/app-market-components/?path=/story/appbox--installed">widgets</a>.</p>
- example: 
```jsx 
<Box width="294px">
  <ClickableCard skin="shadow">
    <Box gap="SP1" direction="vertical">
      <Image
        width="42"
        src="https://static.wixstatic.com/media/22e53e_a53027e61c334a428ee8fd64dd776792~mv2.png/v1/fill/w_42,h_42,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/22e53e_a53027e61c334a428ee8fd64dd776792~mv2.png"
      ></Image>
      <Text weight="bold">Wix Stores</Text>
      <Text size="small" weight="thin">
        Professional eCommerce platform to sell online
      </Text>
      <Box verticalAlign="middle" align="space-between" paddingTop="SP4">
        <Text size="tiny" secondary>
          Free to install
        </Text>
        <Box gap="3px" verticalAlign="middle">
          <div style={{ color: '#FFB700', height: '18px' }}>
            <Icons.FavoriteFilledSmall />
          </div>
          <Text size="tiny" weight="bold">
            4.2
          </Text>
          <Text secondary size="tiny">
            (335)
          </Text>
        </Box>
      </Box>
    </Box>
  </ClickableCard>
</Box>;

```


