
## Feature Examples


### Enter Animation
- description: <p>Make component appear using these four animation types:</p><li> <code>Fade In</code> - use it for sudden appearances or state changes.</li><li><code>Move In</code> - use it to emphasize direction from which object appears. It supports 4 possible directions.</li><li> <code>Expand</code> - use it for objects that appear in between the content. It supports 4 possible directions.</li><li><code>ScaleUp </code>- use it to explain that object appears from a certain point. It supports 9 possible directions.</li><p></p><p>To see all possible direction options please check API.</p>
- example: 
```jsx 
() => {
  const [showFade, setShowFade] = React.useState(false)
  const [showMove, setShowMove] = React.useState(false)
  const [showExpand, setShowExpand] = React.useState(false)
  const [showScaleUp, setShowScaleUp] = React.useState(false)

  return (
    <StorybookComponents.Stack height={200}>
      <StorybookComponents.Stack flexDirection="column" width="25%">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          fadeIn
          <Button onClick={() => setShowFade(!showFade)}>
            {showFade ? 'Reset' : 'Play'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showFade}
          enterAnimation={{
            fadeIn: {
              duration: 'slow02',
              easing: 'enterEasing',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" width="25%">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          moveIn
          <Button onClick={() => setShowMove(!showMove)}>
            {showMove ? 'Reset' : 'Play'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showMove}
          enterAnimation={{
            moveIn: {
              direction: 'bottomToTop',
              distance: '20px',
              duration: 'slow02',
              easing: 'enterEasing',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" width="25%">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          expand
          <Button onClick={() => setShowExpand(!showExpand)}>
            {showExpand ? 'Reset' : 'Play'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showExpand}
          enterAnimation={{
            expand: {
              direction: 'bottomToTop',
              duration: 'slow02',
              easing: 'enterEasing',
              size: '100%',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          scaleUp
          <Button onClick={() => setShowScaleUp(!showScaleUp)}>
            {showScaleUp ? 'Reset' : 'Play'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showScaleUp}
          enterAnimation={{
            scaleUp: {
              direction: 'bottom',
              duration: 'slow02',
              easing: 'enterEasing',
              scale: '100%',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  )
}

```

### Exit Animation
- description: <p>Make components disappear using these four animation types:</p><li><code>Fade Out</code> - use it for appearances or state changes.</li><li><code>Move Out</code> - use it to emphasize the direction to which object disappears. It supports 4 possible directions.</li><li><code>Collapse</code> - use it for objects that disappear in between the content. It supports 4 possible directions.</li><li><code>ScaleDown</code> - use it to explain that an object disappears to a certain point. It supports 9 possible directions.</li><p></p><p>To see all possible direction options please check API.</p>
- example: 
```jsx 

() => {
  const [showFade, setShowFade] = React.useState(true);
  const [showMove, setShowMove] = React.useState(true);
  const [showCollapse, setShowCollapse] = React.useState(true);
  const [showScaleDown, setShowScaleDown] = React.useState(true);

  return (
    <StorybookComponents.Stack height={200}>
      <StorybookComponents.Stack flexDirection="column" width="25%">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          fadeOut
          <Button onClick={() => setShowFade(!showFade)}>
            {showFade ? 'Play' : 'Reset'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showFade}
          exitAnimation={{
            fadeOut: {
              duration: 'slow02',
              easing: 'exitEasing',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" width="25%">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          moveOut
          <Button onClick={() => setShowMove(!showMove)}>
            {showMove ? 'Play' : 'Reset'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showMove}
          exitAnimation={{
            moveOut: {
              direction: 'bottomToTop',
              distance: '50px',
              duration: 'slow02',
              easing: 'exitEasing',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" width="25%">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          collapse
          <Button onClick={() => setShowCollapse(!showCollapse)}>
            {showCollapse ? 'Play' : 'Reset'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showCollapse}
          exitAnimation={{
            collapse: {
              direction: 'bottomToTop',
              duration: 'slow02',
              easing: 'exitEasing',
              size: '0%',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column">
        <StorybookComponents.Stack
          flexDirection="column"
          width="80px"
          gap="6px"
        >
          scaleDown
          <Button onClick={() => setShowScaleDown(!showScaleDown)}>
            {showScaleDown ? 'Play' : 'Reset'}
          </Button>
        </StorybookComponents.Stack>
        <Transition
          show={showScaleDown}
          exitAnimation={{
            scaleDown: {
              direction: 'bottom',
              duration: 'slow02',
              easing: 'exitEasing',
              scale: '0%',
            },
          }}
        >
          <StorybookComponents.Placeholder height="100px" width="100px" />
        </Transition>
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};

```

### Duration
- description: <p>Use it to determine how long animation plays. Choose form 6 following properties:</p><li><code>Fast01</code> - 100ms. Use for small objects such as Buttons or Toggles.</li><li><code>Fast02</code> - 150ms. Use for larger than small objects such as Tooltips or Section Helpers.</li><li><code>Medium01</code> - 200ms. Use for medium size objects like dropdowns or accordions.</li><li><code>Medium02</code> - 300ms. Use for greater than medium size objects like side panel or small modals.</li><li><code>Slow01</code> - 450ms. Use for larger objects like big modals or large collapsible content.</li><li><code>Slow02</code> - 600ms. Use for very large objects like page transitions.</li>
- example: 
```jsx 
() => {
  const [showMove, setShowMove] = React.useState(true)

  const renderTransition = (duration) => {
    return (
      <StorybookComponents.Stack flexDirection="column" width="25%" gap="6px">
        {duration}
        <Transition
          show={showMove}
          enterAnimation={{}}
          exitAnimation={{
            moveOut: {
              direction: 'topToBottom',
              distance: '100px',
              duration,
              easing: 'standardEasing',
            },
          }}
        >
          <StorybookComponents.Placeholder height="60px" width="60px" />
        </Transition>
      </StorybookComponents.Stack>
    )
  }

  return (
    <StorybookComponents.Stack height={300} flexDirection="column">
      <StorybookComponents.Stack>
        <Button onClick={() => setShowMove(!showMove)}>
          {showMove ? 'Play' : 'Reset'}
        </Button>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack justifyContent="space-between">
        {renderTransition('fast01')}
        {renderTransition('fast02')}
        {renderTransition('medium01')}
        {renderTransition('medium02')}
        {renderTransition('slow01')}
        {renderTransition('slow02')}
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  )
}

```

