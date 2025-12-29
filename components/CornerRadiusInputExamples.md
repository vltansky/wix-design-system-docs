
## Feature Examples


### Size
- description: <p>Adjust the size of the input using the <code>size</code> prop. It supports 3 sizes:</p><li>Use <code>large</code> to emphasize input.</li><li>Use <code>medium</code> (default) for most common cases.</li><li>Use <code>small</code> for more dense and compact layouts.</li>
- example: 
```jsx 
() => {
  const [topLeft, setTopLeft] = React.useState(0);
  const [topRight, setTopRight] = React.useState(0);
  const [bottomLeft, setBottomLeft] = React.useState(0);
  const [bottomRight, setBottomRight] = React.useState(0);

  const [topLeftInvalid, setTopLeftInvalid] = React.useState(false);
  const [topRightInvalid, setTopRightInvalid] = React.useState(false);
  const [bottomLeftInvalid, setBottomLeftInvalid] = React.useState(false);
  const [bottomRightInvalid, setBottomRightInvalid] = React.useState(false);

  return (
    <StorybookComponents.Stack flexDirection="column" width="300px">
      <CornerRadiusInput
        size="large"
        linkingButtonLabels={{
          pressed: 'Edit individually',
          unpressed: 'Apply to all corners',
        }}
        topLeft={{
          value: topLeft,
          ariaLabel: 'Top left corner',
          onChange: (e) => {
            setTopLeftInvalid(false);
            setTopLeft(e);
          },
        }}
        topRight={{
          value: topRight,
          ariaLabel: 'Top right corner',
          onChange: (e) => {
            setTopRightInvalid(false);
            setTopRight(e);
          },
        }}
        bottomLeft={{
          value: bottomLeft,
          ariaLabel: 'Bottom left corner',
          onChange: (e) => {
            setBottomLeftInvalid(false);
            setBottomLeft(e);
          },
        }}
        bottomRight={{
          value: bottomRight,
          ariaLabel: 'Bottom right corner',
          onChange: (e) => {
            setBottomRightInvalid(false);
            setBottomRight(e);
          },
        }}
      />
      <CornerRadiusInput
        size="medium"
        linkingButtonLabels={{
          pressed: 'Edit indivually',
          unpressed: 'Apply to all corners',
        }}
        topLeft={{
          value: topLeft,
          ariaLabel: 'Top left corner',
          onChange: (e) => {
            setTopLeftInvalid(false);
            setTopLeft(e);
          },
        }}
        topRight={{
          value: topRight,
          ariaLabel: 'Top right corner',
          onChange: (e) => {
            setTopRightInvalid(false);
            setTopRight(e);
          },
        }}
        bottomLeft={{
          value: bottomLeft,
          ariaLabel: 'Bottom left corner',
          onChange: (e) => {
            setBottomLeftInvalid(false);
            setBottomLeft(e);
          },
        }}
        bottomRight={{
          value: bottomRight,
          ariaLabel: 'Bottom right corner',
          onChange: (e) => {
            setBottomRightInvalid(false);
            setBottomRight(e);
          },
        }}
      />
      <CornerRadiusInput
        size="small"
        linkingButtonLabels={{
          pressed: 'Edit indivually',
          unpressed: 'Apply to all corners',
        }}
        topLeft={{
          value: topLeft,
          ariaLabel: 'Top left corner',
          onChange: (e) => {
            setTopLeftInvalid(false);
            setTopLeft(e);
          },
        }}
        topRight={{
          value: topRight,
          ariaLabel: 'Top right corner',
          onChange: (e) => {
            setTopRightInvalid(false);
            setTopRight(e);
          },
        }}
        bottomLeft={{
          value: bottomLeft,
          ariaLabel: 'Bottom left corner',
          onChange: (e) => {
            setBottomLeftInvalid(false);
            setBottomLeft(e);
          },
        }}
        bottomRight={{
          value: bottomRight,
          ariaLabel: 'Bottom right corner',
          onChange: (e) => {
            setBottomRightInvalid(false);
            setBottomRight(e);
          },
        }}
      />
    </StorybookComponents.Stack>
  );
};
```

