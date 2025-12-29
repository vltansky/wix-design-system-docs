
## Feature Examples


### Size
- description: <p>Adjust the component size using the <code>size</code> prop. It supports 3 sizes:</p><li><code>large</code> is best for onboarding flows, where input needs emphasis.</li><li><code>medium</code> (default) – use for most cases.</li><li><code>small</code>  is appropriate for dense and narrow layouts.</li>
- example: 
```jsx 
() => {
  const options = [
    { id: 1, value: 'tag 1' },
    { id: 2, value: 'tag 2' },
    { id: 3, value: 'tag 3' },
  ];

  const renderMultiSelect = ({ size, tagSize }) => {
    const [tags, setTags] = React.useState([
      {
        size: tagSize,
        id: '1',
        label: 'tag 1',
      },
      {
        size: tagSize,
        id: '2',
        label: 'tag 2',
      },
    ]);

    const handleOnSelect = tag =>
      setTags([...tags, { id: tag.id, label: tag.value, size: tagSize }]);

    const handleOnRemoveTag = tagId =>
      setTags(tags.filter(currTag => currTag.id !== tagId));

    return (
      <MultiSelect
        size={size}
        options={options}
        tags={tags}
        onSelect={handleOnSelect}
        onRemoveTag={handleOnRemoveTag}
      />
    );
  };

  return (
    <StorybookComponents.Stack flexDirection="column">
      <FormField label="Large">
        {renderMultiSelect({ size: 'large', tagSize: 'medium' })}
      </FormField>
      <FormField label="Medium">
        {renderMultiSelect({ size: 'medium', tagSize: 'small' })}
      </FormField>
      <FormField label="Small">
        {renderMultiSelect({ size: 'small', tagSize: 'tiny' })}
      </FormField>
    </StorybookComponents.Stack>
  );
};
```

### Border
- description: <p>Style the component using the <code>border</code> prop. It supports 4 styles:</p><li>For forms and most common cases, use <code>default</code>.</li><li>When component is used to filter data, use <code>round</code>.</li><li>Use <code>bottomLine</code> to create an editable, underlined title field.</li><li>When a component provides its own hover and focus styles, such as a table or spreadsheet cells, use <code>none</code>.</li>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelect
        border="standard"
        placeholder="Standard"
        options={options}
        mode="select"
      />
      <MultiSelect
        border="round"
        placeholder="Round"
        options={options}
        mode="select"
      />
      <MultiSelect
        border="bottomLine"
        placeholder="Bottom line"
        options={options}
        mode="select"
      />
      <MultiSelect
        border="none"
        placeholder="None"
        options={options}
        mode="select"
      />
    </StorybookComponents.Stack>
  );
};
```

### Status
- description: <p>Control the component status using a <code>status</code> prop. It supports 3 states:</p><li><code>error</code> demonstrates that a required input is missing something or the entry was invalid.</li><li><code>warning</code> highlights a value that might have a significant impact to a user.</li><li><code>loading</code> shows when a value is being uploaded to the server.</li>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelect status="error" placeholder="Error" options={options} />
      <MultiSelect status="warning" placeholder="Warning" options={options} />
      <MultiSelect status="loading" placeholder="Loading" options={options} />
    </StorybookComponents.Stack>
  );
};
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the component is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop. Control tooltip placement with <code>tooltipPlacement</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For all default cases:</Text>
        <FormField status="error" statusMessage="This is an error message.">
          <MultiSelect placeholder="See message below" options={options} />
        </FormField>
      </StorybookComponents.Stack>
      <StorybookComponents.Stack flexDirection="column" gap="12px">
        <Text secondary>For narrow layouts only:</Text>
        <MultiSelect
          status="error"
          placeholder="Hover on status icon"
          statusMessage="This is an error message."
          options={options}
        />
      </StorybookComponents.Stack>
    </StorybookComponents.Stack>
  );
};
```

### Read-only and disabled
- description: <p>Multi select can also be made read-only or disabled entirely.</p><li><code>readOnly</code> disables adding or editing, but allows the user to copy the current value. Use it to display URLs, code, etc.</li><li><code>disabled</code> removes all interactions and creates a disabled component state. Use it to highlight functions that are unavailable.</li>
- example: 
```jsx 
() => {
  const options = [
    { value: 'Option 1', id: '1' },
    { value: 'Option 2', id: '2' },
    { value: 'Option 3', id: '3' },
    { value: 'Option 4', id: '4' },
    { value: 'Option 5', id: '5' },
  ];

  return (
    <StorybookComponents.Stack flexDirection="column">
      <MultiSelect value="Read Only" readOnly />
      <MultiSelect
        placeholder="Disabled"
        mode="select"
        options={options}
        disabled
      />
    </StorybookComponents.Stack>
  );
};
```

### Action
- description: <p>Encourage user engagement by displaying the call to action. To add a <code><TextButton/></code>, <a href="https://www.wix-style-react.com/storybook/?path=/story/components-actions--textbutton"></a>use the <code>customSuffix</code> property.</p>
- example: 
```jsx 
() => {
  const [tags, setTags] = React.useState([]);

  const handleOnSelect = tag =>
    setTags([...tags, { id: tag.id, label: tag.value }]);

  const handleOnRemoveTag = tagId =>
    setTags(tags.filter(currTag => currTag.id !== tagId));

  return (
    <MultiSelect
      tags={tags}
      options={[
        { id: '1', value: 'tag 1' },
        { id: '2', value: 'tag 2' },
        { id: '3', value: 'tag 3' },
      ]}
      customSuffix={
        <Box>
          <TextButton prefixIcon={<Icons.Add />}>Add Tag</TextButton>
        </Box>
      }
      onSelect={handleOnSelect}
      onRemoveTag={handleOnRemoveTag}
    />
  );
};
```

