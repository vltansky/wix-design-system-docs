
## Feature Examples


### Type
- description: <p>Control the type of selection users can make with the <code>multiple</code> prop:</p><li><code>false</code> allows users to select a single item only.  </li><li><code>true</code> allows users to select multiple items.  </li>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Item`,
          },
          {
            id: 2,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <SelectorList dataSource={data} />
      <SelectorList dataSource={data} multiple />
    </StorybookComponents.Stack>
  );
};
```

### Item structure
- description: <p>Add more elements to the list items with the following props:  </p><li><code>image</code>  </li><li><code>title</code> (required)</li><li><code>subtitle</code> </li><p></p><p>To add additional text or other components to items, use container props.</p><li><code>subtitleNode</code> shows content below the item subtitle.</li><li><code>extraNode</code> shows content at the end of an item.</li>
- example: 
```jsx 
() => {
  const plainData = [
    {
      id: 0,
      title: `Title`,
    },
    {
      id: 1,
      title: `Title`,
    },
    {
      id: 2,
      title: `Title`,
    },
  ];

  const dataWithImage = [
    {
      id: 0,
      title: `Title`,
      subtitle: 'Subtitle',
      extraNode: (
        <StorybookComponents.Placeholder>
          Extra node
        </StorybookComponents.Placeholder>
      ),
      image: <Image width="100%" height="100%" />,
      subtitleNode: (
        <StorybookComponents.Placeholder>
          Subtitle node
        </StorybookComponents.Placeholder>
      ),
    },
    {
      id: 1,
      title: `Title`,
      subtitle: 'Subtitle',
      extraNode: (
        <StorybookComponents.Placeholder>
          Extra node
        </StorybookComponents.Placeholder>
      ),
      image: <Image width="100%" height="100%" />,
      subtitleNode: (
        <StorybookComponents.Placeholder>
          Subtitle node
        </StorybookComponents.Placeholder>
      ),
    },
    {
      id: 2,
      title: `Title`,
      subtitle: 'Subtitle',
      extraNode: (
        <StorybookComponents.Placeholder>
          Extra node
        </StorybookComponents.Placeholder>
      ),
      image: <Image width="100%" height="100%" />,
      subtitleNode: (
        <StorybookComponents.Placeholder>
          Subtitle node
        </StorybookComponents.Placeholder>
      ),
    },
  ];

  const dataWithNode = [
    {
      id: 0,
      title: `Coffee shop 1`,
      subtitle: 'Main street 1',
      extraNode: <Text secondary>2 tables available</Text>,
      image: <Image width="100%" height="100%" src="FoodExample4.jpg" />,
      subtitleNode: (
        <Box direction="horizontal" gap="1" paddingTop="SP1" color="D30">
          <Tooltip content="Table seating">
            <Icons.TableReservationSmall />
          </Tooltip>
          <Tooltip content="Bar">
            <Icons.BarSmall />
          </Tooltip>
        </Box>
      ),
    },
    {
      id: 1,
      title: `Coffee shop 2`,
      subtitle: 'Main street 2',
      extraNode: <Text secondary>7 tables available</Text>,
      image: <Image width="100%" height="100%" src="FoodExample1.jpg" />,
      subtitleNode: (
        <Box direction="horizontal" gap="1" paddingTop="SP1" color="D30">
          <Tooltip content="Table seating">
            <Icons.TableReservationSmall />
          </Tooltip>
        </Box>
      ),
    },
    {
      id: 2,
      title: `Coffee shop 3`,
      subtitle: 'Main street 2',
      extraNode: <Text secondary>1 table available</Text>,
      image: <Image width="100%" height="100%" src="FoodExample5.jpg" />,
      subtitleNode: (
        <Box direction="horizontal" gap="1" paddingTop="SP1" color="D30">
          <Tooltip content="Table seating">
            <Icons.TableReservationSmall />
          </Tooltip>
          <Tooltip content="Bar">
            <Icons.BarSmall />
          </Tooltip>
        </Box>
      ),
    },
  ];

  const getDataSource = data => (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const filtered = data.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <SelectorList dataSource={getDataSource(plainData)} />
      <SelectorList dataSource={getDataSource(dataWithImage)} />
      <SelectorList dataSource={getDataSource(dataWithNode)} />
    </StorybookComponents.Stack>
  );
};
```

