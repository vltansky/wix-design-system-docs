
## Feature Examples


### Size
- description: <p>Adjust the component size using <code>size</code> prop. It supports 3 sizes:</p><li><code>large</code> - use it in onboarding flows, where input needs emphasis.</li><li><code>medium</code> (default) - use in all common cases.</li><li><code>small</code> - use in dense and narrow layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddressInput placeholder="Large" size="large" />
  <AddressInput placeholder="Medium" size="medium" />
  <AddressInput placeholder="Small" size="small" />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Style the component using <code>border</code> prop. It supports 4 styles:</p><li><code>round</code> (default) - use it when input acts as a data filter.</li><li><code>standard</code> - use it in forms.</li><li><code>bottomLine</code> - use as a title which can be edited on the click.</li><li><code>none</code> - use in Content Manager's spreadsheet cell.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddressInput placeholder="Round" border="round" />
  <AddressInput placeholder="Standard" border="standard" />
  <AddressInput placeholder="Bottom Line" border="bottomLine" />
  <AddressInput placeholder="None" border="none" />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control component status using <code>status</code> prop. It supports 3 states:</p><li><code>error</code> - use it to highlight an invalid input value.</li><li><code>warning</code> - use it to highlight a value that can’t be validated.</li><li><code>loading</code> - use it to indicate a delayed response from the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AddressInput placeholder="Error" status="error" />
  <AddressInput placeholder="Warning" status="warning" />
  <AddressInput placeholder="Loading" status="loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField status="error" statusMessage="This is an error message.">
      <AddressInput placeholder="See message below" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <AddressInput
      placeholder="Hover on status icon"
      status="error"
      statusMessage="This is an error message."
    />
  </StorybookComponents.Stack>
</StorybookComponents.Stack>;
```

### Disabled
- description: <p>Disable all input interactions with <code>disabled</code> prop. Use it to highlight unavailable functions.</p>
- example: 
```jsx 
<AddressInput placeholder="Disabled" disabled />;
```

### Clear button
- description: <p>Control whether to show a clear button with the <code>clearButton</code> prop. It allows to clear the field quickly when a value is optional.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(
    '903  Wilmar Farm Road, Rockville, Maryland',
  );

  return (
    <AddressInput
      placeholder="Search for address..."
      value={value}
      onChange={(e) => setValue(e.target.value)}
      clearButton={true}
      onClear={() => setValue('')}
    />
  );
};
```

### No results message
- description: <p>Control the message displayed in the dropdown layout when no results are found via <code>noResultsText</code>.</p>
- example: 
```jsx 
<AddressInput value="Invalid search term" noResultsText="No results found" />;
```

### Options layout
- description: <p>Control an options list layout with <code>optionLayout</code> prop. It support 2 layouts for main and secondary labels:</p><li><code>single-line</code> (default) - use it to display labels side by side.</li><li><code>double-line</code> - use it to stack labels vertically.</li>
- example: 
```jsx 
() => {
  const singleLineOptions = [
    addressInputItemBuilder({
      id: 1,
      displayLabel: 'Address 1 Country',
      mainLabel: 'Address 1',
      secondaryLabel: 'Country',
      optionLayout: 'single-line',
    }),
    addressInputItemBuilder({
      id: 2,
      displayLabel: 'Address 2 Country',
      mainLabel: 'Address 2',
      secondaryLabel: 'Country',
      optionLayout: 'single-line',
    }),
  ];
  const doubleLineOptions = [
    addressInputItemBuilder({
      id: 1,
      displayLabel: 'Address 1 Country',
      mainLabel: 'Address 1',
      secondaryLabel: 'Country',
      optionLayout: 'double-line',
    }),
    addressInputItemBuilder({
      id: 2,
      displayLabel: 'Address 2 Country',
      mainLabel: 'Address 2',
      secondaryLabel: 'Country',
      optionLayout: 'double-line',
    }),
  ];
  return (
    <StorybookComponents.Stack flexDirection="column">
      <AddressInput placeholder="Single Line" options={singleLineOptions} />
      <AddressInput placeholder="Double Line" options={doubleLineOptions} />
    </StorybookComponents.Stack>
  );
};
```

### Prefix
- description: <p>Specify icons on the left side with <code>prefix</code> prop or choose not to show it by setting <code>prefix</code> to null.</p><p></p><p>By default, <code><LocationIcon /></code> is displayed.</p>
- example: 
```jsx 
() => {
  const noPrefixOptions = [
    addressInputItemBuilder({
      id: 1,
      displayLabel: 'Address 1 Country',
      mainLabel: 'Address 1',
      secondaryLabel: 'Country',
      prefix: null,
    }),
    addressInputItemBuilder({
      id: 2,
      displayLabel: 'Address 2 Country',
      mainLabel: 'Address 2',
      secondaryLabel: 'Country',
      prefix: null,
    }),
  ];
  const customPrefixOptions = [
    addressInputItemBuilder({
      id: 1,
      displayLabel: 'Address 1 Country',
      mainLabel: 'Address 1',
      secondaryLabel: 'Country',
      prefix: <Icons.Toolbox />,
    }),
    addressInputItemBuilder({
      id: 2,
      displayLabel: 'Address 2 Country',
      mainLabel: 'Address 2',
      secondaryLabel: 'Country',
      prefix: <Icons.Home />,
    }),
  ];
  return (
    <StorybookComponents.Stack flexDirection="column">
      <AddressInput placeholder="No prefix" options={noPrefixOptions} />
      <AddressInput placeholder="Custom prefix" options={customPrefixOptions} />
    </StorybookComponents.Stack>
  );
};
```




    


## Common Use Case Examples


### Custom options list
- description: Use list item builders to build a custom options list layout.
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');
  const options = [
    listItemActionBuilder({
      id: 0,
      prefixIcon: <Icons.Send />,
      title: 'Use current location',
      href: 'https://www.wix.com',
      target: '_blank',
    }),
    listItemSectionBuilder({
      title: 'Saved Addresses',
      type: 'subheader',
    }),
    addressInputItemBuilder({
      id: 1,
      displayLabel: 'Work 2818 Saint Patrick Pl, Helena, AL, 35080',
      mainLabel: 'Work',
      secondaryLabel: '2818 Saint Patrick Pl, Helena, AL, 35080',
      prefix: <Icons.Toolbox />,
      suffix: '2km away',
      optionLayout: 'double-line',
    }),
    addressInputItemBuilder({
      id: 2,
      displayLabel: 'Home 512 4th St NE, Montgomery, MN, 56069',
      mainLabel: 'Home',
      secondaryLabel: '512 4th St NE, Montgomery, MN, 56069',
      prefix: <Icons.Home />,
      suffix: '34km away',
      optionLayout: 'double-line',
    }),
  ];

  const handleSelect = (value) =>
    setValue(
      value.id === 0 ? 'Didžioji gatvė 28, Vilnius Lithuania' : value.label,
    );
  return (
    <AddressInput
      value={value}
      onSelect={handleSelect}
      placeholder="Search places..."
      options={options}
      onClear={() => setValue('')}
      onChange={(e) => setValue(e.target.value)}
    />
  );
};
```


