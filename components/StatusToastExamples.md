
## Feature Examples


### Status
- description: <p>Control the toast type with the <code>status</code> prop: </p><li><code>success</code> is for a toast displayed after a successful action.</li><li><code>error</code> is used for error messages and information about critical issues that prevent users from continuing.</li><li><code>warning</code> is meant to draw the user's attention to unresolved issues that might affect the application but doesn't block the process.</li><li><code>info</code> is for informational updates that aren't urgent.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="24px">
  <StatusToast
    status="success"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}>
    Success
  </StatusToast>
  <StatusToast
    status="error"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}>
    Error
  </StatusToast>
  <StatusToast
    status="warning"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}>
    Warning
  </StatusToast>
  <StatusToast
    status="info"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}>
    Info
  </StatusToast>
</StorybookComponents.Stack>;
```

### Close button
- description: <p>Control whether the user can dismiss a status toast with the<code>dismissible</code> prop. </p><p></p><p>NOTE: If this is not enabled, <code>error</code>, <code>warning</code> and <code>info</code> toasts will remain visible on the screen until an action is taken or the issue is resolved. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="24px">
  <StatusToast
    status="error"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}
  >
    Dismissable
  </StatusToast>
  <StatusToast
    status="error"
    action={<StatusToast.Action>Action</StatusToast.Action>}
  >
    Non-dismissable
  </StatusToast>
</StorybookComponents.Stack>;
```

### Action
- description: <p>Add a button to a notification with the <code>action</code> prop.  Offer one action only to avoid complexity. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="24px">
  <StatusToast
    status="success"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}>
    With action
  </StatusToast>
  <StatusToast
    status="success"
    dismissible>
    Without action
  </StatusToast>
</StorybookComponents.Stack>;
```

### Width
- description: <p>Component width is fixed to 600px. If the context exceeds the length, it will wrap to the next line. </p>
- example: 
```jsx 
  <StatusToast
    status="warning"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}
  >
    Width is 680px
  </StatusToast>
```

### Height
- description: <p>Minimum component height is 42px. The component height will grow together with the content. Height is not limited, so be cautious about using very long texts, as a long message will cover any content behind it. </p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="24px">
  <StatusToast
    status="warning"
    dismissible
    action={<StatusToast.Action>Action</StatusToast.Action>}>
This is a one-line content example  </StatusToast>
  <StatusToast
    status="warning"
    dismissible
  action={<StatusToast.Action>Action</StatusToast.Action>}>
This is a much longer content example that wraps automatically to a second line while the status toast height grows with it   </StatusToast>
</StorybookComponents.Stack>;
```

### Positioning 
- description: <p>The position of a status toast is not customizable. <code><ToastContainer/></code> position is attached to the viewport with 26px gap from the bottom and not to the parent container or content within the page. </p>
- example: 
```jsx 
(() => {
  const makeId = () => Math.random().toString(36).substring(2, 9);

  const Blank = () => (
    <div
      style={{
        background:
          'repeating-linear-gradient(45deg, rgba(0,0,0,0.2), rgba(0,0,0,0.2) 10px, rgba(255,255,255,0.2) 10px, rgba(255,255,255,0.2) 20px)',
        flex: '1 1 auto',
      }}
    />
  );

  const Example = () => {
    const [toasts, setToasts] = React.useState([]);

    const clearToasts = () => {
      setToasts([]);
    };

    const removeToast = (id) => {
      setToasts((toasts) => toasts.filter((toast) => toast.id !== id));
    };

    const addToast = (id, toast) => {
      setToasts((toasts) => [...toasts, { id, toast }]);
    };

    const createStatusToast = (status, content, action) => {
      const id = makeId();

      addToast(
        id,
        <StatusToast
          key={id}
          dataHook={id}
          status={status}
          dismissible
          dismissLabel="Dismiss"
          onDismiss={() => {
            removeToast(id);
          }}
          action={action}
        >
          {content}
        </StatusToast>,
      );
    };

    return (
      <>
        <Box gap={1}>
          <Button
            size="small"
            onClick={() =>
              createStatusToast(
                'success',
                'I am placed 26px from the bottom of the screen',
                <StatusToast.Action>Got it</StatusToast.Action>,
              )
            }
          >
            Click here to see positioning
          </Button>
        </Box>
        <ToastContainer>{toasts.map(({ toast }) => toast)}</ToastContainer>
      </>
    );
  };

  return Example;
})();
```

