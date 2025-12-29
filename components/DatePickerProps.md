
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### dataHook
- type: string
- description: Applies as data-hook HTML attribute that can be used in the tests
### autoFocus
- type: bool
- description: Focus selected day automatically when component mounts or updates
### customInput
- type: node
- description: Override a field with a custom input element. If you only need to pass custom props to the `&lt;Input/&gt;`, then use `inputProps` instead.
### inputProps
- type: object
- description: Allows you to pass default Input component properties
### dateIndication
- type: func
- description: ##### Add an indication under a specific date.
   Function returns the indication node of a specific date or null if this day doesn&#39;t have an indication.
- `param` {date: Date, isSelected: boolean }
- `date` - a date
- `isSelected` - whether this date is the selected date
- `return` {React.node} - the indication node of a specific date or null if this day doesn&#39;t have an indication.
### locale
- type: enum
- description: Specify date picker instance locale
### dateStyle
- type: enum
- description: Sets date format of locale
### disabled
- type: bool
- description: Specify whether a field should be disabled or not
### excludePastDates
- type: bool
- description: Specify whether past dates should be selectable or not
### filterDate
- type: func
- description: ##### Specify selectable dates:
 * `param` {Date} `date` - a date to check
 * `return` {boolean} - true if `date` should be selectable, false otherwise
### inputDataHook
- type: string
- description: Applies a data-hook HTML attribute for date picker input
### calendarDataHook
- type: string
- description: Applies a data-hook HTML attribute for date picker calendar view
### placeholderText
- type: string
- description: Defines a placeholder of the field
### rtl
- type: bool
- description: Specify whether RTL mode is enabled or not. When true, the keyboard navigation will be changed, meaning pressing on the right arrow will navigate to the previous day, and pressing on the left arrow will navigate to the next day.
### value
- type: object
- description: Defines the selected date
### initialOpen
- type: bool
- description: Specify whether the calendar will be initially visible or not
### status
- type: enum
- description: Controls the status of a field
### statusMessage
- type: node
- description: Defines the status message to be displayed on status icon hover. If not given or empty, the tooltip won’t be shown.
### width
- type: union
- description: Sets the width of picker input in pixels or percentage
### zIndex
- type: number
- description: Set a desired z-index for date picker popover
### popoverProps
- type: shape
- description: Allows you to pass popover properties. The default placement value depends on the rtl prop - would be &#39;top-start&#39; when rtl=false and &#39;top-end&#39; in case of rtl=true.
### firstDayOfWeek
- type: enum
- description: Specify the starting day of a week, allowing only from 0 to 6 (Sunday to Saturday). The default value is 1 which means Monday.
### size
- type: enum
- description: Specifies the size of the input
### readOnly
- type: bool
- description: Specify whether date picker input is readOnly or not
### today
- type: union
- description: Sets today&#39;s date. The today indication is added automatically according to the user timezone but in some cases, we need the ability to add the today indication based on the business timezone.
### clearButton
- type: bool
- description: Display a clear button (x) on a non-empty field
### clearButtonAriaLabel
- type: string
- description: Aria label for the clear button
### onChange
- type: func
- description: Provides a callback function when  day in selected in the calendar
### onClear
- type: func
- description: Displays clear button (X) on a non-empty input and calls callback with no arguments
### onClose
- type: func
- description: Defines a callback function that is  called whenever a user presses escape, clicks outside of the element or a date is selected and `shouldCloseOnSelect` is set. Receives an event as a first argument.
### onOpen
- type: func
- description: Defines a callback function which is called when date picker is opened.
### onMonthChange
- type: func
- description: Defines a callback function that is called with the date of the first day of the month whenever the user selects a month in the calendar
### disableKeyboardType
- type: bool
- description: Disable typing the in the input. When true, choosing a date is possible only by picking from the calendar. Default: false.
### showYearDropdown
- type: bool
- description: Displays a selectable yearDropdown
### showMonthDropdown
- type: bool
- description: Displays a selectable monthDropdown
### shouldCloseOnSelect
- type: bool
- description: Specify whether the calendar closes on day selection
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
### validate
- type: bool
- description: Enables internal input validation
### onValidate
- type: func
- description: Defines a callback function which is called on cases when date is validated.
- {validationType: &#39;outOfBoundsError&#39; | &#39;formatError&#39; | &#39;valid&#39;, format: string, value: string }
- `validationType` - type &#39;formatError&#39; is set when validated date is in the wrong date format
                   - type &#39;outOfBoundsError&#39; is set when &#39;excludePastDates&#39; is true and date input is before today
                   - type &#39;valid&#39; is set when entered date is valid
- `format` - is set to valid date format
- `value` - is set to current input value
### clearButtonTooltipContent
- type: node
- description: When provided, hover will display a tooltip
### clearButtonTooltipProps
- type: node
- description: Tooltip props
### renderFooter
- type: func
- description: Function which renders a provided node at the bottom of the Calendar.
### calendarProps
- type: shape
- description: Defines the size of calendar opened


