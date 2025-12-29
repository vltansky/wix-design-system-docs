
## Feature Examples


### Close button
- description: <p>Control whether navigation toast can be dismissed by a user with <code>dismissible</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NavigationToast prefixIcon={<Icons.ArrowBentUpLeft />}>
    Dismissable (default)
  </NavigationToast>
  <NavigationToast dismissable={false} prefixIcon={<Icons.ArrowBentUpLeft />}>
    Non-dismissable
  </NavigationToast>
</StorybookComponents.Stack>;
```

### Prefix icon
- description: <p>Define prefix icon with <code>prefixIcon</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <NavigationToast prefixIcon={<Icons.ArrowBentUpLeft />}>
    {'Default icon'}
  </NavigationToast>
  <NavigationToast prefixIcon={<Icons.ArrowUp />} dismissable={false}>
    {'Custom icon'}
  </NavigationToast>
</StorybookComponents.Stack>;
```

### Timeout
- description: <p>Define if toast should disappear automatically with <code>duration</code> prop.</p><p></p><p>By default, toast is persistent and duration is set to 0 milliseconds.</p>
- example: 
```jsx 
(() => {
  const makeId = () => Math.random().toString(36).substring(2, 9);

  const Example = () => {
    const [toasts, setToasts] = React.useState([]);

    const removeToast = (id) => {
      setToasts((toasts) => toasts.filter((toast) => toast.id !== id));
    };

    const addToast = (id, toast) => {
      setToasts((toasts) => [...toasts, { id, toast }]);
    };

    const createNavigationToast = (children, duration = 0) => {
      const id = makeId();

      addToast(
        id,
        <NavigationToast
          key={id}
          duration={duration}
          onDismiss={() => {
            removeToast(id);
          }}
        >
          {children}
        </NavigationToast>,
      );
    };

    return (
      <>
        <Box gap={1}>
          <Button
            size="small"
            onClick={() => createNavigationToast('No timeout (default)', 0)}
          >
            No timeout (default)
          </Button>
          <Button
            size="small"
            onClick={() => createNavigationToast('Custom timeout', 7000)}
          >
            Custom timeout (7 seconds)
          </Button>
        </Box>
        <ToastContainer>{toasts.map(({ toast }) => toast)}</ToastContainer>
      </>
    );
  };

  return Example;
})();
```




    


