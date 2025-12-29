
## Feature Examples


### Structure
- description: Add content to a timeline by using `items` prop. Each item has props to control these containers:<br/> 
        &emsp;- `customPrefix` - overrides the default circle with a specified icon to mark important milestones.<br/>
        &emsp;- `label` -  describes the event.<br/>
        &emsp;- `labelAction` -  enables an action that provides more info or leads to an event.<br/>
        &emsp;- `suffix` - displays event’s date or other additional info.<br/>
        <br/>
        Note that all of these containers are nodes (i.e., can store any component as a child item). Their positions are fixed.
- example: 
```jsx 

```

### Gap
- description: Control vertical distance between the items with a `gap` prop.<br/>
      <br/>
      Default value is 30 px.
- example: 
```jsx 

```

### Label
- description: Set the content for an item’s label with a `label` prop.<br/>
      <br/>
      Label describes the event of the Timeline item. It wraps into multiple lines where necessary.<br/>
      <br/>
      Note that the label container accepts any component as a child item.
- example: 
```jsx 

```

### Label action
- description: Add an action button for a Timeline’s item using a `labelAction` prop.<br/>
      <br/>
      Use it as a link to actions or further information about the Timeline item.
- example: 
```jsx 

```

### Custom Prefix
- description: Set a custom icon for a Timeline item with a `customPrefix` prop. Use it to highlight important milestones or errors.<br/>
      <br/>
      Control it for each item individually.<br/>
      <br/>
      When not defined, prefix is a default filled-in circle.
- example: 
```jsx 

```

### Suffix
- description: Add more information to the Timeline item with a `suffix` prop.<br/>
      <br/>
      Use it to show the date of an event (but it can also render any component as a child item).
- example: 
```jsx 

```




    


## Common Use Case Examples


### Store Order Activity
- description: Illustrate the history of a product order with a Timeline, stored inside a `<Card/>`.<br/>
      <br/>
      In this case, users can fill in recent events into the Timeline themselves, change events’ status, and view more related information.
- example: 
```jsx 

```


