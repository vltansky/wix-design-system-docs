
## Feature Examples


### Step
- description: <p>Define a <code>step</code> to reduce the amount of accepted values within a range. Default step is 1.</p><p></p>
- example: 
```jsx 
() => {
  const [angle, setAngle] = React.useState(0);
  const [shown, setShown] = React.useState(false);

  const handleAngleChange = (newAngle: number) => {
    setAngle(newAngle);
  };

  const props: AngleInputProps = {
    step: 90,
    value: angle,
    onChange: handleAngleChange,
  };

  return (
      <AngleInput {...props} />
  );
};
```

### Disabled
- description: <p>Disable all angle input interactions with <code>disabled</code> prop. Use it to highlight a temporary unavailable function.</p>
- example: 
```jsx 
<AngleInput disabled />
```




    


## Common Use Case Examples


### Settings panel
- description: <p>Use angle input to let users select the angle of an element drop shadow.</p>
- example: 
```jsx 
() => {
  const [angle, setAngle] = React.useState(0);
  const [shown, setShown] = React.useState(false);
  const [value, setValue] = React.useState(1);
  const [opacity, setOpacity] = React.useState(100);

  const handleAngleChange = (newAngle: number) => {
    setAngle(newAngle);
  };

  const props: AngleInputProps = {
    step: 1,
    value: angle,
    onChange: handleAngleChange,
  };

  return (
    <SidePanel maxHeight="576px" width="288px" skin="floating">
      <SidePanel.Header title="Button Design" />
      <SidePanel.Content noPadding>
        <SidePanel.Field>
          <FormField
            label="Apply shadow"
            labelPlacement="left"
            labelWidth="1fr"
          >
            <ToggleSwitch size="medium" checked />
          </FormField>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            legend="Angle"
            legendPlacement="left"
            alignment="center"
            gap="small"
            columns="auto 70px"
          >
            <Box align="right">
              <AngleInput {...props} />
            </Box>
            <NumberInput
              size="small"
              suffix={<Input.Affix>°</Input.Affix>}
              value={angle}
              hideStepper
              onChange={handleAngleChange}
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet gap="medium" legend="Distance" columns="auto 72px">
            <Slider
              onChange={setValue}
              min={0}
              max={50}
              value={value}
              displayMarks={false}
            />
            <Input
              value={value}
              size="small"
              suffix={<Input.Affix>px</Input.Affix>}
              onChange={(e) => setValue(e.target.value)}
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet gap="medium" legend="Size" columns="auto 72px">
            <Slider
              onChange={setValue}
              min={0}
              max={50}
              value={value}
              displayMarks={false}
            />
            <Input
              value={value}
              size="small"
              suffix={<Input.Affix>px</Input.Affix>}
              onChange={(e) => setValue(e.target.value)}
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet gap="medium" legend="Blur" columns="auto 72px">
            <Slider
              onChange={setValue}
              min={0}
              max={50}
              value={value}
              displayMarks={false}
            />
            <Input
              value={value}
              size="small"
              suffix={<Input.Affix>px</Input.Affix>}
              onChange={(e) => setValue(e.target.value)}
            />
          </FieldSet>
        </SidePanel.Field>
        <SidePanel.Field>
          <FieldSet
            legend="Opacity & color"
            legendSize="small"
            legendPlacement="top"
            alignment="center"
            columns="30px auto 67px"
          >
            <FillPreview fill="#000000" aspectRatio={1} />
            <Box margin="0 8px">
              <Slider
                gradientColor="#000000"
                min={0}
                max={100}
                displayMarks={false}
                onChange={(value) => setOpacity(value)}
                value={opacity}
              />
            </Box>
            <NumberInput
              value={opacity}
              min={0}
              max={100}
              onChange={(value) => setOpacity(value)}
              suffix={<Input.Affix>%</Input.Affix>}
              size="small"
              hideStepper
            />
          </FieldSet>
        </SidePanel.Field>
      </SidePanel.Content>
    </SidePanel>
  );
};

```


