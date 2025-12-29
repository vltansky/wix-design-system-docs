
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### onChange
- type: func
- description: Defines a callback function  which is called whenever the user selects a day or a date range in the calendar
### onClose
- type: func
- description: Defines a callback function which is called whenever user press `escape` or click outside of the element
### excludePastDates
- type: bool
- description: Specifies whether past dates should be selectable or not
### filterDate
- type: func
- description: Specifies dates that are selectable. Only the dates that match defined criteria will be available for a user to select.
### value
- type: union
- description: Defines a selected date or date range
### selectionMode
- type: enum
- description: Specifies if user can select a single day or a date range
### showYearDropdown
- type: bool
- description: Specifies whether to display a year selection dropdown inside of a calendar
### showMonthDropdown
- type: bool
- description: Specifies whether to display a month selection dropdown inside of a calendar
### shouldCloseOnSelect
- type: bool
- description: Specifies whether calendar should close on a day selection
### locale
- type: union
- description: Specifies date picker instance locale
### numOfMonths
- type: number
- description: Defines a number of months to display inside of a panel
### presets
- type: arrayOf
- description: Defines an array of predefined calendar presets that are displayed as select items on the left side of a panel
### footer
- type: func
- description: Renders a panel footer. Pass `&lt;CalendarPanelFooter/&gt;` in all common cases. `({selectedDays, submitDisabled}) =&gt; void` - `selectedDays` is the same as the CalendarPanel&#39;s `value` prop. `submitDisabled` is true when the current selectedDays is not valida for submission.


