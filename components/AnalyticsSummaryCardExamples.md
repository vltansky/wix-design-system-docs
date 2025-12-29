
## Feature Examples


### Footer
- description: <p>Add additional information to a card with <code>footer</code>. </p>
- example: 
```jsx 
<AnalyticsSummaryCard
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  onChartHover={() => console.log('on chart hover')}
  title="Sessions"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
  value="1,9K"
  footer={
    <div>
      <div>
        <Text>This is footer text </Text>
      </div>
      <div>
        <Button size="tiny">Click Here </Button>
      </div>
    </div>
  }
/>;
```

### Trend
- description: <p>The <code>trend</code> indicates the change of the value in percentage. </p><p></p><p>It has 2 modes: </p><li><strong>Positive</strong> - colored green with arrow upwards </li><li><strong>Negative</strong> - colored red with arrow downwards. </li><p></p><p>If there’s no change in value, trend won’t be displayed.</p>
- example: 
```jsx 
<div>
  <div>
    <AnalyticsSummaryCard
      chartColorHex="#3899ec"
      chartData={[
        {
          label: new Date('2020-09-03T21:00:00.000Z'),
          value: 100,
        },
        {
          label: new Date('2020-09-04T21:00:00.000Z'),
          value: 17,
        },
        {
          label: new Date('2020-09-05T21:00:00.000Z'),
          value: 18,
        },
      ]}
      chartWidth={169}
      onChartHover={() => console.log('on chart hover')}
      trend={12}
      isTrendVisible={true}
      title="Sessions"
      getChartTooltipContent={(index) => (
        <span style={{ color: '#ffffff' }}>{index}</span>
      )}
      value="1,9K"
    />
  </div>
  <br />
  <br />
  <div>
    <AnalyticsSummaryCard
      chartColorHex="#3899ec"
      chartData={[
        {
          label: new Date('2020-09-03T21:00:00.000Z'),
          value: 100,
        },
        {
          label: new Date('2020-09-04T21:00:00.000Z'),
          value: 17,
        },
        {
          label: new Date('2020-09-05T21:00:00.000Z'),
          value: 18,
        },
      ]}
      chartWidth={169}
      onChartHover={() => console.log('on chart hover')}
      trend={-12}
      isTrendVisible={true}
      title="Sessions"
      getChartTooltipContent={(index) => (
        <span style={{ color: '#ffffff' }}>{index}</span>
      )}
      value="1,9K"
    />
  </div>
</div>;
```

### Action Button
- description: <p>Summary card can have action button inside to assist with any action needed, since it’s a <code>node</code>.</p>
- example: 
```jsx 
<AnalyticsSummaryCard
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  ctaButton={
    <IconButton size="tiny" priority="secondary">
      <Icons.Refresh />
    </IconButton>
  }
  onCTAClick={() => console.log('refresh click')}
  onChartHover={() => console.log('on chart hover')}
  title="Sessions"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
  value="1,9K"
/>;
```

### Clickable Card
- description: <p>Control is a card is clickable with <code>onClick</code>. </p>
- example: 
```jsx 
<div>
  <div>
    <AnalyticsSummaryCard
      chartColorHex="#3899ec"
      chartData={[
        {
          label: new Date('2020-09-03T21:00:00.000Z'),
          value: 100,
        },
        {
          label: new Date('2020-09-04T21:00:00.000Z'),
          value: 17,
        },
        {
          label: new Date('2020-09-05T21:00:00.000Z'),
          value: 18,
        },
      ]}
      chartWidth={169}
      onChartHover={() => console.log('on chart hover')}
      onClick={() => console.log('general click')}
      title="Clickable card"
      getChartTooltipContent={(index) => (
        <span style={{ color: '#ffffff' }}>{index}</span>
      )}
      value="1,9K"
    />
  </div>
  <br />
  <br />
  <div>
    <AnalyticsSummaryCard
      chartColorHex="#3899ec"
      chartData={[
        {
          label: new Date('2020-09-03T21:00:00.000Z'),
          value: 100,
        },
        {
          label: new Date('2020-09-04T21:00:00.000Z'),
          value: 17,
        },
        {
          label: new Date('2020-09-05T21:00:00.000Z'),
          value: 18,
        },
      ]}
      chartWidth={169}
      onChartHover={() => console.log('on chart hover')}
      title="Not interactive card (default)"
      getChartTooltipContent={(index) => (
        <span style={{ color: '#ffffff' }}>{index}</span>
      )}
      value="1,9K"
    />
  </div>
</div>;
```

### Loader
- description: <p>Card supports loading state. <Loader/> will replace the action button when it’s actively loading. If the card is clickable it won’t be actionable as long as the loader is active.</p>
- example: 
```jsx 
<AnalyticsSummaryCard
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  onChartHover={() => console.log('on chart hover')}
  title="Sessions"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
  isLoading={true}
  value="1,9K"
/>;
```