### Easing
- description: <p>Use it to determine the velocity of the object's motion:</p><li><code>Enter Easing</code> - used for objects that appear on the screen during the enter animation.</li><li><code>Exit Easing</code> - used for objects that disappear from the screen during the exit animation.</li><li><code>Standard Easing</code> - used for objects that stay present on the screen during enter or exit animations. For example toggle switch.</li>
- example: 
```jsx 
() => {
  const [showMove, setShowMove] = React.useState(true)

  const renderEasing = (easing) => (
    <StorybookComponents.Stack flexDirection="column" width="25%" gap="6px">
      {easing}
      <Transition
        show={showMove}
        exitAnimation={{
          moveOut: {
            direction: 'topToBottom',
            distance: '100%',
            duration: 'slow02',
            easing,
          },
        }}
      >
        <StorybookComponents.Placeholder height="60px" width="60px" />
      </Transition>
    </StorybookComponents.Stack>
  )

  return (
    <StorybookComponents.Stack flexDirection="column" height={300}>
      <StorybookComponents.Stack>
        <Button onClick={() => setShowMove(!showMove)}>
          {showMove ? 'Play' : 'Reset'}
        </Button>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack justifyContent="space-between">
        {renderEasing('enterEasing')}
        {renderEasing('exitEasing')}
        {renderEasing('standardEasing')}
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  )
}

```

### Delay
- description: <p>Use it to determine the time it takes for animation or next animation to start. There are three delay values:</p><li><code>Short</code> - 100ms.</li><li><code>Medium</code> - 150ms.</li><li><code>Long</code> - 200ms.</li>
- example: 
```jsx 
() => {
  const [showMove, setShowMove] = React.useState(true)

  const renderTransition = (delay) => {
    return (
      <StorybookComponents.Stack flexDirection="column" width="25%" gap="6px">
        {delay}
        <Transition
          show={showMove}
          exitAnimation={{
            moveOut: {
              direction: 'topToBottom',
              distance: '100px',
              duration: 'slow02',
              delay,
              easing: 'standardEasing',
            },
          }}
        >
          <StorybookComponents.Placeholder height="60px" width="60px" />
        </Transition>
      </StorybookComponents.Stack>
    )
  }

  return (
    <StorybookComponents.Stack height={300} flexDirection="column">
      <StorybookComponents.Stack>
        <Button onClick={() => setShowMove(!showMove)}>
          {showMove ? 'Play' : 'Reset'}
        </Button>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack justifyContent="space-between">
        {renderTransition('short')}
        {renderTransition('medium')}
        {renderTransition('long')}
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  )
}

```




    


## Common Use Case Examples


### Animating list items
- description: Use Transition component in cases when new elements appear or disappear from a screen, like in this case when dismissing list items.
- example: 
```jsx 

() => {
  const [child, setChild] = React.useState([]);

  const handleRemove = id => {
    setChild(previous => previous.filter(c => c.id !== id));
  };

  const handleAddChild = () => {
    const id = new Date().getTime();
    const item = {
      id,
      node: (
        <TableListItem
          key={id}
          showDivider
          onClick={() => {
            handleRemove(id);
          }}
          options={[
            { value: <Text>Order {child.length}</Text>, align: 'left' },
            { value: <Text>2 minutes ago</Text>, align: 'center' },
            {
              value: (
                <TableActionCell
                  size="small"
                  primaryAction={{
                    text: 'Mark as fullfilled',
                    skin: 'inverted',
                    onClick: () => handleRemove(id),
                  }}
                />
              ),
            },
          ]}
        />
      ),
    };
    setChild([item, ...child]);
  };

  return (
    <Card hideOverflow>
      <Card.Header
        title="Your order waitlist"
        suffix={
          <Button
            size="small"
            prefixIcon={<Icons.AddSmall />}
            onClick={() => handleAddChild()}
          >
            Add new order
          </Button>
        }
      />
      <Card.Divider />
      <Box direction="vertical">
        <Transition
          enterAnimation={{
            fadeIn: {
              delay: 'long',
              duration: 'slow02',
              easing: 'enterEasing',
            },
            moveIn: {
              direction: 'bottomToTop',
              distance: '30px',
              duration: 'slow02',
              delay: 'long',
              easing: 'enterEasing',
            },
          }}
          exitAnimation={{
            fadeOut: {
              delay: 'long',
              duration: 'slow02',
              easing: 'exitEasing',
            },
            moveOut: {
              direction: 'leftToRight',
              distance: '30px',
              duration: 'slow02',
              delay: 'long',
              easing: 'exitEasing',
            },
          }}
        >
          {child.map(c => c.node)}
        </Transition>
      </Box>
    </Card>
  );
};

```


