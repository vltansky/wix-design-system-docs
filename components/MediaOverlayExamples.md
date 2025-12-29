
## Feature Examples


### Structure
- description: Component consists of two main containers:<br/> 
          &emsp;- `<MediaOverlay>` - a parent container that accepts image or video content via `media` prop.<br/>
          &emsp;- `<MediaOverlay.Content>` - child container that accepts items that should be displayed on top of a media as child elements.<br/>
- example: 
```jsx 

```

### Overlay content placement
- description: Control the position of overlay elements with placement prop. It supports 5 positions:<br/>
          &emsp;- `top-start`<br/>
          &emsp;- `top-end`<br/>
          &emsp;- `middle`<br/>
          &emsp;- `bottom-start`<br/>
          &emsp;- `bottom-end`<br/>
- example: 
```jsx 

```

### Initial overlay skin
- description: Control initial overlay type with `skin` prop. It supports 3 skins:<br/> 
          &emsp;- `none` (default) - use when no visual overlay is required.<br/>
          &emsp;- `gradient` - use it when relevant data needs to be visible in a default state of the element.<br/>
          &emsp;- `dark` - use it when media underneath is less important, e.g. as a last item in galleries with a total number or images on top.<br/>
- example: 
```jsx 

```

### Hover overlay skin
- description: Control hover overlay type with `hoverSkin` prop. It supports 3 skins:<br/> 
          &emsp;- `none` (default) - use for static media items.<br/>
          &emsp;- `gradient` - use it when hovered item must remain visible, but overlaid content needs a contrast.<br/>
          &emsp;- `dark` - use it to bring the maximum contrast of relevant content on interactive element hover.<br/>
- example: 
```jsx 

```

### Overlay content visibility
- description: Specify when overlay content should be revealed for the user with visible prop. It supports 3 values:<br/> 
          &emsp;- `default` (default) - use it to hide overlay content on element hover.<br/>
          &emsp;- `hover` - use it to reveal overlay content on element hover.<br/>
          &emsp;- `always` - use it to display overlay content all the time.<br/>
- example: 
```jsx 

```

### Border radius
- description: Define border radius in pixels with `borderRadius` prop. Get rid of a default border radius with `removeRoundedBorders` prop.
- example: 
```jsx 

```

### Custom media element
- description: Pass a custom `media` element with media prop.
- example: 
```jsx 

```

### Drag handle
- description: Use a compound `<MediaOverlay.DragHandle />` component for reorderable components. Actions should be placed at the top right corner in this scenario. 
- example: 
```jsx 

```




    


## Common Use Case Examples


### Social media gallery
- description: Use media overlay to place identifying data, such as logo or video duration on top of a media item.
- example: 
```jsx 

```

### Item lists
- description: Use media overlay to list down visual items, such as dishes, that can be edited, marked as favourite or interacted with in any other way.
- example: 
```jsx 

```

### Image gallery
- description: Use media overlay to place static data on top of an image, e.g. to place a counter indicating how many more images there are.
- example: 
```jsx 

```

### Content edit
- description: Use media overlay to store actions related to that media element, such as edit, refresh or delete.
- example: 
```jsx 

```

### Reordable list
- description: Use middle placement at the center to position recordable element indication. This function should use a compound `<MediaOverlay.DragHandle/>` component.
- example: 
```jsx 

```


