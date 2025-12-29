
## Feature Examples


### Source
- description: <p>Pass a link to the audio file source with <code>src</code> prop. Component detects your file <code>format</code> from the extension.</p><p></p><p>In situations where extraction does not work, specify a file format with <code>format</code> prop.</p>
- example: 
```jsx 
<AudioPlayer src="AudioTrack1.mp3" />;
```

### Preload
- description: <p>Specify what to download when component is rendered with a <code>preload</code> prop. It supports 3 values:</p><li><code>auto</code> downloads the full file.</li><li><code>metadata</code> downloads the file's metadata only. The full file will be downloaded when play is clicked.</li><li><code>none</code> is used when nothing should be preloaded. The file and its data will be downloaded when the user clicks play.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AudioPlayer preload="auto" src="AudioTrack2.mp3" />
  <AudioPlayer preload="metadata" src="AudioTrack2.mp3" />
  <AudioPlayer preload="none" src="AudioTrack2.mp3" />
</StorybookComponents.Stack>;
```

### Autoplay
- description: <p>Use <code>autoplay</code> prop to start playback automatically when audio is loaded.</p>
- example: 
```jsx 
() => {
  const [src, setSrc] = React.useState(null);
  return (
    <StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="row">
        <Button onClick={() => setSrc('AudioTrack1.mp3')}>Play Audio</Button>
        <Button skin="inverted" onClick={() => setSrc(null)}>
          Stop Audio
        </Button>
      </StorybookComponents.Stack>
      {src && <AudioPlayer autoplay src={src} />}
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Form
- description: <p>Let users listen to audio files.</p>
- example: 
```jsx 
<Card>
  <Card.Header title="Track info" />
  <Card.Divider />
  <Card.Content>
    <Layout>
      <Cell span={4}>
        <FormField label="Cover image">
          <ImageViewer
            addImageInfo="Add track cover. Recommended size 3000x3000px."
            height="214px"
            tooltipProps={{
              textAlign: 'center',
            }}
          />
        </FormField>
      </Cell>
      <Cell span={8}>
        <Box gap="24px" direction="vertical">
          <FormField
            label="Track file"
            suffix={
              <TextButton prefixIcon={<Icons.Refresh />}>
                Change File
              </TextButton>
            }
          >
            <AudioPlayer src="AudioTrack1.mp3" />
          </FormField>
          <FormField label="Track name">
            <Input placeholder="e.g., Audio 1" />
          </FormField>
          <FormField label="Genre (pick up to 3)">
            <MultiSelect
              options={[
                { id: '1', value: 'Alternative' },
                { id: '2', value: 'Blues' },
                { id: '3', value: 'R&B/Soul' },
                { id: '4', value: 'Classical' },
                { id: '5', value: 'Country' },
                { id: '6', value: 'Dance' },
                { id: '7', value: 'Electronic' },
                { id: '8', value: 'Hip Hop' },
                { id: '9', value: 'Jazz' },
              ]}
              placeholder="Start typing to search the list"
            />
          </FormField>
        </Box>
      </Cell>
    </Layout>
  </Card.Content>
</Card>;
```

### Inbox
- description: <p>Use audio player to display received voice messages in the inbox. Provide an option to download a message by displaying the icon button inline to the player.</p>
- example: 
```jsx 
<Card>
  <Box verticalAlign="middle" align="space-between" padding="SP2 SP3">
    <Box gap="SP2" verticalAlign="middle">
      <Avatar name="Sam Lee" size="size30" />
      <Text>Sam Lee</Text>
    </Box>
    <Box gap="SP2">
      <IconButton skin="inverted">
        <Icons.More />
      </IconButton>
      <Button skin="inverted">Archive</Button>
    </Box>
  </Box>
  <Divider />
  <Card.Content>
    <Box
      border="1px solid"
      borderColor="D60"
      borderRadius={12}
      verticalAlign="middle"
      padding="3px SP2 3px SP1"
      width="fit-content"
      gap="6px"
      marginBottom="SP2"
    >
      <Icons.Phone />
      <Heading size="extraTiny">Missed call</Heading>
    </Box>
    <Box
      backgroundColor="D70"
      padding="SP3"
      borderRadius={12}
      width="45%"
      direction="vertical"
      gap="6px"
    >
      <Box marginBottom="SP2" direction="horizontal" verticalAlign="middle">
        <AudioPlayer src="AudioTrack1.mp3" />
        <Box marginLeft="18px">
          <IconButton size="medium" skin="inverted">
            <Icons.Download />
          </IconButton>
        </Box>
      </Box>
      <Text size="small">Message Transcript:</Text>
      <Text size="small">
        “Hey i know you are busy right now could you give me a call back whan
        you have a chance”
      </Text>
      <Box verticalAlign="middle" gap="6px" marginTop="SP1">
        <Icons.PhoneFilledSmall />
        <Text size="tiny">Voicemail</Text>
      </Box>
    </Box>
  </Card.Content>
</Card>;
```


