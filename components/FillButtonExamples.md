
## Feature Examples


### Icon size
- description: Control plus icon size inside of a button:<br/>
        &emsp;- `small` (default) - use it when the button’s width is 30 pixels or smaller.<br/>
        &emsp;- `medium` - use it when the button's width is larger than 30 pixels.
- example: 
```jsx 

```

### Fill
- description: Set the button's fill-in HEX color or linear gradient. Component allows control of the gradient direction.
- example: 
```jsx 

```

### Disabled
- description: Restrict button interactions with `disabled` prop. This will prevent users from adding a new swatch.
- example: 
```jsx 

```

### Tooltip
- description: Explain the action with a message in a tooltip.
        Control the tooltip position and behaviour by passing relevant properties via `tooltipProps`.
- example: 
```jsx 

```

### Icon
- description: Display a custom icon inside of a button using icon prop.<br/>
      <br/>
      Default icon is a plus and is displayed all the time unless specified otherwise.<br/>
      <br/>
      Overridden icon size cannot be controlled using `iconSize` property. Size has to be controlled manually.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Adding custom swatch
- description: Use a fill button to add new fill options to the existing list.
        It’s recommended to place it as the first item on the list, because it won’t be moved down when new colors appear, letting the user always find it.<br/>
        <br/>
        It can be used with `<FileUpload/>` to open a native file picker to upload images.
- example: 
```jsx 

```


