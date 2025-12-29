
## Feature Examples


### Structure
- description: Create timeline content by using `items` prop. Each item has props to control `label`, `width`, `icon` and `state`.
- example: 
```jsx 

```

### Align Label
- description: 
        Control text horizontal alignment with alignLabel prop. It has two options:<br/>
          &emsp;- center (default) - use it in all common cases. <br/>
          &emsp;- start - use it to align text to the left. <br/>
      
- example: 
```jsx 

```

### Skin
- description: 
        Control the style with skin prop. It supports  2 options:<br/>
          &emsp;- dark (default) - use it on colored backgrounds, for example inside SectionHelper.<br/>
          &emsp;- standard - use it on light backgrounds, for example inside a card.<br/>
      
- example: 
```jsx 

```

### Line Type
- description: 
        Control the line type with line prop. It supports  2 options:<br/>
          &emsp;- dashed (default) - use it on colored backgrounds, for example inside SectionHelper.<br/>
          &emsp;- filled - use it to show that this timeline is past.<br/>
      
- example: 
```jsx 

```

### Item Icons
- description: 
        Specify item status by using icon prop for items:<br/>
          &emsp;- DefaultIcon - indicates incomplete steps.<br/>
          &emsp;- ActiveIcon - highlights currently active step.<br/>
          &emsp;- CompleteIcon - indicates complete steps.<br/>
          &emsp;- DestructiveIcon - indicates a step that failed to complete.<br/>
          &emsp;- BoundaryIcon - indicates a milestone that doesn’t have status, but should be reflected in the timeline.<br/>
      
- example: 
```jsx 

```




    


## Common Use Case Examples


### Connect Domain
- description: One of the applications where this component is helpful — it shows the status of domain connection that was requested by a user.
- example: 
```jsx 

```


