
## Feature Examples


### Structure
- description: Component consists of a color spectrum canvas, an input area and a `children` area which is used to add swatches.
        Use the `value` prop to set the initial color.
- example: 
```jsx 

```

### Color converter
- description: Enables to view and edit color codes in HEX/RGB/HSB formats.
        Converter is visible by default and can be hidden on demand by setting the `showConverter` to false. 
- example: 
```jsx 

```

### Color value input
- description: Forbid manual color code edit by setting `showInput` to false.
        Input cannot be hidden if the color converter is visible.
- example: 
```jsx 

```

### History bar
- description: Compare the currently active color with a newly picked one before confirming a change with a history bar.
- example: 
```jsx 

```

### Accept empty value
- description: Allow to submit an empty value with `allowEmpty` prop. Use for non-mandatory color selection.
        Define the placeholder message for HEX value input with `emptyPlaceholder` prop.
- example: 
```jsx 

```

### Add color presets
- description: Add a color to the swatches list by clicking the add color button.
        Pass `<Swatches/>` component to children and use `onAdd` property to add a new swatch.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Listing color options
- description: Call out the picker popover on any component click, for example `<Multiselect/>`.
- example: 
```jsx 

```

### Color swatches
- description: Allow users to select a color from a list of presets by adding `<Swatches/>` to the `children` area above the submit actions.
- example: 
```jsx 

```


