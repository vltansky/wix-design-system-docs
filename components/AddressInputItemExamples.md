
## Feature Examples


### Structure
- description: The component consists of two labels accompanied by a location icon:<br/> 
        &emsp;- `mainLabel` - use it to display a main keywords for search suggestions;<br/>
        &emsp;- `secondaryLabel` - use it for secondary address data, such as country or region.
- example: 
```jsx 

```

### States
- description: Control the state of a component with:<br/>
        &emsp;- `highlighted` - use it to mark a suggested value<br/>
        &emsp;- `selected` use it to mark an active selection<br/>
        &emsp;- `disabled` - use it to mark an unavailable item
- example: 
```jsx 

```

### Layout
- description: Control option layout with optionLayout prop. It supports 2 values:<br/>
        &emsp;- `single-line` (default) - use in all common cases<br/>
        &emsp;- `double-line` - use for addresses that display more data (include country, region, post code and more)
- example: 
```jsx 

```

### Affix
- description: Support option value with additional information added to `prefix` and `suffix` props.
        Props accept text, icons and even badges.<br/>
        <br/>
        `prefix` area by default is filled with a location icon to indicate that this is an address list item.
- example: 
```jsx 

```




    


## Common Use Case Examples


### List item builders
- description: Use it as a list item to build custom address input suggestions.
- example: 
```jsx 

```