### Sparkline Width
- description: <p>Control the sparkline width by pixels with <code>chartWidth</code> prop.</p>
- example: 
```jsx 
<AnalyticsSummaryCard
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={69}
  title="Sessions"
  value="1,9K"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
/>;
```

### Border
- description: <p>Control the appearance of the component using the <code>border</code> prop.</p><p></p><p>Use this property to emphasize the separation between items.</p>
- example: 
```jsx 
<div>
  <div>
    <AnalyticsSummaryCard
      border
      chartColorHex="#3899ec"
      chartData={[
        {
          label: new Date('2020-09-03T21:00:00.000Z'),
          value: 100,
        },
        {
          label: new Date('2020-09-04T21:00:00.000Z'),
          value: 17,
        },
        {
          label: new Date('2020-09-05T21:00:00.000Z'),
          value: 18,
        },
      ]}
      chartWidth={169}
      onChartHover={() => console.log('on chart hover')}
      trend={12}
      isTrendVisible={true}
      title="With border"
      getChartTooltipContent={(index) => (
        <span style={{ color: '#ffffff' }}>{index}</span>
      )}
      value="1,9K"
    />
  </div>
  <br />
  <br />
  <div>
    <AnalyticsSummaryCard
      chartColorHex="#3899ec"
      chartData={[
        {
          label: new Date('2020-09-03T21:00:00.000Z'),
          value: 100,
        },
        {
          label: new Date('2020-09-04T21:00:00.000Z'),
          value: 17,
        },
        {
          label: new Date('2020-09-05T21:00:00.000Z'),
          value: 18,
        },
      ]}
      chartWidth={169}
      onChartHover={() => console.log('on chart hover')}
      trend={-12}
      isTrendVisible={true}
      title="Without border"
      getChartTooltipContent={(index) => (
        <span style={{ color: '#ffffff' }}>{index}</span>
      )}
      value="1,9K"
    />
  </div>
</div>;
```

### Horizontal padding
- description: <p>Control the padding of the card with <code>horizontalPadding</code> prop.</p><p></p><p>It supports three sizes:</p><li><code>large</code> (default)</li><li><code>medium</code></li><li><code>small</code> </li>
- example: 
```jsx 
<StorybookComponents.Stack flexDirection="column" gap="40px">
<AnalyticsSummaryCard
  horizontalPadding="large"
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  ctaButton={
    <IconButton size="tiny" priority="secondary">
      <Icons.Refresh />
    </IconButton>
  }
  onCTAClick={() => console.log('refresh click')}
  onChartHover={() => console.log('on chart hover')}
  title="Horizontal padding"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
  value="Large size"
/>
<AnalyticsSummaryCard
  horizontalPadding="medium"
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  ctaButton={
    <IconButton size="tiny" priority="secondary">
      <Icons.Refresh />
    </IconButton>
  }
  onCTAClick={() => console.log('refresh click')}
  onChartHover={() => console.log('on chart hover')}
  title="Horizontal padding"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
  value="Medium size"
/>
<AnalyticsSummaryCard
  horizontalPadding="small"
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  ctaButton={
    <IconButton size="tiny" priority="secondary">
      <Icons.Refresh />
    </IconButton>
  }
  onCTAClick={() => console.log('refresh click')}
  onChartHover={() => console.log('on chart hover')}
  title="Horizontal padding"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
  value="Small size"
/>
</StorybookComponents.Stack>;
```




## Developer Examples


### Tooltip On Title
- description: <p>If needed, the title can have <code><Tooltip/></code> to better explain the context.</p>
- example: 
```jsx 
<AnalyticsSummaryCard
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  title="Sessions"
  value="1,9K"
  titleTooltip="Site Sessions in your site. A session is a set of interactions made by visitors"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
/>;
```

### Tooltip On Value
- description: <p>When value appears as abbreviated number, <Tooltip/> will appear on hover.</p>
- example: 
```jsx 
<AnalyticsSummaryCard
  chartColorHex="#3899ec"
  chartData={[
    {
      label: new Date('2020-09-03T21:00:00.000Z'),
      value: 100,
    },
    {
      label: new Date('2020-09-04T21:00:00.000Z'),
      value: 17,
    },
    {
      label: new Date('2020-09-05T21:00:00.000Z'),
      value: 18,
    },
  ]}
  chartWidth={169}
  title="Sessions"
  value="1,9K"
  valueTooltip="1,951"
  getChartTooltipContent={(index) => (
    <span style={{ color: '#ffffff' }}>{index}</span>
  )}
/>;
```


    


