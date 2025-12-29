
## Feature Examples


### Affix
- description: <p>Add text, icons or a button at the beginning or end of a text field using prefixIcon and suffix.</p>
- example: 
```jsx 
<div
  style={{
    width: '284px',
    height: '120px',
  }}
>
  <DropdownLayout
    visible
    options={[
      listItemActionBuilder({
        id: 0,
        prefixIcon: <Icons.Edit />,
        title: 'option 1',
        suffix: 'Suffix',
      }),
      listItemActionBuilder({
        id: 1,
        prefixIcon: <Icons.Edit />,
        title: 'option 2',
        suffix: 'Suffix',
      }),
      listItemActionBuilder({
        id: 2,
        prefixIcon: <Icons.Edit />,
        title: 'option 3',
        suffix: 'Suffix',
      }),
    ]}
  />
</div>;
```

### Skin
- description: <p>List item supports three skins:</p><li><code>standard</code> </li><li><code>destructive</code></li><li><code>premium</code></li>
- example: 
```jsx 
<div
  style={{
    width: '284px',
    height: '120px',
  }}
>
  <DropdownLayout
    visible
    options={[
      listItemActionBuilder({
        id: 0,
        title: 'standard',
      }),
      listItemActionBuilder({
        id: 1,
        skin: 'destructive',
        title: 'destructive',
      }),
      listItemActionBuilder({
        id: 1,
        skin: 'premium',
        title: 'premium',
      }),
    ]}
  />
</div>;
```

### Disabled
- description: <p>Supports disabled state.</p><p></p><p>Optionally, tooltips on hover are available to explain disabled states with <code>disabledDescription</code></p>
- example: 
```jsx 
<div
  style={{
    width: '284px',
    height: '120px',
  }}
>
  <DropdownLayout
    visible
    options={[
      listItemActionBuilder({
        id: 0,
        title: 'Disabled with Tooltip',
        prefixIcon: <Icons.Edit />,
        disabled: true,
        disabledDescription: 'You can’t edit this item right now',
      }),
      listItemActionBuilder({
        id: 1,
        title: 'Disabled with Tooltip',
        prefixIcon: <Icons.Edit />,
        disabled: true,
        disabledDescription: 'Editing is restricted for this option',
      }),
      listItemActionBuilder({
        id: 2,
        title: 'Disabled without tooltip',
        prefixIcon: <Icons.Edit />,
        disabled: true,
      }),
    ]}
  />
</div>
```

### Text ellipsis
- description: <p>Text can be set to be ellipsed on tight container width.</p><p></p><p>Tooltips on truncated text will be overridden if the component is disabled. In that case, it will show <code>disabledDescription</code> first.</p>
- example: 
```jsx 
<div style={{ height: '240px' }}>
  <Layout>
    <Cell span={6}>
      <div
        style={{
          width: '200px',
          height: '120px',
        }}
      >
        <DropdownLayout
          visible
          options={[
            listItemActionBuilder({
              id: 0,
              as: 'button',
              title: 'very long message very very',
              ellipsis: true,
            }),
            listItemActionBuilder({
              id: 1,
              as: 'button',
              title: 'very long message very very',
              ellipsis: true,
            }),
            listItemActionBuilder({
              id: 2,
              as: 'button',
              disabled: true,
              disabledDescription: 'This is disabled',
              title: 'very long message very very',
              ellipsis: true,
            }),
          ]}
        />
      </div>
    </Cell>
    <Cell span={6}>
      <div
        style={{
          width: '200px',
          height: '120px',
        }}
      >
        <DropdownLayout
          visible
          options={[
            listItemActionBuilder({
              id: 0,
              as: 'button',
              title: 'very long message very',
            }),
            listItemActionBuilder({
              id: 1,
              as: 'button',
              title: 'very long message very',
            }),
            listItemActionBuilder({
              id: 2,
              as: 'button',
              title: 'very long message very',
            }),
          ]}
        />
      </div>
    </Cell>
  </Layout>
</div>;
```

### Subtitle
- description: <p>A subtitle text can be set with <code>subtitle</code></p>
- example: 
```jsx 
<div
  style={{
    width: '284px',
    height: '240px',
  }}
>
  <DropdownLayout
    visible
    options={[
      listItemActionBuilder({
        id: 0,
        title: 'option 1',
        prefixIcon: <Icons.Edit />,
        subtitle: 'option 1 subtitle',
      }),
      listItemActionBuilder({
        id: 1,
        title: 'option 2',
        prefixIcon: <Icons.Edit />,
        subtitle:
          'option 2 subtitle - with a very long text that will eventually be wrapped',
      }),
      listItemActionBuilder({
        id: 2,
        ellipsis: true,
        title: 'option 3',
        prefixIcon: <Icons.Edit />,
        subtitle:
          'option 3 subtitle - with a very long text that will eventually be truncated by ellipsis',
      }),
    ]}
  />
</div>;
```

### Advanced example
- description: <p>All properties work together and can be combined in various ways. It can be rendered as standalone or as part of dropdown.</p>
- example: 
```jsx 
<Box height="500px">
  <DropdownLayout
    visible
    selectedId={2}
    maxHeightPixels={720}
    options={[
      listItemActionBuilder({
        id: 0,
        title: 'Edit profile',
        prefixIcon: <Icons.Edit />,
        subtitle: 'Update name or contact info',
      }),
      listItemActionBuilder({
        id: 1,
        skin: 'destructive',
        title: 'Delete account',
        prefixIcon: <Icons.Delete />,
        subtitle: 'This action can’t be undone',
      }),
      listItemActionBuilder({
        id: 2,
        disabled: true,
        title: 'Change email',
        prefixIcon: <Icons.Email />,
        subtitle: 'Requires admin approval',
        suffix: <Icons.LockLocked />,
        disabledDescription: 'You don’t have permission to change your email',
      }),
      { id: 'divider-1', value: '-' },
      listItemActionBuilder({
        id: 4,
        title: 'Manage subscriptions',
        prefixIcon: <Icons.Pages />,
        subtitle: 'Includes long text that will wrap if needed',
      }),
      listItemActionBuilder({
        id: 5,
        ellipsis: true,
        title: 'View activity log',
        prefixIcon: <Icons.Activity />,
        subtitle: 'See login and update history for this account',
      }),
      { id: 'divider-2', value: '-' },
      listItemActionBuilder({
        id: 6,
        title: 'Invite to team',
        prefixIcon: <Icons.Users />,
        subtitle: 'Send an invitation email',
        suffix: <Icons.Facebook />,
      }),
      listItemActionBuilder({
        id: 7,
        title: 'View permissions',
        prefixIcon: <Icons.LockUnlocked />,
        subtitle: 'See current role and access level',
      }),
      { id: 'divider-3', value: '-' },
      listItemActionBuilder({
        id: 8,
        size: 'small',
        title: 'Account overview',
        subtitle: 'Summary of account details',
      }),
    ]}
  />
</Box>;
```




    