### Image shape
- description: <p>Control shape of the images with the <code>imageShape</code> prop:</p><li><code>rectangular</code>is the default that's used for all common cases.  </li><li><code>circle</code> is for images that show users or user initials.</li>
- example: 
```jsx 
() => {
  const rectangularData = [
    {
      id: 0,
      title: `Rectangular (default)`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Rectangular (default)`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Rectangular (default)`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const circleData = [
    {
      id: 0,
      title: `Circle`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Circle`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Circle`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const getDataSource = data => (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const filtered = data.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <SelectorList dataSource={getDataSource(rectangularData)} />
      <SelectorList
        dataSource={getDataSource(circleData)}
        imageShape="circle"
      />
    </StorybookComponents.Stack>
  );
};

```

### Image size
- description: <p>Change the size of the images with <code>imageSize</code> props:</p><li><code>tiny</code> is for especially dense layouts.</li><li><code>small</code> is for dense layouts.</li><li><code>large</code> is the default for all common cases.</li><li><code>portrait</code> should be used to present images vertically.</li><li><code>cinema</code> should be used to present images horizontally.</li><p></p><p>Note: Only use a <code>rectangular</code> image when the size is <code>portrait</code> or <code>cinema</code>.</p>
- example: 
```jsx 
() => {
  const tinyImageData = [
    {
      id: 0,
      title: `Tiny`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Tiny`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Tiny`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const smallImageData = [
    {
      id: 0,
      title: `Small`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Small`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Small`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const largeImageData = [
    {
      id: 0,
      title: `Large (default)`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Large (default)`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Large (default)`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const portraitImageData = [
    {
      id: 0,
      title: `Portrait`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Portrait`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Portrait`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const cinemaImageData = [
    {
      id: 0,
      title: `Cinema`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 1,
      title: `Cinema`,
      image: <Image weight="100%" height="100%" />,
    },
    {
      id: 2,
      title: `Cinema`,
      image: <Image weight="100%" height="100%" />,
    },
  ];

  const getDataSource = data => (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const filtered = data.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <SelectorList
        dataSource={getDataSource(tinyImageData)}
        imageSize="tiny"
      />
      <SelectorList
        dataSource={getDataSource(smallImageData)}
        imageSize="small"
      />
      <SelectorList
        dataSource={getDataSource(largeImageData)}
        imageSize="large"
      />
      <SelectorList
        dataSource={getDataSource(portraitImageData)}
        imageSize="portrait"
      />
      <SelectorList
        dataSource={getDataSource(cinemaImageData)}
        imageSize="cinema"
      />
    </StorybookComponents.Stack>
  );
};

```

### Height
- description: <p>Control the height of the selector list with these props:</p><li><code>height</code> changes the component's height in pixels or percentage.</li><li><code>maxHeight</code> sets the component's max height in pixels or percentage.</li><p></p><p>By default, the component fills in 100% of its parent container. If the selector list is longer than <code>height</code> or <code>maxHeight</code> , a vertical scrollbar appears.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Item`,
          },
          {
            id: 3,
            title: `Item`,
          },
          {
            id: 4,
            title: `Item`,
          },
          {
            id: 5,
            title: `Item`,
          },
          {
            id: 6,
            title: `Item`,
          },
          {
            id: 7,
            title: `Item`,
          },
          {
            id: 8,
            title: `Item`,
          },
          {
            id: 9,
            title: `Item`,
          },
          {
            id: 10,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return (
    <StorybookComponents.Stack flexDirection="line">
      <SelectorList dataSource={data} height="240px"></SelectorList>
      <SelectorList dataSource={data} maxHeight="360px"></SelectorList>
    </StorybookComponents.Stack>
  );
};
```

### Disabled item
- description: <p>Mark a list item as unavailable for selection with the <code>disabled</code> prop.</p><p></p><p>The item will still be displayed in the list and search results.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Disabled item`,
            disabled: true,
          },
          {
            id: 2,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return <SelectorList dataSource={data} />;
};
```

