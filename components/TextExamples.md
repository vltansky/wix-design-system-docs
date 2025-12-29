
## Feature Examples


### Size
- description: <p>Control the size of the text with the <code>size</code> prop. It supports 3 sizes:</p><li><code>medium</code> is the default for all common cases of running text.</li><li><code>small</code> is for field labels and secondary content.</li><li><code>tiny</code> is for short messages of minor importance. </li><p></p><p>Note: Use <code>tiny</code> in exceptional cases only, as it's hard to read, and not recommended for accessibility.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text size="medium">
    Medium size is a default size that's used most of the time.
  </Text>
  <Text size="small">
    Small size is used where medium doesn't fit or content is less important.
  </Text>
  <Text size="tiny">
    Tiny size is used when there's no space or it's the last thing users need to
    see.
  </Text>
</StorybookComponents.Stack>;
```

### Weight
- description: <p>Control the weight of the text with the <code>weight</code> prop. It supports 3 weights:</p><li><code>bold</code> emphasizes running text.</li><li><code>normal</code> is for form field values and button labels.</li><li><code>thin</code> is the default for all regular paragraphs.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text weight="bold">Bold weight is meant to emphasize running text.</Text>
  <Text weight="normal">
    Normal weight is for form field values and buttons.
  </Text>
  <Text weight="thin">
    Thin weight is for running text. Use it for all regular paragraphs. 
  </Text>
</StorybookComponents.Stack>;
```

### Skin
- description: <p>Control the color of text with the <code>skin</code> prop. It supports 6 skins:</p><li><code>standard</code></li><li><code>premium</code></li><li><code>success</code></li><li><code>error</code></li><li><code>disabled</code></li><li><code>primary</code></li><p></p><p><code>standard</code> skin can be placed on backgrounds with color. All other skins can be used only on white or gray backgrounds.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text skin="standard">Standard skin appears in all regular texts.</Text>
  <Text skin="premium">
    Premium skin calls users to upgrade to get unlimited features.
  </Text>
  <Text skin="success">
    Success skin indicates that everything went smooth.
  </Text>
  <Text skin="error">Error skin alerts users that something went wrong.</Text>
  <Text skin="disabled">
    Disabled skin indicates that something cannot be accessed.
  </Text>
  <Text skin="primary">Primary skin is for inline links.</Text>
</StorybookComponents.Stack>;
```

### Light
- description: <p>Invert text color so it can be used on a dark background with the <code>light</code> prop. It affects standard and disabled skins only.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text>Dark text is used on light backgrounds.</Text>
  <Box backgroundColor="D10">
    <Text light>Light text is used on dark backgrounds.</Text>
  </Box>
</StorybookComponents.Stack>;
```

### Secondary
- description: <p>Emphasize content hierarchy by setting running text priority to <code>secondary</code>. It applies lower contrast font color for standard skin text only.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text skin="standard" secondary>
    Dark secondary text is used where it's less important than standard text.
  </Text>
  <Box backgroundColor="D10">
    <Text light secondary>
      Light secondary text also serves as neutral content just on a dark
      background.
    </Text>
  </Box>
</StorybookComponents.Stack>;
```

### Unordered list
- description: <p>Use a standard <code><ul></code> HTML tag to build an unordered list. Control its style with the <code>listStyle</code> prop. It supports 2 styles:</p><li><code>checkmark</code></li><li><code>circle</code></li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text listStyle="checkmark">
    The list below is built using standard "ul" and "li" HTML tags.
    <ul>
      <li>First statement</li>
      <li>
        Second statement
        <ul>
          <li>Subitem</li>
          <li>Subitem</li>
        </ul>
      </li>
      <li>Third statement</li>
    </ul>
  </Text>
  <Text listStyle="circle">
    The list below is built using standard "ul" and "li" HTML tags.
    <ul>
      <li>First statement</li>
      <li>
        Second statement
        <ul>
          <li>Subitem</li>
          <li>Subitem</li>
        </ul>
      </li>
      <li>Third statement</li>
    </ul>
  </Text>
</StorybookComponents.Stack>;
```