### Status
- description: <p>Below the input, include text explaining the status.</p><p></p><p>To add an inline error message wrap the component in a <code><FieldSet/></code> and add the <code>statusMessage</code> to it.</p>
- example: 
```jsx 
() => {
  const [topLeft, setTopLeft] = React.useState(0);
  const [topRight, setTopRight] = React.useState(0);
  const [bottomLeft, setBottomLeft] = React.useState(0);
  const [bottomRight, setBottomRight] = React.useState(0);

  const [topLeftInvalid, setTopLeftInvalid] = React.useState(false);
  const [topRightInvalid, setTopRightInvalid] = React.useState(false);
  const [bottomLeftInvalid, setBottomLeftInvalid] = React.useState(false);
  const [bottomRightInvalid, setBottomRightInvalid] = React.useState(false);

  return (
    <StorybookComponents.Stack flexDirection="column" width="300px">
      <FieldSet
        legend="Corner radius"
        status="error"
        statusMessage="This is an error message."
      >
        <CornerRadiusInput
          linkingButtonLabels={{
            pressed: 'Edit individually',
            unpressed: 'Apply to all corners',
          }}
          topLeft={{
            value: topLeft,
            ariaLabel: 'Top left corner',
            status: 'error',
            onChange: (e) => {
              setTopLeftInvalid(false);
              setTopLeft(e);
            },
          }}
          topRight={{
            value: topRight,
            ariaLabel: 'Top right corner',
            status: 'error',
            onChange: (e) => {
              setTopRightInvalid(false);
              setTopRight(e);
            },
          }}
          bottomLeft={{
            value: bottomLeft,
            ariaLabel: 'Bottom left corner',
            status: 'error',
            onChange: (e) => {
              setBottomLeftInvalid(false);
              setBottomLeft(e);
            },
          }}
          bottomRight={{
            value: bottomRight,
            ariaLabel: 'Bottom right corner',
            status: 'error',
            onChange: (e) => {
              setBottomRightInvalid(false);
              setBottomRight(e);
            },
          }}
        />
      </FieldSet>
      <FieldSet
        legend="Corner radius"
        status="warning"
        statusMessage="This is a warning message."
      >
        <CornerRadiusInput
          linkingButtonLabels={{
            pressed: 'Edit individually',
            unpressed: 'Apply to all corners',
          }}
          topLeft={{
            value: topLeft,
            ariaLabel: 'Top left corner',
            status: 'warning',
            onChange: (e) => {
              setTopLeftInvalid(false);
              setTopLeft(e);
            },
          }}
          topRight={{
            value: topRight,
            ariaLabel: 'Top right corner',
            status: 'warning',
            onChange: (e) => {
              setTopRightInvalid(false);
              setTopRight(e);
            },
          }}
          bottomLeft={{
            value: bottomLeft,
            ariaLabel: 'Bottom left corner',
            status: 'warning',
            onChange: (e) => {
              setBottomLeftInvalid(false);
              setBottomLeft(e);
            },
          }}
          bottomRight={{
            value: bottomRight,
            ariaLabel: 'Bottom right corner',
            status: 'warning',
            onChange: (e) => {
              setBottomRightInvalid(false);
              setBottomRight(e);
            },
          }}
        />
      </FieldSet>
    </StorybookComponents.Stack>
  );
};
```

