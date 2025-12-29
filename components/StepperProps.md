
### dataHook
- type: string
- description: Hook for testing purposes.
### onClick
- type: func
- description: Event triggered on step click: `onClick(stepIndex)`
### activeStep
- type: number
- description: Index of the active step.
### steps
- type: arrayOf
- description: An array of steps, where each step is an object with the following properties:
- `text` - step title text (required).
- `type` - step type (`completed`, `disabled`, `error` or default `normal`).
### type
- type: enum
- description: Style type.
### size
- type: enum
- description: Sets the size of the items
### fit
- type: enum
- description: Fit mode for steps. In `stretched` mode the component will grow to fill parent
container width.


