
### dataHook
- type: string
- description: Applied as data-hook HTML attribute that can be used in the tests
### title
- type: string
- description: The editable selector&#39;s title
### toggleType
- type: enum
- description: Specifies the type of the toggle
### newRowLabel
- type: string
- description: Text for the add new row button
### editButtonText
- type: string
- description: Text for the edit button
### onOptionAdded
- type: func
- description: New option added callback function
### onOptionEdit
- type: func
- description: Option edited callback function
### onOptionDelete
- type: func
- description: Option deleted callback function
### onOptionToggle
- type: func
- description: Option toggled callback function
### options
- type: arrayOf
- description: Array of objects:
* `title` - the title of the option.
* `isSelected` - whether this option is selected or not.