### Ordered list
- description: <p>Use a standard <code><ol></code> HTML tag to build an ordered list. It accepts all default HTML <a href="https://www.w3schools.com/html/html_lists_ordered.asp">types</a>.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <Text>
    The list below is built using standard "ol" and "li" HTML tags.
    <ol type="1">
      <li>First statement</li>
      <li>
        Second statement
        <ol type="1">
          <li>Subitem</li>
          <li>Subitem</li>
        </ol>
      </li>
      <li>Third statement</li>
    </ol>
  </Text>
  <Text>
    The list below is built using standard "ol" and "li" HTML tags.
    <ol type="A">
      <li>First statement</li>
      <li>
        Second statement
        <ol type="a">
          <li>Subitem</li>
          <li>Subitem</li>
        </ol>
      </li>
      <li>Third statement</li>
    </ol>
  </Text>
  <Text>
    The list below is built using standard "ol" and "li" HTML tags.
    <ol type="I">
      <li>First statement</li>
      <li>
        Second statement
        <ol type="i">
          <li>Subitem</li>
          <li>Subitem</li>
        </ol>
      </li>
      <li>Third statement</li>
    </ol>
  </Text>
</StorybookComponents.Stack>;
```

### Text overflow
- description: <p>Handle text overflow by wrapping text, truncating it or doing both.</p><p></p><p>By default, text wraps into any number of lines. With <code>ellipsis</code> enabled, it will truncate to fit the width of the parent container. Specify <code>maxLines</code> to truncate text after a specified number of rows.</p><p></p><p>Always provide full text content to view:</p><li>The most accessible pattern is to add a 'Show more' button which expands the full text.</li><li>Show full text on mouse hover with <code>showTooltip</code> prop. Control tooltip style by passing all default <code><Tooltip/></code> properties via <code>tooltipProps</code>.</li>
- example: 
```jsx 
() => {
  const [open, setOpen] = React.useState(false);
  const suffixIcon = open ? <Icons.ChevronUp /> : <Icons.ChevronDown />;

  return (
    <StorybookComponents.Stack flexDirection="column" width="50%">
      <Text>Text that wraps forever. It doesn't show any ellipsis.</Text>
      <Box direction="vertical">
        <Text maxLines={open ? 4 : 2} ellipsis>
          Text that is truncated but has an accessible alternative to provide
          its full content. Click 'Show more' to expand full text. Full text is
          then revealed in the main layout.
        </Text>
        <TextButton onClick={() => setOpen(!open)} suffixIcon={suffixIcon}>
          {open ? 'Show less' : 'Show more'}
        </TextButton>
      </Box>
      <Text ellipsis maxLines={2}>
        Text with ellipsis. It can wrap until a specified number of lines. When
        the limit is reached it displays the 3 dot ellipsis. Full text is
        revealed on hover.
      </Text>
    </StorybookComponents.Stack>
  );
};
```

### Custom tag
- description: <p>Render text as a custom HTML tag by using the <code>tagName</code> prop.</p>
- example: 
```jsx 
<Text tagName="div">This text will be rendered as a "div" element.</Text>;
```

### Inline link
- description: <p>Use a default <code><a></code> HTML tag to add an inline link to a sentence.</p>
- example: 
```jsx 
<Text>
  Use a standard HTML 'a' tag to add <a>a text link</a> within the line.
</Text>;
```




    


## Common Use Case Examples


### Inline button
- description: <p>Use inline <code><Box/></code> to place buttons or other elements inline to text.</p>
- example: 
```jsx 
<Text>
  Set up subscriptions, memberships or package plans to sell on your site.
  <Box inline paddingLeft="SP1">
    <TextButton underline="always">Learn more about Pricing Plans</TextButton>
  </Box>
</Text>;

```

### Show more
- description: <p>Toggle <code>maxLines</code> prop value to recreate 'Show more / Show less' behavior for text paragraphs.</p><p></p><p>This is a more accessible way to handle text overflow than using a tooltip only, since keyboard users can't access the complete text inside the tooltip.</p>
- example: 
```jsx 
() => {
  const [open, setOpen] = React.useState(false);
  const suffixIcon = open ? <Icons.ChevronUp /> : <Icons.ChevronDown />;

  return (
    <Box width="50%" direction="vertical">
      <Text maxLines={open ? 4 : 1} ellipsis>
        Click 'Show more' to display more than a single line of text. Toggling
        maxLines allows to recreate expand / collapse behaviour.
      </Text>
      <TextButton onClick={() => setOpen(!open)} suffixIcon={suffixIcon}>
        {open ? 'Show less' : 'Show more'}
      </TextButton>
    </Box>
  );
};
```


