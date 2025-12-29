
## Feature Examples


### Number of pages
- description: <p>Control the total number of pages available with the <code>totalPages</code> prop.</p><p></p><p>This number starts from two and has no maximum value.</p><p></p><p></p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Pagination currentPage={1} totalPages={2} />
  <Pagination currentPage={1} totalPages={10} />
</StorybookComponents.Stack>;
```

### Current page
- description: <p>Specify which page is currently selected with the <code>currentPage</code> prop.</p><p></p><p>The first page will be selected, if not specified otherwise.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Pagination currentPage={1} totalPages={16} />
  <Pagination currentPage={8} totalPages={16} />
  <Pagination currentPage={16} totalPages={16} />
</StorybookComponents.Stack>;
```




    


