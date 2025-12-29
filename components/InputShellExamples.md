
## Feature Examples


### Size
- description: <p>Adjust the size of the input using the <code>size</code> prop. It supports 3 sizes:</p><li>For most common cases, use the default <code>medium.</code></li><li>To emphasize specific inputs in onboarding flows, use <code>large</code>.</li><li>Use <code>small</code> for more dense and compact layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputShell size="large" placeholder="Large" />
  <InputShell size="medium" placeholder="Medium" />
  <InputShell size="small" placeholder="Small" />
</StorybookComponents.Stack>;
```

### Menu arrow
- description: <p>Use <code>menuArrow</code> prop to change InputShell to look like a Dropdown.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputShell placeholder="No dropdown arrow" />
  <InputShell placeholder="With drodown arrow" menuArrow />
</StorybookComponents.Stack>

```

### Disabled
- description: <p><code>disabled</code> removes all interactions and creates a disabled input state. Use it to highlight functions that are unavailable.</p>
- example: 
```jsx 
<InputShell disabled={true}>Disabled</InputShell>;
```

### Render as
- description: <p><InputShell /> can be rendered as <code>div</code> or as <code>button</code></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <InputShell
    as="div"
    placeholder="Rendered as div"
    dataHook="as-div-example"
  />
  <InputShell
    as="button"
    placeholder="Rendered as button"
    dataHook="as-button-example"
  />
</StorybookComponents.Stack>

```




    


## Common Use Case Examples


### Border style
- description: <p>To show border style in the dropdown you can use <InputShell /> as a <code>div</code> and use css or even an svg to create such designs.</p>
- example: 
```jsx 
() => {
  const [opacity, setOpacity] = React.useState(50);

  return (
    <SidePanel onCloseButtonClick skin="floating" width="288px">
      <SidePanel.Header title="Design" />
      <SidePanel.Content>
        <FieldSet
          suffix={
            <ToggleButton labelValue="Small" size="tiny">
              <Icons.AdjustSmall />
            </ToggleButton>
          }
          legend="Borders"
          legendSize="small"
          legendPlacement="top"
          alignment="center"
          columns="32px auto 120px"
        >
          <div style={{ height: '32px' }}>
            <FillPreview fill="#000000" aspectRatio={1} />{' '}
          </div>
          <NumberInput
            value={opacity}
            min={0}
            max={10}
            onChange={(value) => setOpacity(value)}
            suffix={<Input.Affix>px</Input.Affix>}
            hideStepper
          />
          <InputShell menuArrow>
            <div
              style={{
                height: '20px',
                width: '80px',
                alignItems: 'center',
                justifyContent: 'center',
              }}
            >
              <div
                style={{
                  height: '10px',
                  borderBottom: '2px solid black',
                }}
              ></div>
            </div>
          </InputShell>
        </FieldSet>
      </SidePanel.Content>
    </SidePanel>
  );
};

```