### Timeout
- description: <p>Whether notification disappears automatically or not can be controlled with <code>duration</code> prop.</p><p></p><p>Recommended delay until toast disappears is at least <strong>7 seconds</strong>.</p><p></p><p>When possible, it is recommended to make <code>error</code> toasts persistent, giving the user a chance to resolve the error or dismiss it at their own pace.</p>
- example: 
```jsx 
(() => {
  const makeId = () => Math.random().toString(36).substring(2, 9);

  const Blank = () => (
    <div
      style={{
        background:
          'repeating-linear-gradient(45deg, rgba(0,0,0,0.2), rgba(0,0,0,0.2) 10px, rgba(255,255,255,0.2) 10px, rgba(255,255,255,0.2) 20px)',
        flex: '1 1 auto',
      }}
    />
  );

  const Example = () => {
    const [toasts, setToasts] = React.useState([]);

    const clearToasts = () => {
      setToasts([]);
    };

    const removeToast = (id) => {
      setToasts((toasts) => toasts.filter((toast) => toast.id !== id));
    };

    const addToast = (id, toast) => {
      setToasts((toasts) => [...toasts, { id, toast }]);
    };

    const createStatusToast = (status, content, action) => {
      const id = makeId();

      addToast(
        id,
        <StatusToast
          key={id}
          dataHook={id}
          status={status}
          dismissible
          dismissLabel="Dismiss"
          onDismiss={() => {
            removeToast(id);
          }}
          action={action}
        >
          {content}
        </StatusToast>,
      );
    };

    return (
      <>
        <Box gap={1}>
          <Button
            size="small"
            onClick={() =>
              createStatusToast(
                'info',
                'Info toast - no timeout',
                <StatusToast.Action>Action</StatusToast.Action>,
              )
            }
          >
            Info
          </Button>
          <Button
            size="small"
            onClick={() =>
              createStatusToast(
                'warning',
                'Warning toast - no timeout',
                <StatusToast.Action>Action</StatusToast.Action>,
              )
            }
          >
            Warning
          </Button>
          <Button
            size="small"
            onClick={() =>
              createStatusToast(
                'error',
                'Error toast - no timeout',
                <StatusToast.Action>Action</StatusToast.Action>,
              )
            }
          >
            Error
          </Button>
          <Button
            size="small"
            onClick={() =>
              createStatusToast(
                'success',
                'Success toast - timeout after 7 seconds',
                <StatusToast.Action>Action</StatusToast.Action>,
              )
            }
          >
            Success
          </Button>
          {toasts.length ? (
            <Tooltip content="Clear">
              <IconButton
                size="small"
                onClick={clearToasts}
                priority="secondary"
              >
                <Icons.DeleteSmall />
              </IconButton>
            </Tooltip>
          ) : null}
        </Box>
        <ToastContainer>{toasts.map(({ toast }) => toast)}</ToastContainer>
      </>
    );
  };

  return Example;
})();
```

### Stacking
- description: <p>By default, only one toast is visible at a time and the rest will be hidden under the first one. </p><p></p><p>However, you can control how many toast are visible at the same time. <strong>Up to thee toast</strong> can be visible at the same time. If more than given number is shown, they will be stacked with 6px gap between each other. </p><p></p><p>If three toasts are already visible, the newest one will be shown instead of the oldest one, until a slot is freed up by closing a toast, solving an issue, or it times out. </p>
- example: 
```jsx 
() => {
  const makeId = () => Math.random().toString(36).substring(2, 9);

  const [toasts, setToasts] = React.useState([]);

  const clearToasts = () => {
    setToasts([]);
  };

  const removeToast = (id) => {
    setToasts((toasts) => toasts.filter((toast) => toast.id !== id));
  };

  const addToast = (id, toast) => {
    setToasts((toasts) => [...toasts, { id, toast }]);
  };

  const createStatusToast = (status, content, action) => {
    const id = makeId();

    addToast(
      id,
      <StatusToast
        key={id}
        dataHook={id}
        status={status}
        dismissible
        dismissLabel="Dismiss"
        onDismiss={() => {
          removeToast(id);
        }}
        action={action}
      >
        {content}
      </StatusToast>,
    );
  };

  return (
    <>
      <Box gap={1}>
        <Button
          size="small"
          onClick={() =>
            createStatusToast(
              'error',
              'I am 1st toast',
              <StatusToast.Action>Action</StatusToast.Action>,
            )
          }
        >
          1st toast
        </Button>
        <Button
          size="small"
          onClick={() =>
            createStatusToast(
              'error',
              'I am 2nd toast',
              <StatusToast.Action>Action</StatusToast.Action>,
            )
          }
        >
          2nd toast
        </Button>
        <Button
          size="small"
          onClick={() =>
            createStatusToast(
              'error',
              'I am 3rd toast',
              <StatusToast.Action>Action</StatusToast.Action>,
            )
          }
        >
          3rd toast
        </Button>
        <Button
          size="small"
          onClick={() =>
            createStatusToast(
              'error',
              'I am 4th toast',
              <StatusToast.Action>Action</StatusToast.Action>,
            )
          }
        >
          4th toast
        </Button>
        {toasts.length ? (
          <Tooltip content="Clear">
            <IconButton size="small" onClick={clearToasts} priority="secondary">
              <Icons.DeleteSmall />
            </IconButton>
          </Tooltip>
        ) : null}
      </Box>

      <ToastContainer maxToasts={3}>
        {toasts.map(({ toast }) => toast)}
      </ToastContainer>
    </>
  );
};
```




    


