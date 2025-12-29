
## Feature Examples


### Size
- description: <p>Adjust the component's size using the <code>size</code> prop. It supports 3 sizes:</p><li>Use <code>large</code> to emphasize the input field.</li><li>Use <code>medium</code> for all common cases (default).</li><li>Use  <code>small</code> when the layout is dense and narrow.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ColorInput placeholder="Large" size="large" />
  <ColorInput placeholder="Medium" size="medium" />
  <ColorInput placeholder="Small" size="small" />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Indicate the component's status using the <code>status</code> prop. It has three states:</p><li>Use the <code>error</code> state to indicate an invalid value (e.g., a HEX value that doesn’t exist).</li><li>Use the <code>warning</code> state to highlight a value that can cause an unwanted result (e.g., text color is the same as the background color).</li><li>Use the <code>loading</code> state to show the value is currently being saved or validated.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <ColorInput value="#FF0000" status="error" />
  <ColorInput value="#FF0000" status="warning" />
  <ColorInput value="#FF0000" status="loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <ColorInput placeholder="See message below" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <ColorInput
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Prevent the user from using the color input field with the <code>disabled</code> prop. Use it to indicate that the field is unavailable for editing (e.g., if the element already has a pre-defined color that can't be changed). </p>
- example: 
```jsx 
() => {
  const [presets, setPresets] = React.useState([
    'midnightblue',
    'darkmagenta',
    'lightcoral',
  ]);
  return (
    <ColorInput
      value="#FF4136"
      disabled
      addTooltipContent="Add Color"
      onAddColor={color => setPresets([...presets, color])}
      colorPickerChildren={({ changeColor }) => (
        <Swatches colors={presets} onClick={changeColor} />
      )}
    />
  );
};
```

### Popover
- description: <p>Adjust the placement and behavior of the color picker popover by using any of the properties in <code>popoverProps</code>. Check the <code><Popover/></code> component API <a href="https://www.wix-style-react.com/storybook/?path=/story/components-overlays--popover"></a>for a full list.</p>
- example: 
```jsx 
<StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="6px">
    <Text size="small">Popover placement: Left</Text>
    <ColorInput
      value="#FF4136"
      popoverProps={{
        placement: 'left',
        appendTo: 'viewport',
      }}
    />
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="6px">
    <Text size="small">Animate: true</Text>
    <ColorInput
      value="#FF4136"
      popoverProps={{
        animate: true,
      }}
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Add color presets
- description: <p>Allow users to add new color presets inside the color picker by clicking an "Add color" button. Use a combination of the <code>colorPickerChildren</code> and the <code>onAddColor</code> properties to add this ability.</p>
- example: 
```jsx 
() => {
  const [presets, setPresets] = React.useState([
    'midnightblue',
    'darkmagenta',
    'lightcoral',
  ]);
  return (
    <ColorInput
      value="#FF4136"
      addTooltipContent="Add Color"
      onAddColor={color => setPresets([...presets, color])}
      colorPickerChildren={({ changeColor }) => (
        <Swatches colors={presets} onClick={changeColor} />
      )}
    />
  );
};
```




    


## Common Use Case Examples


### Custom text color
- description: <p>Use color input in a variety of composers to define custom colors for text, background fills, icons, etc.</p>
- example: 
```jsx 
() => {
  const [color, setColor] = React.useState('#000000');
  const [alignment, setAlignment] = React.useState(0);
  const [text, setText] = React.useState('Luna Boutique');

  return (
    <SidePanel>
      <SidePanel.Header title="Customise text"></SidePanel.Header>
      <SidePanel.Content>
        <Box direction="vertical" gap="30px">
          <Text size="small" secondary>
            Change the font, color and more to make your text stand out.
          </Text>
          <FormField label="Edit text">
            <Input value={text} onChange={e => setText(e.target.value)} />
          </FormField>
          <FormField label="Font">
            <Box gap="6px">
              <Text weight="bold">Playfair Display - 700</Text>
              <Button size="tiny" priority="secondary">
                Change Font
              </Button>
            </Box>
          </FormField>
          <FormField label="Alignment">
            <Box gap="6px">
              <ToggleButton
                labelValue="Left"
                selected={alignment === 0}
                onClick={() => setAlignment(0)}
              >
                <Icons.TextAlignLeft />
              </ToggleButton>
              <ToggleButton
                labelValue="Center"
                selected={alignment === 1}
                onClick={() => setAlignment(1)}
              >
                <Icons.TextAlignCenter />
              </ToggleButton>
              <ToggleButton
                labelValue="Right"
                selected={alignment === 2}
                onClick={() => setAlignment(2)}
              >
                <Icons.TextAlignRight />
              </ToggleButton>
            </Box>
          </FormField>
          <FormField label="Text color">
            <ColorInput
              value={color}
              onChange={setColor}
              popoverAppendTo="viewport"
            />
          </FormField>
        </Box>
      </SidePanel.Content>
      <SidePanel.Footer>
        <Box align="right" gap="12px">
          <Button size="small" priority="secondary">
            Discard Changes
          </Button>
          <Button size="small">Save</Button>
        </Box>
      </SidePanel.Footer>
    </SidePanel>
  );
};
```


