
## Feature Examples


### Presets
- description: Empower the user to quickly select a predefined range or date using `presets` prop.
- example: 
```jsx 

```

### Footer
- description: Make the date selection secure by using `footer` prop which adds summarized date selection and confirmation actions.
- example: 
```jsx 

```

### Number of Months
- description: Specify a number of months visible inside of a panel with `numOfMonths` prop.<br/>
        <br/>
        By default panel displays 2 months at once. Display a single month only when presets are available.
- example: 
```jsx 

```

### Selection Mode
- description: Enable users to select the range of dates with `selectionMode` prop. It supports 2 values:<br/>
        &emsp;- `day` (default) - lets to select 1 day.<br/>
        &emsp;- `range` - lets to select any range of dates.
- example: 
```jsx 

```

### Month and Year Selection
- description: Let the user quickly change the month and year values with:<br/>
        &emsp;- `showMonthDropdown` (default) - enables month selection dropdown.<br/>
        &emsp;- `showYearDropdown` - enables year selection dropdown.
- example: 
```jsx 

```

### Excluding Dates
- description: Control what dates the user can select with 2 props:<br/>
        &emsp;- `filterDate` (default) - define what dates will be selectable.<br/>
        &emsp;- `excludePastDates` - allow selecting only today and future dates.
- example: 
```jsx 

```

### Localization
- description: Change the language using `locale` prop. Some languages will change the start of the week day and order of month and year.
        First Day of the week can be controlled manually with `firstDayOfWeek` prop.<br/>
        <br/>
        Presets and footer actions aren’t controlled by this and have to be translated manually.<br/>
        <br/>
        When using `Yoshi 5` with `BM Flow` there's no need to use `locale` prop anymore. It is handled automatically.
- example: 
```jsx 

```




    


## Common Use Case Examples


### Trigger
- description: Call it out from any action component such as `<IconButton/>`, `<TextButton/>`, `<Button/>`, etc.
        Use it to filter data and content.
- example: 
```jsx 

```


