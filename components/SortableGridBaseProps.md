
### droppable
- type: bool
- description: indicates if user can drop item in the list by default it&#39;s true
### insertPosition
- type: enum
- description: function that specifying where the item can be inserted
### usePortal
- type: bool
- description: in case of wrong position of item during drag you can force SortableListBase to use portals
### dragPreview
- type: bool
- description: if you are having nested SortableListBases,
   list that you are currently dragging need to be marked as dragPreview
   inside of renderItem callback
### items
- type: array
- description: list of items with {id: any}
### onDragStart
- type: func
- description: callback for drag start
### onDragEnd
- type: func
- description: callback for drag end
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### contentClassName
- type: string
- description: className of the first items parent container
### animationDuration
- type: number
- description: animation duration in ms, default = 0 - disabled
### animationTiming
- type: string
- description: animation timing function, default = &#39;&#39; (ease)
### canDrag
- type: func
- description: callback that could prevent item from dragging
### delay
- type: number
- description: number in seconds to add delay between initial mouseDown and drag start
### listOfPropsThatAffectItems
- type: array
- description: In case that you are using some external props inside of renderItems method,
   you need to define them here.

   renderItem = ({ item }) =&gt; &lt;div key={item.id}&gt;{this.props.myAwesomeProp}&lt;/div&gt;

   render() {
      return (
        &lt;SortableListBase
          ...
          listOfPropsThatAffectItems={[this.props.myAwesomeProp]}
        /&gt;
      )
    }
### startFixedElement
- type: node
- description: Node which will be rendered before draggable items and this element won&#39;t be draggable
### endFixedElement
- type: node
- description: Node which will be rendered after draggable items and this element won&#39;t be draggable


