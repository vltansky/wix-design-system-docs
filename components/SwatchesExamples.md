
## Feature Examples


### Colors
- description: Specify a list of colors to show as swatches. Accepts HEX, RGB, HSL and string values.
- example: 
```jsx 

```

### Columns
- description: Define the number of columns in a single row with the `columns` prop.
- example: 
```jsx 

```

### Gap
- description: Define the gap between color swatches using the `gap` prop. It supports pixel units.
- example: 
```jsx 

```

### Clear color
- description: Allows user to select a ‘Clear color’ option. This option is added as a first item on the list using the `showClear` prop.
        Provide an explanatory message with the `showClearMessage` prop.
- example: 
```jsx 

```

### Add button
- description: Add a new color swatch using the:<br/>
        &emsp;- `showAddButton` - specify whether to add button is visible<br/>
        &emsp;- `addButtonIconSize` - control the plus icon size within the button<br/>
        &emsp;- `showAddButtonMessage` -  show action description in a tooltip <br/>
        &emsp;- `onAdd` - calls assigned function <br/>
        &emsp;- `popoverProps` - control the color picker popover by passing props
- example: 
```jsx 

```

### ColorPicker customization
- description: Customize the ColorPicker by using `renderColorPicker` prop. This render prop provides full control over the color picker UI. Use it to configure the default ColorPicker with custom props like `showInput` and `showConverter`.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Inside Color Picker
- description: Use swatches in composer panels to let users create color palettes for their product.
- example: 
```jsx 

```


