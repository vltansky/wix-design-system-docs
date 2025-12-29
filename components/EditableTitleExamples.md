
## Feature Examples


### Max length
- description: <p>Define a max number of characters that users can write in the title with <code>maxLength</code> prop.</p><p></p><p><code>maxLength</code> includes spaces and has no default value.</p>
- example: 
```jsx 
<EditableTitle initialValue="I can only write 24 char" maxLength={24} />;
```

### Auto focus
- description: <p>Make the component ready to type in as soon as it is rendered (on mount) with <code>autoFocus</code> prop.</p>
- example: 
```jsx 
<EditableTitle initialValue="Start writing now" autoFocus />;
```

### Value
- description: <p>Control title text value with these props:</p><li><code>defaultValue</code> - use it to display a placeholder text. It will become a title if users do not change it.</li><li><code>initialValue</code> - use it to suggest a fitting opening title for users. They can delete and change it themselves.</li><li><code>value</code> - use it to specify the current value of the title.</li><p></p><p>Note that when users delete the <code>initialValue</code>, <code>defaultValue</code> is still shown.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <EditableTitle defaultValue="Default Value" />
  <EditableTitle initialValue="Initial Value" />
  <EditableTitle value="value" />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### Giving a name for a newly created item
- description: <p>Use Editable title in the <code><Page.Header/></code> when users create a new item with no default name (e.g., a product for the Store).</p><p></p><p>Editable title can work in sync with Form components (e.g., writing 'Green Shoes' in the 'Name' field will automatically change the page title, too).</p>
- example: 
```jsx 
() => {
  const [productName, setProductName] = React.useState('');

  return (
    <Page height="60vh">
      <Page.Header
        title=<EditableTitle
          defaultValue="Untitled Product"
          value={productName}
        />
        actionsBar={
          <Box gap="SP2">
            <Button skin="inverted">Cancel</Button>
            <Button>Save</Button>
          </Box>
        }
        breadcrumbs={
          <Breadcrumbs
            activeId="2"
            items={[
              { id: '1', value: 'Products' },
              { id: '2', value: 'Untitled Product' },
            ]}
          />
        }
      />
      <Page.Content>
        <Layout>
          <Cell span={8}>
            <Card>
              <Card.Header title="Product info" />
              <Card.Divider />
              <Card.Content>
                <Layout>
                  <Cell span={6}>
                    <FormField label="Name">
                      <Input
                        value={productName}
                        onChange={(e) => setProductName(e.target.value)}
                        placeholder="Add a product name"
                      />
                    </FormField>
                  </Cell>
                  <Cell span={6}>
                    <FormField label="Price">
                      <Input prefix={<Input.Affix>$</Input.Affix>} />
                    </FormField>
                  </Cell>
                  <Cell span={12}>
                    <FormField label="Description">
                      <RichTextInputArea minHeight="114px" maxHeight="114px" />
                    </FormField>
                  </Cell>
                </Layout>
              </Card.Content>
            </Card>
          </Cell>
        </Layout>
      </Page.Content>
    </Page>
  );
};
```


