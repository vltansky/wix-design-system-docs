
## Feature Examples


### Structure
- description: This component consists of a list of options inside a popover that is called out via a `trigger` element. The `trigger` can be any interactive WSR component.
        Usually it’s `TextButton.`
- example: 
```jsx 

```

### Trigger action
- description: Call out a popover on click or hover interactions.
- example: 
```jsx 

```

### Placement
- description: Control the dropdown layout location around a trigger with the `placement` prop. It accepts all
        <a target="_blank" href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--popover">\<Popover/></a>
        placement options. Move it farther from the trigger on X and Y axis with the `moveBy` prop.
- example: 
```jsx 

```

### Dimensions
- description: Control dropdown layout dimensions with:<br/>
      &emsp;- `maxHeight` - limit the height for longer list of options.<br/>
      &emsp;- `minWidth` - control minimum width when the trigger element is narrow.<br/>
      &emsp;- `maxWidth` - limit the width when the list contains long titles.<br/>
      &emsp;- `dynamicWidth` - match the dropdown width to the trigger element width.<br/>
- example: 
```jsx 

```

### Arrow
- description: Control the popover arrow visibility with the `showArrow` prop. It’s not displayed by default.
- example: 
```jsx 

```

### List item builders
- description: Build custom dropdown layouts with:<br/>
      &emsp;- `listItemSectionBuilder` - use this element to group items into sections by type. See
      <a target="_blank" href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--listitemsection">ListItemSection</a> for more details.<br/>
      &emsp;- `listItemActionBuilder` - use this element to add text button for related list actions, e.g. "Manage categories". See
      <a target="_blank" href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--listitemaction">ListItemAction</a> for more details.<br/>
      &emsp;- `listItemSelectBuilder` - use this element to build custom list designs. See
      <a target="_blank" href="https://www.wix-pages.com/wix-design-system-employees/?path=/story/components-api-components--listitemselect">ListItemSelect</a> for more details.<br/>
- example: 
```jsx 

```

### Focus on option
- description: Control a focused element inside of dropdown with:<br/>
      &emsp;- `focusOnOption` - control which option is highlighted when nothing is selected yet.<br/>
      &emsp;- `focusOnSelectedOption` - scrolls list to display selected option when dropdown is opened.<br/>
- example: 
```jsx 

```

### Animate
- description: Create smooth transitions by adding enter and exit animations to the popover with the `animate` prop.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Content filters
- description: Use DropdownBase to build custom filters for page or card content.
- example: 
```jsx 

```

### Assign task or item
- description: Use DropdownBase to call out popovers for the user to assign a person. Once selected, replace the trigger button with a tag representing the user.
- example: 
```jsx 

```


