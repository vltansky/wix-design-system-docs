
## Feature Examples


### Authorization
- description: <p>Requests to Atlas must be authorized using an authorization header. Check out this <a href="https://bo.wix.com/wix-docs/rest/internal-tools/atlas/introduction#internal-tools_atlas_introduction_atlas-v2-api-authorization">Wix Doc</a> about how to retrieve a signed instance in your environment.</p><p></p><p>Pass an authorization token to AtlasAddressInput using the <code>token</code> prop.</p>
- example: 
```jsx 
<AtlasAddressInput placeholder="Search..." token="some_auth_token" />;
```

### Size
- description: <p>Adjust the component size using <code>size</code> prop. It supports 3 sizes:</p><li><code>large</code> - use it in onboarding flows, where input needs emphasis.</li><li><code>medium</code> (default) - use in all common cases.</li><li><code>small</code> - use in more dense and narrow layouts.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AtlasAddressInput placeholder="Large" size="large" />
  <AtlasAddressInput placeholder="Medium" size="medium" />
  <AtlasAddressInput placeholder="Small" size="small" />
</StorybookComponents.Stack>;
```

### Border
- description: <p>Style the component using <code>border</code> prop. It supports 4 styles:</p><li><code>round</code> (default) - use it when input acts as a filter.</li><li><code>standard</code> - use it in a form.</li><li><code>bottomLine</code> - use as a title which can be edited on the click.</li><li><code>none</code> - use in Content Manager's spreadsheet cell.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AtlasAddressInput placeholder="Round" border="round" />
  <AtlasAddressInput placeholder="Standard" border="standard" />
  <AtlasAddressInput placeholder="Bottom Line" border="bottomLine" />
  <AtlasAddressInput placeholder="None" border="none" />
</StorybookComponents.Stack>;
```

### Status
- description: <p>Control component status using <code>status</code> prop. It supports 3 states:</p><li><code>error</code> - use it to highlight invalid input value.</li><li><code>warning</code> - use it to highlight value that can’t be validated.</li><li><code>loading</code> - use it to indicate a delayed response from the server.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AtlasAddressInput placeholder="Error" status="error" />
  <AtlasAddressInput placeholder="Warning" status="warning" />
  <AtlasAddressInput placeholder="Loading" status="loading" />
</StorybookComponents.Stack>;
```

### Status message
- description: <p>Add text that explains the status or what action the user should take with the <code>statusMessage</code> prop.</p><p></p><p>Showing the status message inline, directly below the input is preferred in all default cases.</p><li>To add an accessible inline message, wrap the component in a <code><FormField/></code> and add the <code>statusMessage</code>.</li><li>To add a status message in a tooltip that requires users to hover on the icon, use the <code>statusMessage</code> prop.</li><p></p><p>View more inline status message examples in <code><FormField/></code>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For all default cases:</Text>
    <FormField statusMessage="This is an error message." status="error">
      <AtlasAddressInput placeholder="See message below" />
    </FormField>
  </StorybookComponents.Stack>
  <StorybookComponents.Stack flexDirection="column" gap="12px">
    <Text secondary>For narrow layouts only:</Text>
    <AtlasAddressInput
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
<AtlasAddressInput placeholder="Disabled" disabled />;
```

### Clear button
- description: <p>Control whether to show a clear button with <code>clearButton</code> prop. It allows you to clear the field quickly when a value is optional.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState(
    '903  Wilmar Farm Road, Rockville, Maryland',
  );
  return (
    <AtlasAddressInput
      placeholder="Search for address..."
      value={value}
      onChange={(e) => setValue(e.target.value)}
      clearButton={true}
      onClear={() => setValue('')}
    />
  );
};
```

### Options layout
- description: <p>Control options list layout with <code>optionLayout</code> prop. It supports 2 layouts for main and secondary labels:</p><li><code>single-line</code> (default) - use it to display labels side by side.</li><li><code>double-line</code> - use it to stack labels vertically.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AtlasAddressInput placeholder="Single Line" optionLayout="single-line" />
  <AtlasAddressInput placeholder="Double Line" optionLayout="double-line" />
</StorybookComponents.Stack>;
```

### Options affix
- description: <p>Add supportive info to an options list in defined affix areas:</p><li><code>optionPrefix</code> - use the location icon by default. Override only in cases where more specific context is needed, i.e. defining work address.</li><li><code>optionSuffix</code> - use it to provide extra info about address.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <AtlasAddressInput
    optionPrefix={<Icons.Toolbox />}
    placeholder="Option prefix"
  />
  <AtlasAddressInput optionSuffix="5km away" placeholder="Option suffix" />
</StorybookComponents.Stack>;
```

### Localization
- description: <p>Translate search results per country by providing language and locale details.</p><li>Specify the language with <code>language</code> prop.</li><li>Specify a required address formatting with <code>locale</code> prop.</li>
- example: 
```jsx 
<AtlasAddressInput placeholder="Search..." language="en" locale="en-us" />;
```




    


## Common Use Case Examples


### Custom address
- description: <p>Define custom address formatting using <code>onSelect</code> callback that provides a <code>getAddress</code> function to fetch a <a href="https://github.com/wix-private/p13n/blob/master/protos/common/src/main/proto/wix/common/address.proto">Wix Address Object</a> from Atlas.</p><p></p><p>This example displays a post code along with the address.</p>
- example: 
```jsx 
() => {
  const [value, setValue] = React.useState('');

  const onChange = (event) => setValue(event.target.value);

  const onClear = () => setValue('');

  const onSelect = (option, getAddress) => {
    getAddress().then((address) => {
      setValue(`${option.label} - ${address.postalCode}`);
    });
  };

  return (
    <AtlasAddressInput
      onChange={onChange}
      onClear={onClear}
      onSelect={onSelect}
      value={value}
      token="some_auth_token"
      placeholder="Type address and select it"
    />
  );
};
```


