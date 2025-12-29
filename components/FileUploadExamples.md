
## Feature Examples


### Basic structure
- description: <p>A trigger component must be added, so that users can open the upload dialog box. This trigger is defined as a child item of <code>FileUpload</code>.</p>
- example: 
```jsx 
<FileUpload>
  {({ openFileUploadDialog }) => (
    <Button onClick={openFileUploadDialog} prefixIcon={<Icons.UploadExport />}>
      Upload File
    </Button>
  )}
</FileUpload>;
```

### File type selection
- description: <p>Select which types of files can be uploaded with the <code>accept</code> prop. The file types are separated by a comma.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <FileUpload accept=".jpeg,.gif,.png">
    {({ openFileUploadDialog }) => (
      <Button
        prefixIcon={<Icons.UploadExport />}
        onClick={openFileUploadDialog}
      >
        Upload Image
      </Button>
    )}
  </FileUpload>
  <FileUpload accept=".doc,.pdf">
    {({ openFileUploadDialog }) => (
      <Button
        prefixIcon={<Icons.UploadExport />}
        onClick={openFileUploadDialog}
      >
        Upload Document
      </Button>
    )}
  </FileUpload>
</StorybookComponents.Stack>;
```

### Multiple files upload
- description: <p>Let users upload multiple files at once using the <code>multiple</code> prop.</p>
- example: 
```jsx 
<FileUpload multiple>
  {({ openFileUploadDialog }) => (
    <Button onClick={openFileUploadDialog} prefixIcon={<Icons.UploadExport />}>
      Upload Files
    </Button>
  )}
</FileUpload>;
```




    


## Common Use Case Examples


### Upload files
- description: <p>Any library component can be used to open an upload dialog box. Nevertheless, it's better to use buttons or viewer components that have predefined interaction states and can be accessed with the keyboard (for accessibility reasons).</p>
- example: 
```jsx 
<FileUpload multiple accept=".jpeg,.gif,.png">
  {({ openFileUploadDialog }) => (
    <AddItem
      size="large"
      subtitle="Only JPEG, GIF and PNG files up to 5 MB are supported."
      onClick={openFileUploadDialog}
    >
      Upload Media
    </AddItem>
  )}
</FileUpload>;
```

### Add images
- description: <p>To let users add images, set <code><ImageViewer/></code> as the trigger component.</p>
- example: 
```jsx 
<FileUpload multiple accept=".jpeg,.gif,.png">
  {({ openFileUploadDialog }) => (
    <ImageViewer onAddImage={openFileUploadDialog} />
  )}
</FileUpload>;
```

### Add attachments
- description: <p>Let users attach files to messages, emails or contact details with the <code><Button/></code> or <code><TextButton/></code> components.</p>
- example: 
```jsx 
() => {
  const renderAddFileButton = (
    <FileUpload multiple>
      {({ openFileUploadDialog }) => (
        <TextButton
          size="small"
          onClick={openFileUploadDialog}
          prefixIcon={<Icons.Add />}
        >
          Attach File
        </TextButton>
      )}
    </FileUpload>
  );

  return (
    <Layout>
      <Cell span={6}>
        <Card>
          <Card.Content>
            <Box direction="vertical" gap={2}>
              <Box
                width="100%"
                align="space-between"
                marginBottom={4}
                verticalAlign="middle"
              >
                <Text size="medium" secondary weight="bold">
                  Attachments
                </Text>
                {renderAddFileButton}
              </Box>
              <Box align="space-between" verticalAlign="middle">
                <Box gap={2}>
                  <Icons.Attachment />
                  <Text secondary>CV.pdf</Text>
                </Box>
                <PopoverMenu
                  textSize="small"
                  triggerElement={
                    <Tooltip content="More actions">
                      <IconButton priority="secondary" size="small">
                        <Icons.MoreSmall />
                      </IconButton>
                    </Tooltip>
                  }
                >
                  <PopoverMenu.MenuItem
                    text="Download"
                    prefixIcon={<Icons.DownloadImportSmall />}
                  />
                  <PopoverMenu.MenuItem
                    text="Delete"
                    prefixIcon={<Icons.DeleteSmall />}
                  />
                </PopoverMenu>
              </Box>
              <Box align="space-between" verticalAlign="middle">
                <Box gap={2}>
                  <Icons.Attachment />
                  <Text secondary>Contract.pdf</Text>
                </Box>
                <PopoverMenu
                  textSize="small"
                  triggerElement={
                    <Tooltip content="More actions">
                      <IconButton priority="secondary" size="small">
                        <Icons.MoreSmall />
                      </IconButton>
                    </Tooltip>
                  }
                >
                  <PopoverMenu.MenuItem
                    text="Download"
                    prefixIcon={<Icons.DownloadImportSmall />}
                  />
                  <PopoverMenu.MenuItem
                    text="Delete"
                    prefixIcon={<Icons.DeleteSmall />}
                  />
                </PopoverMenu>
              </Box>
            </Box>
          </Card.Content>
        </Card>
      </Cell>
    </Layout>
  );
};
```