### Subtitle
- description: <p>Add any component inside a <code>subtitle</code> container above the search input. Together with search input, they will stick to the top when users scroll the list.</p><p></p><p>Use this container to add text, a heading or filter to selector list items.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Item`,
          },
          {
            id: 2,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return (
    <SelectorList
      dataSource={data}
      subtitle=<StorybookComponents.Placeholder>
        Subtitle
      </StorybookComponents.Placeholder>
    />
  ); 
};
```

### Search
- description: <p>The selector list has a search input field by default. Control its visibility using <code>withSearch</code> prop.</p><p></p><p>Change the search placeholder value with <code>searchPlaceholder</code> prop.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Item`,
          },
          {
            id: 2,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <StorybookComponents.Stack flexDirection="column">
      <SelectorList dataSource={data} withSearch={false} />
      <SelectorList
        dataSource={data}
        searchPlaceholder="Custom placeholder"
      />
    </StorybookComponents.Stack>
  );
};
```

### Select or deselect all
- description: <p>Allow users to select all items at once by adding a “Select all” checkbox below the list.</p><p></p><p>When the selector list is inside a <code><CustomModalLayout/></code>, add the checkbox to its footer <code>sideActions</code> container using the <code>renderToggleAllCheckbox</code> function.</p><p></p><p>Customize checkbox labels with the properties <code>selectAllText</code> and <code>deselectAllText</code>.</p><p></p><p>Note: Make sure the “Select all” checkbox is aligned with the list checkboxes by wrapping <code>renderToggleAllCheckbox</code> function to the <code><Box/></code> with 6 px left padding.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Item`,
          },
          {
            id: 2,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return (
    <StorybookComponents.Stack flexDirection="column">
      <SelectorList dataSource={data} multiple>
        {({ renderList, renderToggleAllCheckbox, selectedItems }) => (
          <CustomModalLayout
            title="Import items"
            primaryButtonText="Import"
            secondaryButtonText="Cancel"
            onCloseButtonClick={() => {}}
            removeContentPadding
            showFooterDivider
            showHeaderDivider
            sideActions=<Box paddingLeft="1">{renderToggleAllCheckbox()}</Box>
          >
            {renderList()}
          </CustomModalLayout>
        )}
      </SelectorList>
      <SelectorList
        dataSource={data}
        multiple
        selectAllText="Select all"
        deselectAllText="Deselect all from importing"
      >
        {({ renderList, renderToggleAllCheckbox, selectedItems }) => (
          <CustomModalLayout
            title="Import items"
            primaryButtonText="Import"
            secondaryButtonText="Cancel"
            onCloseButtonClick={() => {}}
            removeContentPadding
            showFooterDivider
            showHeaderDivider
            sideActions=<Box paddingLeft="1">{renderToggleAllCheckbox()}</Box>
          >
            {renderList()}
          </CustomModalLayout>
        )}
      </SelectorList>
    </StorybookComponents.Stack>
  );
};
```

### Below node
- description: <p>Add text or any other component to the container below each item using the <code>belowNode</code> prop, which shows once an item is selected. Be sure to set the <code>showBelowNodeOnSelect</code> property to <code>true</code>.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
            belowNode: (
              <StorybookComponents.Placeholder>
                Below node
              </StorybookComponents.Placeholder>
            ),
            showBelowNodeOnSelect: true,
            selected: true,
          },
          {
            id: 1,
            title: `Item`,
            belowNode: (
              <StorybookComponents.Placeholder>
                Below node
              </StorybookComponents.Placeholder>
            ),
            showBelowNodeOnSelect: true,
          },
          {
            id: 2,
            title: `Item`,
            belowNode: (
              <StorybookComponents.Placeholder>
                Below node
              </StorybookComponents.Placeholder>
            ),
            showBelowNodeOnSelect: true,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return <SelectorList dataSource={data} />;
};
```

### No items empty state
- description: <p>Use <code>emptyState</code> prop to display the <code><EmptyState/></code> component in the <code>section</code> theme when there are no items show.<a href="https://www.wix-style-react.com/storybook/?path=/story/components-layout--emptystate"></a></p><p></p><p>Make sure the illustration reflects the type of items the list should contain.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <SelectorList
      dataSource={data}
      imageSize="small"
      emptyState=<Box height="280px" align="center" verticalAlign="middle">
        <EmptyState
          image="EmptyState_Generic1.svg"
          title="Add your first meal"
          subtitle="Start getting orders by adding meals to your menu."
        >
          <TextButton prefixIcon={<Icons.Add />}>Add Meal</TextButton>
        </EmptyState>
      </Box>
    >
      {({ renderList }) => (
        <CustomModalLayout
          title="Edit menu"
          primaryButtonText="Save"
          secondaryButtonText="Cancel"
          onCloseButtonClick={() => {}}
          removeContentPadding
          showFooterDivider
          showHeaderDivider
        >
          {renderList()}
        </CustomModalLayout>
      )}
    </SelectorList>
  );
};
```

