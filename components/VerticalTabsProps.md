
### children
- type: ReactNode
- description: Child nodes of this component must be of type &lt;code&gt;&lt;VerticalTabs.TabsGroup&gt;&lt;/code&gt; or &lt;code&gt;&lt;VerticalTabs.Footer&gt;&lt;/code&gt;
### size
- type: VerticalTabsSize
- description: Text Size (tiny, small, medium)
### activeTabId
- type: string | number
- description: Current selected tab id
### onChange
- type: (id: TabId) =&gt; void
- description: Callback function called on tab selection change with the following parameters&lt;code&gt;(id)&lt;/code&gt;
### dataHook
- type: string
- description: Data attribute for testing purposes
### skin
- type: ValuesOf&lt;{ readonly LIGHT: &#34;light&#34;; readonly NEUTRAL: &#34;neutral&#34;; readonly STANDARD: &#34;standard&#34;; }&gt;
- description: Specifies the skin of a TabItem.


