
## Feature Examples


### Structure
- description: <p>This component consists of 2 elements:</p><li>Use <code><Dropzone.Content/></code> to define the initial dropzone area’s content.</li><li>Use <code><Dropzone.Overlay/></code> to define what's shown to the user when a file is dragged into the dropzone.</li>
- example: 
```jsx 
<StorybookComponents.Placeholder>
  <Dropzone>
    <Dropzone.Overlay>
      <StorybookComponents.Background skin="blue">
        <StorybookComponents.Stack
          height="300px"
          alignItems="center"
          justifyContent="center"
          width="100%"
        >
          Release on this Overlay to upload
        </StorybookComponents.Stack>
      </StorybookComponents.Background>
    </Dropzone.Overlay>
    <Dropzone.Content>
      <StorybookComponents.Stack
        height="300px"
        alignItems="center"
        justifyContent="center"
      >
        Drag file to this Dropzone
      </StorybookComponents.Stack>
    </Dropzone.Content>
  </Dropzone>
</StorybookComponents.Placeholder>;
```




    


## Common Use Case Examples


### Add item
- description: <p>Use a dropzone to upload multiple items to a designated area. </p><p></p><p>Include a dropzone to let users drag and drop multiple files to upload. For example, adding photos to an album or importing data from a CSV file. </p>
- example: 
```jsx 
<Card>
  <Card.Header
    title={
      <Stepper
        activeStep={1}
        steps={[
          { text: 'Prepare', type: 'completed' },
          { text: 'Upload' },
          { text: 'Match', type: 'disabled' },
          { text: 'Label', type: 'disabled' },
        ]}
      />
    }
  />
  <Card.Divider />
  <Card.Content>
    <Layout gap="24px">
      <Cell>
        <Dropzone onDrop={() => {}}>
          <Dropzone.Overlay>
            <Box
              direction="vertical"
              height="100%"
              boxSizing="border-box"
              border="dashed 1px"
              borderRadius="6px"
              borderColor="B20"
            >
              <AddItem theme="filled" size="large">
                Drop your images here
              </AddItem>
            </Box>
          </Dropzone.Overlay>
          <Dropzone.Content>
            <Box
              direction="vertical"
              border="dashed 1px"
              boxSizing="border-box"
              borderRadius="6px"
              padding="42px"
              borderColor="B20"
            >
              <EmptyState
                title="Drag your images here"
                subtitle="Or upload images from your computer"
                image="generic_add_item_illustration.svg"
              >
                <FileUpload>
                  {({ openFileUploadDialog }) => (
                    <TextButton
                      onClick={openFileUploadDialog}
                      prefixIcon={<Icons.Upload />}
                    >
                      Upload Images
                    </TextButton>
                  )}
                </FileUpload>
              </EmptyState>
            </Box>
          </Dropzone.Content>
        </Dropzone>
      </Cell>
      <Cell>
        <Box width="100%" align="space-between">
          <Button
            size="small"
            priority="secondary"
            prefixIcon={<Icons.ChevronLeftSmall />}
          >
            Back
          </Button>
          <Button size="small">
            Next
          </Button>
        </Box>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;
```


