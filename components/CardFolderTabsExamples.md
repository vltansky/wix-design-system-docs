
## Feature Examples


### Structure
- description: This component is composed of a `<CardFolderTabs>` wrapper that holds any number of `<CardFolderTabs.Tab/>` items inside of it.
        You can specify content for each tab separately.
- example: 
```jsx 

```

### Tab button width
- description: Specify maximum allowed tab width in pixels or percentage with `maxTabWidth` prop. Stretch tabs equally to fill the full width of a card with `fluid` prop.
        <br/>
        <br/>
        Initially all tab buttons are sized to be equal with a maximum width of 138px. Set `maxTabWidth` value  to “fit-content” to size them to match title width.
        <br/>
- example: 
```jsx 

```

### Disabled
- description: Restrict users from opening a certain tab with `disabled` prop.
- example: 
```jsx 

```

### Custom title
- description: Customize the tab title by overriding default text string value of `name` prop to any required components or their composition.
- example: 
```jsx 

```

### Text overflow
- description: Control text overflow with `ellipsis` prop. By default, tab titles that exceed `maxTabWidth` will be truncated and displayed in a tooltip when the user hover over a tab. Set `ellipsis` to false to enable text wrapping.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Empty state
- description: Use section `<EmptyState/>`  as tab content when there’s no data to display. 
- example: 
```jsx 

```