### Edit mode
- description: <p>Corners can be adjusted individually or collectively by toggling between the  "Edit individually" and "Apply to all corners" options in the lock and unlock toggle.</p>
- example: 
```jsx 
() => {
  const [topLeft, setTopLeft] = React.useState(0);
  const [topRight, setTopRight] = React.useState(0);
  const [bottomLeft, setBottomLeft] = React.useState(0);
  const [bottomRight, setBottomRight] = React.useState(0);

  const [topLeftInvalid, setTopLeftInvalid] = React.useState(false);
  const [topRightInvalid, setTopRightInvalid] = React.useState(false);
  const [bottomLeftInvalid, setBottomLeftInvalid] = React.useState(false);
  const [bottomRightInvalid, setBottomRightInvalid] = React.useState(false);

  return (
    <StorybookComponents.Stack flexDirection="column" width="300px">
      <CornerRadiusInput
        linked
        linkingButtonLabels={{
          pressed: 'Edit individually',
          unpressed: 'Apply to all corners',
        }}
        topLeft={{
          value: topLeft,
          ariaLabel: 'Top left corner',
          onChange: (e) => {
            setTopLeftInvalid(false);
            setTopLeft(e);
          },
        }}
        topRight={{
          value: topRight,
          ariaLabel: 'Top right corner',
          onChange: (e) => {
            setTopRightInvalid(false);
            setTopRight(e);
          },
        }}
        bottomLeft={{
          value: bottomLeft,
          ariaLabel: 'Bottom left corner',
          onChange: (e) => {
            setBottomLeftInvalid(false);
            setBottomLeft(e);
          },
        }}
        bottomRight={{
          value: bottomRight,
          ariaLabel: 'Bottom right corner',
          onChange: (e) => {
            setBottomRightInvalid(false);
            setBottomRight(e);
          },
        }}
      />
    </StorybookComponents.Stack>
  );
};
```

### Suffix
- description: <p>Specify the unit used to adjust corner radius of an element using <code>suffix</code>. The default unit is pixels (px).</p><p></p><p></p><p></p><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" width="300px">
  <CornerRadiusInput
    linkingButtonLabels={{
      pressed: 'Edit individually',
      unpressed: 'Apply to all corners',
    }}
    topLeft={{
      ariaLabel: 'Top left corner',
      value: 0,
    }}
    topRight={{
      ariaLabel: 'Top right corner',
      value: 0,
    }}
    bottomLeft={{
      ariaLabel: 'Bottom left corner',
      value: 0,
    }}
    bottomRight={{
      ariaLabel: 'Bottom right corner',
      value: 0,
    }}
  />
  <CornerRadiusInput
    linkingButtonLabels={{
      pressed: 'Edit individually',
      unpressed: 'Apply to all corners',
    }}
    topLeft={{
      ariaLabel: 'Top left corner',
      value: 0,
      suffix: '%',
    }}
    topRight={{
      ariaLabel: 'Top right corner',
      value: 0,
      suffix: '%',
    }}
    bottomLeft={{
      ariaLabel: 'Bottom left corner',
      value: 0,
      suffix: '%',
    }}
    bottomRight={{
      ariaLabel: 'Bottom right corner',
      value: 0,
      suffix: '%',
    }}
  />
  <CornerRadiusInput
    linkingButtonLabels={{
      pressed: 'Edit individually',
      unpressed: 'Apply to all corners',
    }}
    topLeft={{
      ariaLabel: 'Top left corner',
      value: 0,
      suffix: (
        <DropdownBase
          selectedId={0}
          focusOnSelectedOption
          dynamicWidth
          options={[
            { id: 0, value: 'px' },
            { id: 1, value: '%' },
          ]}
        >
          {({ toggle, selectedOption = {} }) => (
            <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
          )}
        </DropdownBase>
      ),
    }}
    topRight={{
      ariaLabel: 'Top right corner',
      value: 0,
      suffix: (
        <DropdownBase
          selectedId={0}
          focusOnSelectedOption
          dynamicWidth
          options={[
            { id: 0, value: 'px' },
            { id: 1, value: '%' },
          ]}
        >
          {({ toggle, selectedOption = {} }) => (
            <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
          )}
        </DropdownBase>
      ),
    }}
    bottomLeft={{
      ariaLabel: 'Bottom left corner',
      value: 0,
      suffix: (
        <DropdownBase
          selectedId={0}
          focusOnSelectedOption
          dynamicWidth
          options={[
            { id: 0, value: 'px' },
            { id: 1, value: '%' },
          ]}
        >
          {({ toggle, selectedOption = {} }) => (
            <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
          )}
        </DropdownBase>
      ),
    }}
    bottomRight={{
      ariaLabel: 'Bottom right corner',
      value: 0,
      suffix: (
        <DropdownBase
          selectedId={0}
          focusOnSelectedOption
          dynamicWidth
          options={[
            { id: 0, value: 'px' },
            { id: 1, value: '%' },
          ]}
        >
          {({ toggle, selectedOption = {} }) => (
            <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
          )}
        </DropdownBase>
      ),
    }}
  />