### Select mode
- description: <p>Allow users to select only options that are listed with <code>mode</code> prop.</p>
- example: 
```jsx 
() => {
  const [tags, setTags] = React.useState([]);

  const handleOnSelect = tag =>
    setTags([...tags, { id: tag.id, label: tag.value }]);

  const handleOnRemoveTag = tagId =>
    setTags(tags.filter(currTag => currTag.id !== tagId));

  return (
    <MultiSelect
      tags={tags}
      options={[
        { id: '1', value: 'tag 1' },
        { id: '2', value: 'tag 2' },
        { id: '3', value: 'tag 3' },
      ]}
      mode="select"
      placeholder="Select tags from a list"
      onSelect={handleOnSelect}
      onRemoveTag={handleOnRemoveTag}
    />
  );
};
```

### Manual input
- description: <p>Allow users to enter their own tags using the keyboard with <code>onManuallyInput</code> property.</p>
- example: 
```jsx 
() => {
  const [tags, setTags] = React.useState([]);

  const handleManualInput = tag =>
    setTags([...tags, { id: Math.random(), label: tag[0] }]);

  const handleOnRemoveTag = tagId =>
    setTags(tags.filter(currTag => currTag.id !== tagId));

  return (
    <MultiSelect
      tags={tags}
      placeholder="Type custom tags and separate them with the Enter key"
      onManuallyInput={handleManualInput}
      onRemoveTag={handleOnRemoveTag}
    />
  );
};
```

### Predicate
- description: <p>Build autocomplete features using the <code>predicate</code> property.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');
  const [tags, setTags] = React.useState([]);

  const options = [
    { value: 'Alabama', id: 'AL' },
    { value: 'California', id: 'CA' },
    { value: 'North Carolina', id: 'NC' },
    { value: 'Colorado', id: 'CO' },
    { value: 'Connecticut', id: 'CT' },
  ];

  const handleOnChange = event => setValue(event.target.value);

  const predicate = option =>
    option.value && option.value.toLowerCase().includes(value.toLowerCase());

  const handleOnSelect = tag =>
    setTags([...tags, { id: tag.id, label: tag.value }]);

  const handleOnRemoveTag = tagId =>
    setTags(tags.filter(currTag => currTag.id !== tagId));

  return (
    <MultiSelect
      predicate={predicate}
      tags={tags}
      value={value}
      options={options}
      onChange={handleOnChange}
      placeholder="Start typing a state to find a match"
      onSelect={handleOnSelect}
      onRemoveTag={handleOnRemoveTag}
    />
  );
};
```

### Reorder
- description: <p>Use the <code>onReorder</code> property to allow users to change the order in which keywords are displayed.</p>
- example: 
```jsx 
() => {
  const [tags, setTags] = React.useState([
    { id: 1, label: 'One' },
    { id: 2, label: 'Two' },
    { id: 3, label: 'Three' },
  ]);

  const options = [
    { id: 1, value: 'One' },
    { id: 2, value: 'Two' },
    { id: 3, value: 'Three' },
  ];

  const handleOnSelect = tag =>
    setTags([...tags, { id: tag.id, label: tag.value }]);

  const handleOnRemoveTag = tagId =>
    setTags(tags.filter(currTag => currTag.id !== tagId));

  return (
    <MultiSelect
      tags={tags}
      options={options}
      onReorder={({ addedIndex, removedIndex }) => {
        const nextTags = tags.slice();
        nextTags.splice(addedIndex, 0, ...nextTags.splice(removedIndex, 1));
        setTags(nextTags);
      }}
      onSelect={handleOnSelect}
      onRemoveTag={handleOnRemoveTag}
    />
  );
};
```




    


## Common Use Case Examples


### Enter contact emails
- description: <p>Multiselect input can be useful for entering contacts or emails.</p><p></p><p>If combined with advanced list item props, multiselect can provide explicit information, therefore, making multiple keyboard entries easier.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');
  const [tags, setTags] = React.useState([]);

  const contacts = [
    { name: 'River Watts', email: 'riverw@wix.com', id: 1 },
    { name: 'Jesse Neimus', email: 'jessen@wix.com', id: 2 },
    { name: 'Morgan James', email: 'morganj@wix.com', id: 3 },
    { name: 'Reese Whiteman', email: 'reesew@wix.com', id: 4 },
  ];

  const options = contacts.map(contact => ({
    ...contact,
    ...listItemSelectBuilder({
      prefix: (
        <Avatar
          size="size30"
          imgProps={{ src: `AvatarExample${contact.id}.jpg` }}
        />
      ),
      id: contact.id,
      title: contact.name,
      subtitle: contact.email,
    }),
  }));

  const handleOnSelect = ({ name, email, id }) =>
    setTags([...tags, { id, label: name ? `${email} (${name})` : email }]);

  const handleOnRemoveTag = tagId =>
    setTags(tags.filter(currTag => currTag.id !== tagId));

  const handleOnChange = event => setValue(event.target.value);

  const predicate = option =>
    (option.name + option.email).toLowerCase().includes(value.toLowerCase());

  return (
    <MultiSelect
      value={value}
      options={options}
      tags={tags}
      onChange={handleOnChange}
      onSelect={handleOnSelect}
      onRemoveTag={handleOnRemoveTag}
      placeholder="Start typing a name to find a match"
      predicate={predicate}
    />
  );
};
```


