
### allowCross
- type: bool
- description: Allows sliders handles to cross.
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### displayMarks
- type: bool
- description: Controls the visibility of the marks.
### displayTooltip
- type: bool
- description: Controls visibility of slide handle tooltip
### id
- type: string
- description: Assigns an unique identifier for the root element.
### max
- type: number
- description: Sets the absolute maximum value of sliders range.
### min
- type: number
- description: Sets the absolute minimum value of the sliders range.
### marks
- type: object
- description: Specifies slider marks. The key determines the position, and the value determines what will show. The object structure should be either
```{ number : number}``` / ```{ number : string }```
### onAfterChange
- type: func
- description: Defines a callback function which will be called when ontouchend or onmouseup is triggered.
### onBeforeChange
- type: func
- description: Defines a callback function which will be called when ontouchstart or onmousedown is triggered.
### onChange
- type: func
- description: Defines a callback function which is called upon every value change.
### rtl
- type: bool
- description: Adjust component for RTL.
### step
- type: number
- description: Specifies the interval between range values.
### pushable
- type: union
- description: Push surrounding handles when moving a handle (relevant for multi value sliders only). Number specifies a minimum distance between handles.
### value
- type: union
- description: Specifies the selected value.
### disabled
- type: bool
- description: Specifies whether interactions are disabled.
### startPoint
- type: number
- description: Specifies the starting value of a track. If undefined, the minimum value of a range is used as a starting point.
### direction
- type: enum
- description: Sets slider direction in either horizontal way or vertical
### ariaLabelForHandle
- type: union
- description: Set the aria-label attributes for slider handles.
### onFocus
- type: func
- description: Sets the onFocus callback for the slider&#39;s handle.
```javascript
 onFocus((handleValue) =&gt; ({}))
```
### onBlur
- type: func
- description: Sets the onBlur callback for the slider&#39;s handle.
```javascript
 onBlur((handleValue) =&gt; ({}))
```
### gradientColor
- type: string
- description: Converts slider to a slider with a gradient background. RGB, HEX formats or color names are accepted.
```javascript
 gradientColor=&#34;rgb(105, 110, 28)&#34;
 gradientColor=&#34;#FFAC4B&#34;
 gradientColor=&#34;pink&#34;
```
If color cannot be parsed, fallback color will be applied
### marksLabelAlignment
- type: enum
- description: Sets the alignment of the marks labels.
### formatValue
- type: func
- description: Formats the raw value for display in tooltip.