### No search results empty state
- description: <p>Provide an empty state when users look for content via search query and no items match their criteria using the <code>renderNoResults</code> function and the <code><EmptyState/></code> in the <code>section</code> theme.</p><p></p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Item`,
          },
          {
            id: 1,
            title: `Item`,
          },
          {
            id: 2,
            title: `Item`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return (
    <SelectorList
      dataSource={data}
      multiple
      renderNoResults={() => (
        <Box height="280px" align="center" verticalAlign="middle">
          <EmptyState
            image="EmptyState_Generic2.svg"
            title="No results found"
            subtitle="No items match your search criteria. Try to search by another keyword."
          >
            <TextButton>Clear Search</TextButton>
          </EmptyState>
        </Box>
      )}
    >
      {({ renderList }) => (
        <CustomModalLayout
          title="Import items"
          primaryButtonText="Import"
          secondaryButtonText="Cancel"
          onCloseButtonClick={() => {}}
          removeContentPadding
          showFooterDivider
          showHeaderDivider
        >
          {renderList()}
        </CustomModalLayout>
      )}
    </SelectorList>
  );
};
```




## Developer Examples


### Number of items to load
- description: <p>Control the number of items that load with two properties:</p><li><code>initialAmountToLoad</code> is the number of items loaded after a search.</li><li><code>itemsPerPage</code> is the number of items that load each consecutive time a user scrolls down to the end of the list. The default is 50.</li><p></p><p>If not specified, <code>initialAmountToLoad</code> will be the same as <code>itemsPerPage</code>.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = Array(50)
          .fill(0)
          .map((_, i) => ({
            id: i,
            title: `Item ${i + 1}`,
          }));

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return (
    <CustomModalLayout
      height="480px"
      title="Select item"
      primaryButtonText="Select"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => {}}
      removeContentPadding
      showHeaderDivider
      showFooterDivider
    >
      <SelectorList
        itemsPerPage={15}
        initialAmountToLoad={10}
        dataSource={data}
      />
    </CustomModalLayout>
  );
};
```


    


## Common Use Case Examples


### Single selection
- description: <p>Use the selector list to load and display a set of items.</p><p></p><p>If the anticipated number of items is small, hide the default search input field.</p><p></p><p>Use the <code>subtitle</code>, <code>subtitleNode</code> or <code>extraNode</code> containers to explain why an item is unavailable for selection.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Training`,
            subtitle: `3 posts`,
            extraNode: <Text secondary>Current category</Text>,
            disabled: true,
          },
          {
            id: 1,
            title: `Championships`,
            subtitle: `3 posts`,
          },
          {
            id: 3,
            title: `Inventory`,
            subtitle: `21 post`,
          },
          {
            id: 4,
            title: `Trainers`,
            subtitle: `18 posts`,
          },
          {
            id: 5,
            title: `Teams`,
            subtitle: `2 posts`,
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );

  return (
    <CustomModalLayout
      primaryButtonText="Move Post"
      secondaryButtonText="Cancel"
      onCloseButtonClick={() => setShown(false)}
      title="Move post to a category"
      removeContentPadding
      showFooterDivider
      showHeaderDivider
      width="600px"
    >
      <SelectorList dataSource={data} withSearch={false} />
    </CustomModalLayout>
  );
};
```

### Multiple selection
- description: <p>Use the selector list to search and select multiple items.</p><p></p><p>Allow users to select and deselect all items at once using the <code>renderToggleAllCheckbox</code> function.</p>
- example: 
```jsx 
() => {
  const data = (searchQuery, offset, limit) =>
    new Promise(resolve =>
      setTimeout(() => {
        const items = [
          {
            id: 0,
            title: `Science Expert`,
            subtitle: `Monaco, Monaco`,
            extraNode: <Text secondary>$77/h</Text>,
            image: (
              <Avatar
                name="Science Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 1,
            title: `Yoga Expert`,
            subtitle: `New Delhi, India`,
            extraNode: <Text secondary>$78/h</Text>,
            image: (
              <Avatar
                name="Yoga Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 3,
            title: `History Expert`,
            subtitle: `Singapore, Singapore`,
            extraNode: <Text secondary>$52/h</Text>,
            image: (
              <Avatar
                name="History Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 4,
            title: `Statistics Expert`,
            subtitle: `Abidjan, Ivory Coast`,
            extraNode: <Text secondary>$80/h</Text>,
            image: (
              <Avatar
                name="Statistics Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 5,
            title: `Soccer Expert`,
            subtitle: `Tokyo, Japan`,
            extraNode: <Text secondary>$200/h</Text>,
            image: (
              <Avatar
                name="Soccer Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 6,
            title: `Culinary Expert`,
            subtitle: `Sydney, Australia`,
            extraNode: <Text secondary>$102/h</Text>,
            image: (
              <Avatar
                name="Culinary Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 7,
            title: `Design Expert`,
            subtitle: `Baku, Azerbaijan`,
            extraNode: <Text secondary>$75/h</Text>,
            image: (
              <Avatar
                name="Design Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 8,
            title: `SEO Expert`,
            subtitle: `San Francisco, United States`,
            extraNode: <Text secondary>$115/h</Text>,
            image: (
              <Avatar
                name="SEO Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 9,
            title: `Painting Expert`,
            subtitle: `Seoul, South Korea`,
            extraNode: <Text secondary>$65/h</Text>,
            image: (
              <Avatar
                name="Painting Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 10,
            title: `Health Expert`,
            subtitle: `Paris, France`,
            extraNode: <Text secondary>$160/h</Text>,
            image: (
              <Avatar
                name="Health Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 11,
            title: `Writing Expert`,
            subtitle: `Oklahoma City, United States`,
            extraNode: <Text secondary>$90/h</Text>,
            image: (
              <Avatar
                name="Writing Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 12,
            title: `Painting Expert`,
            subtitle: `Phoenix, Arizona, United States`,
            extraNode: <Text secondary>$80/h</Text>,
            image: (
              <Avatar
                name="Painting Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 13,
            title: `Meditation Expert`,
            subtitle: `Belgrade, Serbia`,
            extraNode: <Text secondary>$64/h</Text>,
            image: (
              <Avatar
                name="Meditation Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 14,
            title: `Career Expert`,
            subtitle: `Tokyo, Japan`,
            extraNode: <Text secondary>$130/h</Text>,
            image: (
              <Avatar
                name="Career Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
          {
            id: 15,
            title: `Sales Expert`,
            subtitle: `Bangkok, Thailand`,
            extraNode: <Text secondary>$75/h</Text>,
            image: (
              <Avatar
                name="Sales Expert"
                size="size60"
                imgProps={{ src: 'NotFoundImage.jpg' }}
              />
            ),
          },
        ];

        const filtered = items.filter(({ title }) =>
          title.toLowerCase().includes(searchQuery.toLowerCase()),
        );

        resolve({
          items: filtered.slice(offset, offset + limit),
          totalCount: filtered.length,
        });
      }, 2000),
    );
  return (
    <SelectorList itemsPerPage={10} dataSource={data} multiple>
      {({ renderList, renderToggleAllCheckbox, selectedItems }) => (
        <CustomModalLayout
          width="600px"
          height="480px"
          title="Select experts"
          primaryButtonText="Select"
          secondaryButtonText="Cancel"
          onCloseButtonClick={() => {}}
          removeContentPadding
          showFooterDivider
          showHeaderDivider
          sideActions=<Box paddingLeft="1">{renderToggleAllCheckbox()}</Box>
        >
          {renderList()}
        </CustomModalLayout>
      )}
    </SelectorList>
  );
};
```


