
## Feature Examples


### Layout
- description: Change calendar’s layout using `numOfMonths` prop. It can display 1 or 2 months.
- example: 
```jsx 

```

### Size
- description: Adjust the component `size` using size prop. It supports 2 sizes:<br/>
      &emsp;-  `medium` (default) - use it in all common cases.<br/>
      &emsp;- `small` - use it in dense layouts like Bookings Calendar to save vertical and horizontal space.
- example: 
```jsx 

```

### Date Indication
- description: Mark important dates with `dateIndication` prop. It’s helpful when the calendar needs to highlight the dates with happening events.
- example: 
```jsx 

```

### Selection Mode
- description: Enable select the range of dates with `selectionMode` prop. It supports 2 values:<br/>
      &emsp;- `day` (default) - lets to select 1 day.<br/>
      &emsp;- `range` - lets to select any range of dates.
- example: 
```jsx 

```

### Excluding Dates
- description: Control what dates the user can select with 2 props:<br/>
      &emsp;- `filterDate` - define what dates will be selectable.<br/>
      &emsp;- `excludePastDates` - allow selecting only today and future dates.
      
- example: 
```jsx 

```

### Select  Month and Year
- description: Let the user quickly change the month and year values with props::<br/>
      &emsp;- `showMonthDropdown ` - enables month dropdown.<br/>
      &emsp;- `showYearDropdown` - enables year dropdown.
      
- example: 
```jsx 

```

### Localization
- description: Change the language using `locale` prop. Some languages will change the start of the week day and order of month and year. First Day of the week can be controlled manually with `firstDayOfWeek` prop.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Event scheduling
- description: Use a calendar with time picker to let our users set the appointment date or article publish date.
- example: 
```jsx 

```


