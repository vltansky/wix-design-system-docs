
## Feature Examples


### Status
- description: Control the component status using a `status` prop. It supports 2 states:<br/>
        &emsp;- `error` - use it to highlight an invalid search keyword that has no matching results<br/>
        &emsp;- `warning` - use it to highlight value that impacts the user or can’t be validated
- example: 
```jsx 

```

### Status Message
- description: Explain the status with `statusMessage` prop.<br/>
        <br/>
        It only works when `status` is set to `error`.
- example: 
```jsx 

```

### Disabled
- description: Disable all input interactions with `disabled` prop. Use it to highlight unavailable functions.
- example: 
```jsx 

```

### Suffix
- description: Explain the field value with additional information added to the `suffix` area.
        This prop accepts text, icons and even buttons.
- example: 
```jsx 

```

### List item builders
- description: Build custom layouts with:<br/>
        &emsp;- `listItemSectionBuilder` - use it to group list items into sections by type. See <a href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--listitemsection">ListItemSection</a> for more details.<br/>
        &emsp;- `listItemActionBuilder` - use it to add text buttons for related list actions, e.g., ‘Manage categories’. See <a href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--listitemaction">ListItemAction</a> for more details.<br/>
        &emsp;- `listItemSelectBuilder` - use it to build custom list designs. See <a href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--listitemselect">ListItemSelect</a> for more details.
- example: 
```jsx 

```

### List container height
- description: Control container size with `maxHeightPixels` prop. Use it to restrict the height of longer lists of options.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Checkout Form
- description: The autocomplete selection only be used in a Premium Checkout form.
- example: 
```jsx 

```


