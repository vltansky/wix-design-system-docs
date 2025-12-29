
## Feature Examples


### Structure
- description: <p>Component consists of 4 content areas:</p><li><code>siteName</code> - shows the title of a page at the top of the widget.</li><li><code>previewUrl</code> - shows the URL preview at the top of the widget.</li><li><code>title</code> - shows the title of the page and its keywords, as set in the SEO settings.</li><li><code>description</code> - shows a short description for the page, as set in the SEO settings (optional).</li>
- example: 
```jsx 
<GooglePreview
  siteName="Site name"
  title="Title"
  previewUrl="Preview URL"
  description="Description"
/>;
```

### Skin
- description: <p>Change the background of the widget with <code>skin</code> prop:</p><li><code>light</code> (default) sets the background to white with gray 1 px border.</li><li><code>transparent</code> removes the background color and border.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <GooglePreview
    siteName="Site Name"
    title="Title | <GooglePreview/> in light (default) background"
    previewUrl="www.site-name.com"
    description="A short description for a site"
    skin="light"
  />
  <GooglePreview
    siteName="Site Name"
    title="Title | <GooglePreview/> in transparent background"
    previewUrl="www.site-name.com"
    description="A short description for a site"
    skin="transparent"
  />
</StorybookComponents.Stack>;
```

### Title
- description: <p>Limit the number of lines the <code>title</code> can take with <code>titleMaxLines</code> prop.</p><p></p><p>The default <code>titleMaxLines</code> value is 1.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <GooglePreview
    siteName="Site Name"
    title="Site Name | This is a single line title"
    previewUrl="www.site-name.com"
    description="A short description for a site"
  />
  <GooglePreview
    siteName="Site Name"
    title="Site Name | This is an especially long website title that does not fit in one line and gets truncated"
    previewUrl="www.site-name.com"
    description="A short description for a site"
  />
  <GooglePreview
    siteName="Site Name"
    title="Site Name | This is an especially long website title that does not fit in one line. However, titleMaxlines prop is set to 2, so the title wraps into two lines"
    previewUrl="www.site-name.com"
    description="A short description for a site"
    titleMaxLines={2}
  />
</StorybookComponents.Stack>;
```

### Description
- description: <p>Use <code>description</code> to provide more context about a site.</p><p></p><p>Truncate the description after a certain number of lines with <code>descriptionMaxLines</code> prop.</p><p></p><p>The default <code>descriptionMaxLines</code> value is 2.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <GooglePreview
    siteName="Site Name"
    title="Site Name | a title of your site"
    previewUrl="www.site-name.com"
    description="A short description for a site containing all the relevant keywords that get your website great results in search engines."
  />
  <GooglePreview
    siteName="Site Name"
    title="Site Name | a title of your site"
    previewUrl="www.site-name.com"
    description="This is a long description for a site containing all the relevant keywords that get your website great results in search engines. If the description is longer than 2 lines, by default it gets truncated by ellipses at the end of the second line. This is an example how the end of this sentence will not be visible, since it will get truncated by ellipses."
  />
  <GooglePreview
    siteName="Site Name"
    title="Site Name | Preview without description"
    previewUrl="www.site-name.com"
  />
</StorybookComponents.Stack>;
```




    


## Common Use Case Examples


### SEO settings panel
- description: <p>Use Google preview to visualise SEO settings impact on user website appearance in Google search results.</p>
- example: 
```jsx 
() => {
  const [title, setTitle] = React.useState(
    'Logo maker | Create Your Own Free Logo Design | Wix.com',
  );
  const [siteName, setSiteName] = React.useState('Wix Logo Maker');
  const [description, setDescription] = React.useState(
    'With Wix Logo Maker, you can design a logo that looks exactly the way you want. Each logo is completely customizable - change the font, color, size.',
  );
  const [urlSlug, setUrlSlug] = React.useState('/logo-maker');
  const [indexablePage, setIndexablePage] = React.useState(false);

  return (
    <Card>
      <Card.Header title="Get found on Google" />
      <Card.Divider />
      <Card.Content>
        <Layout>
          <Cell span={6}>
            <Layout>
              <Cell>
                <FormField label="Site name">
                  <Input
                    placeholder="/your-URL-slug"
                    value={siteName}
                    onChange={(e) => setSiteName(e.target.value)}
                  />
                </FormField>
              </Cell>
              <Cell>
                <FormField label="URL slug">
                  <Input
                    placeholder="/your-URL-slug"
                    value={urlSlug}
                    onChange={(e) => setUrlSlug(e.target.value)}
                  />
                </FormField>
              </Cell>
              <Cell>
                <FormField label="Page title tag">
                  <InputArea
                    placeholder="Add your title tag here..."
                    value={title}
                    onChange={(e) => setTitle(e.target.value)}
                  />
                </FormField>
              </Cell>
              <Cell>
                <FormField label="Page meta description">
                  <InputArea
                    autoGrow
                    maxLength={200}
                    placeholder="Write 2 to 3 sentences describing what your site has to offer..."
                    value={description}
                    onChange={(e) => setDescription(e.target.value)}
                  />
                </FormField>
              </Cell>
              <Cell>
                <Box>
                  <FormField
                    label="Let search engines index this page"
                    labelPlacement="right"
                    stretchContent={false}
                    infoContent="Get listed with Google Search so potential customers can find you in online results"
                  >
                    <ToggleSwitch
                      checked={indexablePage}
                      onChange={() => setIndexablePage(!indexablePage)}
                    />
                  </FormField>
                </Box>
              </Cell>
            </Layout>
          </Cell>
          <Cell span={6}>
            <FormField label="Preview on Google">
              <GooglePreview
                siteName={siteName}
                title={title}
                previewUrl={'www.wix.com' + urlSlug}
                description={description}
                descriptionMaxLines="1"
              />
            </FormField>
          </Cell>
        </Layout>
      </Card.Content>
    </Card>
  );
};
```


