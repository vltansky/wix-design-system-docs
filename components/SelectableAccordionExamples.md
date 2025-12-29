
## Feature Examples


### Structure
- description: <p>Selectable accordion consists of clickable items and their inner content, which is expanded when an item is selected.</p><p></p><p>Inner content areas accept any components inside.</p>
- example: 
```jsx 
<SelectableAccordion
  type="toggle"
  items={[
    {
      title: 'First item',
      initiallyOpen: true,
      content: (
        <StorybookComponents.Placeholder>
          First item content
        </StorybookComponents.Placeholder>
      ),
    },
    {
      title: 'Second item',
      content: (
        <StorybookComponents.Placeholder>
          Second item content
        </StorybookComponents.Placeholder>
      ),
    },
  ]}
/>;
```

### Type
- description: <p>Change the type of items' controller with <code>type</code> prop. It supports 2 options:</p><li><code>checkbox</code> - use when multiple items can be selected at once.</li><li><code>toggle</code>  - use when items (or features) are enabled / disabled.</li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SelectableAccordion
    type="checkbox"
    items={[
      {
        title: 'Checkbox',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Checkbox',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
  <SelectableAccordion
    type="toggle"
    items={[
      {
        title: 'Toggle',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Toggle',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Vertical padding
- description: <p>Control vertical padding of selectable accordion items with <code>verticalPadding</code> prop:</p><li><code>medium</code> is a larger padding that emphasizes a few items.</li><li><code>small</code> (default) is a standard padding for common cases.</li><li><code>tiny</code> is a compact padding that displays more items in a smaller space.</li><p></p><p>Note that <code>verticalPadding</code> prop only controls the padding of selectable accordion items (and not their inner content).</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SelectableAccordion
    verticalPadding="medium"
    type="toggle"
    items={[
      {
        title: 'Medium',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Medium',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
  <SelectableAccordion
    verticalPadding="small"
    type="toggle"
    items={[
      {
        title: 'Small',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Small',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
  <SelectableAccordion
    verticalPadding="tiny"
    type="toggle"
    items={[
      {
        title: 'Tiny',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Tiny',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Title and subtitle
- description: <p>Describe selectable accordion items with <code>title</code> and <code>subtitle</code> props.</p><p></p><p>These containers also accept any component or a composition of multiple elements.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SelectableAccordion
    type="toggle"
    items={[
      {
        title: 'Title',
        subtitle: 'Subtitle',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Title',
        subtitle: (
          <Box gap="SP1">
            <Text size="small">Subtitle</Text>
            <TextButton size="small" underline="always">
              Learn More
            </TextButton>
          </Box>
        ),
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: <StorybookComponents.Placeholder height="18px" />,
        subtitle: <StorybookComponents.Placeholder height="18px" />,
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Initially open item
- description: <p>By default, all selectable accordion items are closed until selected by the user.</p><p></p><p>Control which items are open on page load with <code>initiallyOpen</code> prop.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SelectableAccordion
    type="toggle"
    items={[
      {
        title: 'Default',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Initially open',
        initiallyOpen: true,
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```

### Disabled item
- description: <p>Disable a selectable accordion item with <code>disabled</code> prop.</p><p></p><p>Users will not be able to select or deselect it.</p>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column">
  <SelectableAccordion
    type="toggle"
    items={[
      {
        title: 'Default',
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
      {
        title: 'Disabled',
        disabled: true,
        content: (
          <StorybookComponents.Placeholder>
            Item content
          </StorybookComponents.Placeholder>
        ),
      },
    ]}
  />
</StorybookComponents.Stack>;
```




## Developer Examples


### Programatically controlled item
- description: <p>Control the selectable accordion items programatically using <code>open</code> prop.</p>
- example: 
```jsx 
() => {
  const [firstOptionOpen, setFirstOptionOpen] = React.useState(true);

  return (
    <StorybookComponents.Stack flexDirection="column">
      <Box>
        <Button
          onClick={() => setFirstOptionOpen(!firstOptionOpen)}
          priority="secondary"
        >
          Select {firstOptionOpen ? 'second' : 'first'} item
        </Button>
      </Box>
      <SelectableAccordion
        type="checkbox"
        items={[
          {
            open: firstOptionOpen,
            title: 'First item',
            content: (
              <StorybookComponents.Placeholder>
                Item content
              </StorybookComponents.Placeholder>
            ),
          },
          {
            title: 'Second item',
            content: (
              <StorybookComponents.Placeholder>
                Item content
              </StorybookComponents.Placeholder>
            ),
            open: !firstOptionOpen,
          },
        ]}
      />
    </StorybookComponents.Stack>
  );
};
```


    


## Common Use Case Examples


### In long settings pages
- description: <p>A selectable accordion on a settings page helps save space and reduces mental load for the user.</p><p></p><p>This is because the UI displays only the settings that are relevant at a time.</p>
- example: 
```jsx 
() => {
  const [selectedOptions, setSelectedOptions] = React.useState([]);

  return (
    <Card hideOverflow>
      <Card.Header
        title="Benefits"
        subtitle="Set up how your benefits work in this plan."
        suffix=<Button size="small" priority="secondary">
          Connect More Benefits
        </Button>
      ></Card.Header>
      <Card.Divider />
      <SelectableAccordion
        verticalPadding="medium"
        type="checkbox"
        items={[
          {
            title: 'Bookings Services',
            subtitle:
              'Offer services as a membership or package with this plan.',
            content: (
              <Layout cols={3}>
                <FormField label="Total sessions">
                  <Dropdown
                    initialSelectedId={0}
                    options={[{ id: 0, value: 'Limited number' }]}
                  />
                </FormField>
                <FormField label="Amount">
                  <NumberInput
                    placeholder="0"
                    suffix={<Input.Affix>sessions</Input.Affix>}
                  />
                </FormField>
                <FormField label="Period">
                  <Dropdown
                    initialSelectedId={0}
                    options={[{ id: 0, value: 'per billing cycle' }]}
                  />
                </FormField>
              </Layout>
            ),
          },
          {
            title: 'Online Programs',
            subtitle:
              'Allow participation in different programs with this plan.',
            content: (
              <FormField label="Select online programs">
                <MultiSelectCheckbox
                  placeholder="Select"
                  options={[
                    { value: 'Fitness 2023', id: 'Fitness2023' },
                    { value: 'Getting fit is easy', id: 'GettingFitIsEasy' },
                    { value: 'Fitness for newbies', id: 'FitnessForNewbies' },
                    { value: 'Fit mom at home', id: 'FitMomAtHome' },
                    {
                      value: 'Advanced fitness at home',
                      id: 'AdvancedFitnessAtHome',
                    },
                  ]}
                  selectedOptions={selectedOptions}
                  onSelect={(option) =>
                    setSelectedOptions([...selectedOptions, option])
                  }
                  onDeselect={(option) =>
                    setSelectedOptions(
                      selectedOptions.filter((item) => item !== option),
                    )
                  }
                  popoverProps={{ appendTo: 'window' }}
                />
              </FormField>
            ),
          },
        ]}
      />
    </Card>
  );
};
```