</StorybookComponents.Stack>;
```

### Min and max values
- description: <p>Define the range of the corner radius values using <code>min</code> and <code>max</code>.</p>
- example: 
```jsx 
() => {
  const [topLeft, setTopLeft] = React.useState(0);
  const [topRight, setTopRight] = React.useState(0);
  const [bottomLeft, setBottomLeft] = React.useState(0);
  const [bottomRight, setBottomRight] = React.useState(0);

  const [topLeftInvalid, setTopLeftInvalid] = React.useState(false);
  const [topRightInvalid, setTopRightInvalid] = React.useState(false);
  const [bottomLeftInvalid, setBottomLeftInvalid] = React.useState(false);
  const [bottomRightInvalid, setBottomRightInvalid] = React.useState(false);

  return (
    <StorybookComponents.Stack flexDirection="column" width="300px">
      <FieldSet
        legend="Corner radius"
        status={
          ((topLeftInvalid ||
            topRightInvalid ||
            bottomLeftInvalid ||
            bottomRightInvalid) &&
            'error') ||
          undefined
        }
        statusMessage={
          ((topLeftInvalid ||
            topRightInvalid ||
            bottomLeftInvalid ||
            bottomRightInvalid) &&
            'Enter a number between 0 and 10.') ||
          'Type a number less than 0 or more than 10.'
        }
        statusId="corner-radius-error"
      >
        <CornerRadiusInput
          linkingButtonLabels={{
            pressed: 'Edit individually',
            unpressed: 'Apply to all corners',
          }}
          min={0}
          max={10}
          statusId="corner-radius-error"
          topLeft={{
            value: topLeft,
            ariaLabel: 'Top left corner',
            status: (topLeftInvalid && 'error') || undefined,
            onChange: (e) => {
              setTopLeftInvalid(false);
              setTopLeft(e);
            },
            onInvalid: (e) => {
              setTopLeft(e);
              setTopLeftInvalid(true);
            },
          }}
          topRight={{
            value: topRight,
            ariaLabel: 'Top right corner',
            status: (topRightInvalid && 'error') || undefined,
            onChange: (e) => {
              setTopRightInvalid(false);
              setTopRight(e);
            },
            onInvalid: (e) => {
              setTopRight(e);
              setTopRightInvalid(true);
            },
          }}
          bottomLeft={{
            value: bottomLeft,
            ariaLabel: 'Bottom left corner',
            status: (bottomLeftInvalid && 'error') || undefined,
            onChange: (e) => {
              setBottomLeftInvalid(false);
              setBottomLeft(e);
            },
            onInvalid: (e) => {
              setBottomLeft(e);
              setBottomLeftInvalid(true);
            },
          }}
          bottomRight={{
            value: bottomRight,
            ariaLabel: 'Bottom right corner',
            status: (bottomRightInvalid && 'error') || undefined,
            onChange: (e) => {
              setBottomRightInvalid(false);
              setBottomRight(e);
            },
            onInvalid: (e) => {
              setBottomRight(e);
              setBottomRightInvalid(true);
            },
          }}
        />
      </FieldSet>
    </StorybookComponents.Stack>
  );
};
```

### Invalid value
- description: <p>Use <code>onInvalid</code> callback function to notify users when they enter invalid inputs.  Explain why it's invalid using the <code>statusMessage</code> prop of a <code><FieldSet/></code>.</p>
- example: 
```jsx 
() => {
  const [topLeft, setTopLeft] = React.useState(100);
  const [topRight, setTopRight] = React.useState(100);
  const [bottomLeft, setBottomLeft] = React.useState(100);
  const [bottomRight, setBottomRight] = React.useState(100);

  const [topLeftInvalid, setTopLeftInvalid] = React.useState(false);
  const [topRightInvalid, setTopRightInvalid] = React.useState(false);
  const [bottomLeftInvalid, setBottomLeftInvalid] = React.useState(false);
  const [bottomRightInvalid, setBottomRightInvalid] = React.useState(false);

  return (
    <StorybookComponents.Stack flexDirection="column" width="300px">
      <FieldSet
        legend="Corner radius"
        status={
          ((topLeftInvalid ||
            topRightInvalid ||
            bottomLeftInvalid ||
            bottomRightInvalid) &&
            'error') ||
          undefined
        }
        statusMessage={
          ((topLeftInvalid ||
            topRightInvalid ||
            bottomLeftInvalid ||
            bottomRightInvalid) &&
            'Enter a number between 0 and 10.') ||
          'Type a number less than 0 or more than 10.'
        }
        statusId="corner-radius-error"
      >
        <CornerRadiusInput
          linkingButtonLabels={{
            pressed: 'Edit individually',
            unpressed: 'Apply to all corners',
          }}
          min={0}
          max={10}
          statusId="corner-radius-error"
          topLeft={{
            value: topLeft,
            ariaLabel: 'Top left corner',
            status: (topLeftInvalid && 'error') || undefined,
            onChange: (e) => {
              setTopLeftInvalid(false);
              setTopLeft(e);
            },
            onInvalid: (e) => {
              setTopLeft(e);
              setTopLeftInvalid(true);
            },
          }}
          topRight={{
            value: topRight,
            ariaLabel: 'Top right corner',
            status: (topRightInvalid && 'error') || undefined,
            onChange: (e) => {
              setTopRightInvalid(false);
              setTopRight(e);
            },
            onInvalid: (e) => {
              setTopRight(e);
              setTopRightInvalid(true);
            },
          }}
          bottomLeft={{
            value: bottomLeft,
            ariaLabel: 'Bottom left corner',
            status: (bottomLeftInvalid && 'error') || undefined,
            onChange: (e) => {
              setBottomLeftInvalid(false);
              setBottomLeft(e);
            },
            onInvalid: (e) => {
              setBottomLeft(e);
              setBottomLeftInvalid(true);
            },
          }}
          bottomRight={{
            value: bottomRight,
            ariaLabel: 'Bottom right corner',
            status: (bottomRightInvalid && 'error') || undefined,
            onChange: (e) => {
              setBottomRightInvalid(false);
              setBottomRight(e);
            },
            onInvalid: (e) => {
              setBottomRight(e);
              setBottomRightInvalid(true);
            },
          }}
        />
      </FieldSet>
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Change units
- description: <p>Allow users to change units of corner radius by adding dropdown selection to the suffix area.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" width="300px">
  <FieldSet legend="Corner radius">
    <CornerRadiusInput
      linkingButtonLabels={{
        pressed: 'Edit individually',
        unpressed: 'Apply to all corners',
      }}
      topLeft={{
        ariaLabel: 'Top left corner',
        value: 0,
        suffix: (
          <DropdownBase
            selectedId={1}
            focusOnSelectedOption
            dynamicWidth
            options={[
              { id: 0, value: 'px' },
              { id: 1, value: '%' },
            ]}
          >
            {({ toggle, selectedOption = {} }) => (
              <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
            )}
          </DropdownBase>
        ),
      }}
      topRight={{
        ariaLabel: 'Top right corner',
        value: 0,
        suffix: (
          <DropdownBase
            selectedId={1}
            focusOnSelectedOption
            dynamicWidth
            options={[
              { id: 0, value: 'px' },
              { id: 1, value: '%' },
            ]}
          >
            {({ toggle, selectedOption = {} }) => (
              <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
            )}
          </DropdownBase>
        ),
      }}
      bottomLeft={{
        ariaLabel: 'Bottom left corner',
        value: 0,
        suffix: (
          <DropdownBase
            selectedId={1}
            focusOnSelectedOption
            dynamicWidth
            options={[
              { id: 0, value: 'px' },
              { id: 1, value: '%' },
            ]}
          >
            {({ toggle, selectedOption = {} }) => (
              <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
            )}
          </DropdownBase>
        ),
      }}
      bottomRight={{
        ariaLabel: 'Bottom right corner',
        value: 0,
        suffix: (
          <DropdownBase
            selectedId={1}
            focusOnSelectedOption
            dynamicWidth
            options={[
              { id: 0, value: 'px' },
              { id: 1, value: '%' },
            ]}
          >
            {({ toggle, selectedOption = {} }) => (
              <TextButton onClick={toggle}>{selectedOption.value}</TextButton>
            )}
          </DropdownBase>
        ),
      }}
    />
  </FieldSet>
</StorybookComponents.Stack>;
```

### Design panel
- description: <p>Use corner radius input to control the design of  elements, such as button or box.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(2);
  const [opacity, setOpacity] = React.useState(75);

  const [topLeft, setTopLeft] = React.useState(0);
  const [topRight, setTopRight] = React.useState(0);
  const [bottomLeft, setBottomLeft] = React.useState(0);
  const [bottomRight, setBottomRight] = React.useState(0);

  const [topLeftInvalid, setTopLeftInvalid] = React.useState(false);
  const [topRightInvalid, setTopRightInvalid] = React.useState(false);
  const [bottomLeftInvalid, setBottomLeftInvalid] = React.useState(false);
  const [bottomRightInvalid, setBottomRightInvalid] = React.useState(false);

  return (
    <SidePanel
      onCloseButtonClick={() => {}}
      skin="floating"
      width="288px"
      height="576px"
    >
      <SidePanel.Header title="Box Design" />
      <SidePanel.Field>
        <FieldSet gap="small" legend="Border width" columns="auto 72px">
          <Slider
            onChange={setValue}
            min={0}
            max={10}
            value={value}
            displayMarks={false}
          />
          <Input
            size="small"
            value={value}
            onChange={(e) => setValue(e.target.value)}
          />
        </FieldSet>
      </SidePanel.Field>
      <SidePanel.Field>
        <FieldSet legend="Border radius">
          <CornerRadiusInput
            size="small"
            linkingButtonLabels={{
              pressed: 'Edit individually',
              unpressed: 'Apply to all corners',
            }}
            topLeft={{
              value: topLeft,
              ariaLabel: 'Top left corner',
              onChange: (e) => {
                setTopLeftInvalid(false);
                setTopLeft(e);
              },
            }}
            topRight={{
              value: topRight,
              ariaLabel: 'Top right corner',
              onChange: (e) => {
                setTopRightInvalid(false);
                setTopRight(e);
              },
            }}
            bottomLeft={{
              value: bottomLeft,
              ariaLabel: 'Bottom left corner',
              onChange: (e) => {
                setBottomLeftInvalid(false);
                setBottomLeft(e);
              },
            }}
            bottomRight={{
              value: bottomRight,
              ariaLabel: 'Bottom right corner',
              onChange: (e) => {
                setBottomRightInvalid(false);
                setBottomRight(e);
              },
            }}
          />
        </FieldSet>
      </SidePanel.Field>
    </SidePanel>
  );
};
```