## Common Use Case Examples


### In modals
- description: <p>Status toasts should be used inside of modals as well. Toasts in modals have the same logic as in pages. They appear at the same location, with an offset of 26px from the bottom of the page and have the same stacking behavior.</p>
- example: 
```jsx 
() => {
  const [shown, setShown] = React.useState(false);
  const [copy, setCopy] = React.useState(false);
  const [toast, setToast] = React.useState(null);

  const createStatusToast = (status, content, action) => {
    setToast(
      <StatusToast
        key={'test-id'}
        status={status}
        dismissible
        dismissLabel="Dismiss"
        onDismiss={clearToast}
        action={action}
      >
        {content}
      </StatusToast>,
    );
  };

  const clearToast = () => {
    setToast(null);
  };

  const onShowModal = () => {
    setShown(true);
    createStatusToast(
      'error',
      'Your internet connection has been lost. Refresh and try again',
      <StatusToast.Action>Refresh</StatusToast.Action>,
    );
  };

  const onCloseModal = () => {
    setShown(false);
    clearToast();
  };

  const data = [
    { name: 'User 1', plan: 'Gold', email: 'user1@mail.com' },
    { name: 'User 2', plan: 'Silver', email: 'user2@mail.com' },
    { name: 'User 3', plan: 'Gold', email: 'user3@mail.com' },
    { name: 'User 4', plan: 'Gold', email: 'user4@mail.com' },
    { name: 'User 5', plan: 'Bronze', email: 'user5@mail.com' },
    { name: 'User 6', plan: 'Bronze', email: 'user6@mail.com' },
    { name: 'User 7', plan: 'Gold', email: 'user7@mail.com' },
    { name: 'User 8', plan: 'Bronze', email: 'user8@mail.com' },
  ];
  const columns = [
    { title: 'Name', render: (row) => row.name },
    { title: 'Plan', render: (row) => row.plan },
    { title: 'Email', render: (row) => row.email },
  ];

  return (
    <>
      <Card>
        <Card.Header
          title="Send coupons to your members"
          subtitle="Select members who will receive a new coupon via email."
          suffix={
            <Button size="small" priority="secondary" onClick={onShowModal}>
              Send Coupons
            </Button>
          }
        />
        <Modal
          isOpen={shown}
          onRequestClose={onCloseModal}
          shouldCloseOnOverlayClick
          screen="desktop"
        >
          <CustomModalLayout
            title="Send coupons to members"
            subtitle="Select members who will receive coupons via email."
            onCloseButtonClick={() => setShown(false)}
            primaryButtonOnClick={() => setShown(false)}
            secondaryButtonOnClick={() => setShown(false)}
            width="720px"
            maxHeight="350px"
            removeContentPadding
            primaryButtonText="Send"
            secondaryButtonText="Cancel"
            sideActions={
              <Checkbox
                size="small"
                checked={copy}
                onChange={() => setCopy(!copy)}
              >
                Send copy Email to myself
              </Checkbox>
            }
            content={
              <Table data={data} columns={columns} showSelection>
                <Table.Content />
              </Table>
            }
          />
        </Modal>
      </Card>
      <ToastContainer>{toast}</ToastContainer>
    </>
  );
};
```


