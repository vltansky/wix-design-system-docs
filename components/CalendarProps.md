
### dataHook
- type: string
- description: Applies as data-hook HTML attribute that can be used in the tests
### autoFocus
- type: bool
- description: Focus selected day automatically when component mounts or updates
### numOfMonths
- type: enum
- description: Allows to display multiple months at once. Currently it shows 1 or 2 months only.
### firstDayOfWeek
- type: enum
- description: First day of the week, allowing only from 0 to 6 (Sunday to Saturday). The default value is 1 which means Monday.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### onChange
- type: func
- description: Provides a callback function when day in selected in the calendar
### onClose
- type: func
- description: Defines a callback function that is  called whenever a user presses escape, clicks outside of the element or a date is selected and `shouldCloseOnSelect` is set. Receives an event as a first argument.
### onKeyDown
- type: func
- description: Provides a callback function when any key is clicked in the calendar
### onMonthChange
- type: func
- description: Defines a callback function that is called with the date of the first day of the month whenever the user selects a month in the calendar
### excludePastDates
- type: bool
- description: Specify whether past dates should be selectable or not
### filterDate
- type: func
- description: ##### Specify selectable dates:
 * `param` {Date} `date` - a date to check
 * `return` {boolean} - true if `date` should be selectable, false otherwise
### value
- type: union
- description: Defines the selected date
### selectionMode
- type: enum
- description: Whether the user should be able to select a date range, or just a single day
### showYearDropdown
- type: bool
- description: Displays a selectable yearDropdown
### showMonthDropdown
- type: bool
- description: Displays a selectable monthDropdown
### shouldCloseOnSelect
- type: bool
- description: Specify whether the calendar closes on day selection
### locale
- type: enum
- description: Specify date picker instance locale
### rtl
- type: bool
- description: Specify whether RTL mode is enabled or not. When true, the keyboard navigation will be changed means pressing on the right arrow will navigate to the previous day, and pressing on the left arrow will navigate to the next day.
### dateIndication
- type: func
- description: ##### Add an indication under a specific date.
   Function returns the indication node of a specific date or null if this day doesn&#39;t have an indication.
- `param` {date: Date, isSelected: boolean }
- `date` - a date
- `isSelected` - whether this date is the selected date
- `return` {React.node} - the indication node of a specific date or null if this day doesn&#39;t have an indication.
### today
- type: instanceOf
- description: Sets today&#39;s date. The today indication is added automatically according to the user timezone but in some cases, we need the ability to add the today indication based on the business timezone.
### leftArrowAriaLabel
- type: string
- description: Defines a string value that labels the left arrow in calendar header
### leftArrowAriaLabelledBy
- type: string
- description: Identifies the element that labels the left arrow in calendar header
### rightArrowAriaLabel
- type: string
- description: Defines a string value that labels the right arrow in calendar header
### rightArrowAriaLabelledBy
- type: string
- description: Identifies the element that labels the right arrow in calendar header
### monthDropdownAriaLabel
- type: string
- description: Defines a string value that labels the months dropdown in calendar header
### monthDropdownAriaLabelledBy
- type: string
- description: Identifies the element that labels the months dropdown in calendar header
### yearDropdownAriaLabel
- type: string
- description: Defines a string value that labels the years dropdown in calendar header
### yearDropdownAriaLabelledBy
- type: string
- description: Identifies the element that labels the years dropdown in calendar header
### size
- type: enum
- description: Defines calendar size property. It can be either small or medium (default)
### containFocus
- type: bool
- description: Use FocusScope to contain focus within calendar


