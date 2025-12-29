
    ### Accordion
    - description: <p>Accordion is a list of items that shows and hides content in collapsible sections.</p>
    - do: Use it to organize content by grouping it into collapsible sections.,Use it to show information on user demand only.
    - donts: No donts

    ### AddItem
    - description: <p>Add item component allows users to add a new item to an existing list.</p>
    - do: Use it to add a new item to the list.,Use it together with <FileUpload/> mechanism to add a new file to a list.
    - donts: No donts

    ### AddressInput
    - description: Address input allows users to enter a location address. This component provides UI definition only and requires an address provider to be specified from the product side.
    - do: Use it to search for a location.,Use it to enter addresses that must be validated before they are submitted.,Use it as a UI element together with a required address provider passed from the side.
    - donts: No donts

    ### AddressInputItem
    - description: Address Input Item is an internal component that displays address list item in a dropdown selection. It’s mainly used as a part of the `<AddressInput/>` component.
    - do: Use it to represent address selection items.
    - donts: No donts

    ### AnalyticsLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### AnalyticsSummaryCard
    - description: <p>Analytics Summary Card component provides a concise overview of key metrics, helping users quickly understand performance insights at a glance.</p>
    - do: Use short labels that are easy to read.,Use it together with < AnalyticsLayout/> to control the layout.
    - donts: No donts

    ### AngleInput
    - description: <p>Angle input enables users select an angle degree value.</p>
    - do: Use it to adjust settings, such as shadow or rotation.,Use angle input with <NumberInput /> to indicate to value and give users the option to type the value manually.
    - donts: No donts

    ### AnnouncementModalLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### AreaChart
    - description: No description
    - do: No do
    - donts: No donts

    ### AtlasAddressInput
    - description: <p>AtlasAddressInput allows users to search for an address with a built-in autocomplete service.</p><p></p><p>To use this component you must install the following peer-dependencies:</p><p><code>npm install</code> <code>@wix/ambassador</code> <code>@wix/ambassador-wix-atlas-service-web</code></p>
    - do: Use it as a built-in solution for a location search.,Use it to enter addresses that must be validated before submitting.
    - donts: No donts

    ### AudioPlayer
    - description: <p>Audio player lets users play an uploaded audio file.</p>
    - do: Use it to play audio files, such as songs or voice messages.
    - donts: No donts

    ### AutoComplete
    - description: <p>Autocomplete allows users to select a single item from a predefined list of options. Users can type into the input field to filter the list.</p>
    - do: Use it to select an item from a list with 10 or more options.,Use it with user-generated data (e.g., a staff member list, custom categories, labels, products, etc.)
    - donts: No donts

    ### AutoCompleteWithLabel
    - description: AutoCompleteWithLabel allows users to select a single item from a predefined list of options. This component provides an editable input field for filtering the list and a built-in label.
    - do: Use it in Wix Premium checkout form.
    - donts: No donts

    ### Avatar
    - description: Avatar visually represents a user or an organization either as an image, text (name initials) or a placeholder image.
    - do: Use it in circle shape to represent a user.,Use it in square shape to represent an organization.
    - donts: No donts

    ### AvatarGroup
    - description: AvatarGroup allows to display a number of avatars (digital representation of a user) as a single entity. It’s a building block grouping number of standalone `<Avatar/>` components.
    - do: Use it to display a group of 2+ users,Use it to display users that have something in common (i.e. belong to a project, are in the same team, attend the same event, etc.)
    - donts: No donts

    ### Badge
    - description: <p>A badge is a visual indicator that informs users about the status of an item or function. </p>
    - do: Use badges to show the status of an item or function.,Use short and clear text labels (1 - 2 words).
    - donts: No donts

    ### BadgeSelect
    - description: No description
    - do: No do
    - donts: No donts

    ### BadgeSelectItem
    - description: No description
    - do: No do
    - donts: No donts

    ### BarChart
    - description: No description
    - do: No do
    - donts: No donts

    ### BounceAnimation
    - description: No description
    - do: No do
    - donts: No donts

    ### Box
    - description: <p>A box is a container that allows the layout, alignment, spacing and style of its child elements. Boxes can wrap and apply CSS styles to one or more elements that are contained inside.</p>
    - do: Arrange elements vertically or horizontally.,Apply custom spacing and styles.,Build custom widgets.
    - donts: No donts

    ### Breadcrumbs
    - description: <p>Breadcrumbs show the page a user is on within the site hierarchy and let them navigate back.</p>
    - do: Use it in pages that are arranged in site hierarchy.,Add breadcrumbs to deeper level pages (i.e. second, third, etc.).,Use it when users navigate between folders or lists.
    - donts: No donts

    ### BrowserPreviewWidget
    - description: <p>Browser preview widget enables users to see how their site will look like when opened in a web browser.</p>
    - do: Use it to show how a user's site or other content will appear in a web browser.,Use it to show how user-controlled settings look like in a published website.
    - donts: No donts

    ### Button
    - description: <p>Buttons let users initiate actions, like saving changes, navigating or canceling. They’re used throughout the UI in various places like pages, widgets and modals.</p>
    - do: Use it to communicate primary and secondary actions users can take.
,Give secondary action buttons a different style to indicate their lower priority.
    - donts: No donts

    ### Calendar
    - description: Calendar component lets to pick a date while seeing the full month of days.  It’s used in `<DatePicker/>` component, but it can be used alone too.
    - do: Use it to show the list of available days to choose from,Use it if calendar needs to be prominent all the time,Use it to display multiple months at once
    - donts: No donts

    ### CalendarPanel
    - description: Calendar Panel component lets a user pick a date while providing a great overview of available selections.It’s built using `<Calendar/>` and `<CalendarPanelFooter/>` components. 
    - do: Use it when a wider view of available dates should be seen,Use it when needed to select recurring range of days, for example in charts,Use it when extra validation is needed before submitting the date selection
    - donts: No donts

    ### CalendarPanelFooter
    - description: Calendar panel footer is an internal component that is designed to layout submit actions for a date selector. It is used as a part of the `<CalendarPanel/>` component.
    - do: Use it as a fundamental part of <CalendarPanel/> to display submit actions and selected date
    - donts: No donts

    ### Card
    - description: <p>Cards are containers that group related content and actions.</p>
    - do: Display content on a single topic.,Make cards easy to scan for important information. 
    - donts: No donts

    ### CardFolderTabs
    - description: Card folder tabs allow users to organize content by a certain criteria in a card layout. 
    - do: Use it to distribute content within a card.,Use it to group card content by a specific criteria, such as status or type.  
    - donts: No donts

    ### CardGalleryItem
    - description: Card gallery item is an interactive component that allows users to display media content and actions related to it in a grid layout.
    - do: Use it to represent a content entity, such a blog post, product or event.,Use it to display content that users can interact with.,Use it to display content for grid layout.
    - donts: No donts

    ### Carousel
    - description: No description available
    - do: No do available
    - donts: No donts available

    ### CarouselWIP
    - description: No description
    - do: No do
    - donts: No donts

    ### CheckToggle
    - description: Check toggle allows users to make a binary choice between two states. It`s commonly used to mark a specific item as completed or not.
    - do: Use it to mark item as completed or not
    - donts: No donts

    ### Checkbox
    - description: <p>Checkboxes allows to select single or multiple items from a list of predefined options.</p>
    - do: Use it in forms to select one or multiple items from a list of options.,Use it when all options need to be displayed right away.,Use it when an explicit action is required to apply a setting, e.g., Agree to terms and conditions.
    - donts: No donts

    ### CircularProgressBar
    - description: <p>A circular progress bar indicates the percentage of completion for a task or process with a visual indication that fills a circular track.</p>
    - do: Use to indicate progress of a task that require a long time to complete (10 seconds and more).,Use to show users that their action is being processed. 
    - donts: No donts

    ### CloseButton
    - description: <p>Close button is an interactive element that allows users to exit an event.</p>
    - do: Use it to close pages, notifications, helpers, cards or menus.,Use one close button at a time.
    - donts: No donts

    ### Collapse
    - description: No description
    - do: No do
    - donts: No donts

    ### ColorInput
    - description: <p>Color input allows the user to select a color, either by using a visual color picker or by entering the HEX color code manually into the text field.</p>
    - do: Use it to specify a custom color for any item.
    - donts: No donts

    ### ColorPicker
    - description: Color picker allows users to select a color value by dragging the cursor inside of a color spectrum. It’s a popover that should be called out via `<ColorInput/>`, `<Button/>` or another component.
      It uses this color manipulation library: [https://github.com/Qix-/color](https://github.com/Qix-/color)
    - do: Use it to freely select any solid color.,Use it to show the full spectrum of available colors to select.
    - donts: No donts

    ### ComposerHeader
    - description: Composer header is a local navigation of a composer environment.
    - do: Use it to navigate within a composer.,Use it to display actions and data related to the composer environment, such as content state, undo actions, etc.
    - donts: No donts

    ### ComposerSidebar
    - description: Composer sidebar is a local navigation used to control the composer's settings panel.
    - do: Use it to list the categories of composer's <SidePanel/> settings.
    - donts: No donts

    ### ComposerButton
    - description: <p>Composer button as it's name suggest, is a custom button for composers tools and functions.</p>
    - do: Use it to describe a composer tool, action or a function.
    - donts: No donts

    ### CopyClipboard
    - description: No description
    - do: No do
    - donts: No donts

    ### CornerRadiusInput
    - description: <p>Corner radius inputs enable users to adjust the border radius for different elements, such as boxes or images.</p><p></p><p></p>
    - do: Use to edit border radius of elements.
    - donts: No donts

    ### CounterBadge
    - description: No description
    - do: No do
    - donts: No donts

    ### CustomModalLayout
    - description: <p>Custom modal layouts contain content like forms, lists, or media within a <code><Modal/></code> overlay.</p>
    - do: Use it to present a subtask, display more information or other custom content.,Use it after an intentional user action and only when it is completely necessary. Because they are intrusive, modals should be used sparingly.
    - donts: No donts

    ### ClickableCard
    - description: <p>Clickable Card is an interactive container that acts as a clickable surface. It can be used as a single image or contain a group of elements such as text, buttons, etc...</p>
    - do: Use it to create a card layout the interacts as a button
    - donts: No donts

    ### DatePicker
    - description: <p>Date pickers allow users to select or enter a specific date. It’s a combination of the <code><Input/></code>, <code><Calendar/></code> and <code><Popover/></code> components.</p>
    - do: Use it to select dates in the recent past or near future.,Make it easier to select dates far in the past or in the future with month and year selection in the calendar (e.g., when entering a birth date or expiration date).
    - donts: No donts

    ### Divider
    - description: <p>Dividers are thin lines that separate content, or groups it into clear sections. They act like visual punctuation marks and make web pages easier to read.</p>
    - do: Separate content in lists and layouts.,Use dividers to support visual hierarchy.
    - donts: No donts

    ### Drawer
    - description: <p>The <code><Drawer/></code> is a mobile‑first component used to display additional options, actions, or content without navigating away from the current screen. It slides up from the bottom of the viewport and is commonly used to expand dropdown lists on mobile, act as an action sheet when opened from popovers, or present any contextual content in a mobile experience.</p>
    - do: Use it for focused, short tasks - e.g choosing an option, confirming an action, quick edits,Allow easy dismissal - swipe down, close icon, tapping the overlay when safe,Keep content concise and scannable - prioritize primary actions and key information
    - donts: No donts

    ### Dropdown
    - description: <p>Dropdowns let users select a single item from a predefined list of options.</p>
    - do: Use when users can select a single item from 5 to 10 options.
    - donts: No donts

    ### DropdownBase
    - description: The DropdownBase is a mechanism that allows the user to open up a dropdown layout via a specified trigger element and return a selected value for it.
    - do: Use it to build custom filters.,Use it to build “sort by” actions.
    - donts: No donts

    ### DropdownLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### Dropzone
    - description: <p>Dropzone lets users drag and drop files to upload them in a specified area.</p>
    - do: Use it to upload files using drag and drop to a specified region.,Use it to upload single or multiple files.
    - donts: No donts

    ### EditableSelector
    - description: No description
    - do: No do
    - donts: No donts

    ### EditableTitle
    - description: <p>Editable title allows users to change a page title on the spot. It is used as a title inside of a <code><Page.Header/></code> component.</p>
    - do: Use it to let users give a title for a page (e.g., for a product, category or event detail page).,Use it as a part of a <PageHeader/>.
    - donts: No donts

    ### EmptyState
    - description: <p>An empty state is used when an app, page or section has no data to show. </p>
    - do: Show it when there's no data to display.,Use it to give feedback when no search results are available.,Use it when the page content fails to load or there's a technical error.
,Give an explanation and provide a next action.
    - donts: No donts

    ### FacesRatingBar
    - description: Faces rating bar allows you to rate an experience, such as an interview, a call with customer care or a doctor's appointment.
    - do: Use it to display the rating of an experience.,Use it to measure 'likability'.,Use it to collect feedback about experiences that involve interaction with other people.
    - donts: No donts

    ### FeatureList
    - description: Feature list allows users to promote a product or service by listing down the main features and benefits. It’s designed  to be used in `<MarketingPage/>` component.
    - do: Display it in a footer area of a <MarketingPage/>,Use it to list down product features or benefits
    - donts: No donts

    ### FieldSet
    - description: <p>A field set wraps a group of related components in a form, has a title (legend), and can include a tooltip for extra information.</p>
    - do: Use it to provide a short title for a group of related form components.,Use it to give a group title for screen reader users.,Provide additional information about the group in a tooltip.
    - donts: No donts

    ### FilePicker
    - description: The file picker allows users to upload a single file at a time. The component handles the file upload via the native file browser dialog, the validation and preview of an uploaded file.
    - do: Use it to upload text or media file,Use it to upload single file at a time
    - donts: No donts

    ### FileUpload
    - description: <p>File upload allows users to upload one or multiple files at once. This wrapper opens a native upload dialog box when the user clicks a trigger.</p>
    - do: Let users upload all types of text or media files.,Let users upload one or more files at once.,Use it to add a file type selection to existing components like <AddItem/>.
    - donts: No donts

    ### FillButton
    - description: Fill button allows to add a new color swatch to an existing list of options. It’s used as a building part for `<Swatches/>` component.
    - do: Use it to add a new swatch to the list of colors or gradients.,Use it to call out the color picker popover.,Use it to call out Media Manager to pick an image.
    - donts: No donts

    ### FillPreview
    - description: <p>A clickable preview for colors, gradients, images and vector graphics. Mainly used as a building part for <code><Swatches/></code> component, but can be used as a standalone item too.</p>
    - do: Use it to create a swatch of selectable colors, gradients or images.,Use it to list available style options for the fill.
    - donts: No donts

    ### FloatingHelper
    - description: No description
    - do: No do
    - donts: No donts

    ### FloatingNotification
    - description: <p>Notification informs users about the status change in application. Floating notification is used as a temporary overlay element or inline element within cards.</p>
    - do: Use it to provide contextual feedback on the outcome of user action.,Use it to notify users about a happened change in the application.,Display notifications inside modals as a temporary overlay.,Place as a section message first in the section that it applies to.
    - donts: No donts

    ### FormField
    - description: <p>Form fields are labels used to tell the user what they need to select or enter in the field of a form. They can indicate if a field is mandatory and can include a tooltip to provide more information.</p>
    - do: Use it to add a label to the field to tell the user what info they need to enter or select.,Mark required fields as mandatory.,Provide additional information about the form element in a tooltip.
    - donts: No donts

    ### FunnelChart
    - description: No description
    - do: No do
    - donts: No donts

    ### GoogleAddressInput
    - description: No description
    - do: No do
    - donts: No donts

    ### GooglePreview
    - description: Google preview allows users to preview how the website appears in Google search results. It is frequently used in SEO settings’ panels.
    - do: Use it to illustrate how a website appears on Google search results.,Use it to visualize changes in SEO settings.
    - donts: No donts

    ### Heading
    - description: <p>Headings are titles for the main sections of a page. They help users understand what a page or section is about at a glance. </p><p></p><p></p>
    - do: Use headings to describe each section on a page.,Keep the heading text short and clear.,Keep the entire heading text visible at all times. Make sure it doesn't get truncated with an ellipsis.,Follow a sequential, descending heading order, and do not skip levels.
    - donts: No donts

    ### Highlighter
    - description: No description
    - do: No do
    - donts: No donts

    ### HorizontalTimeline
    - description: HorizontalTimeline is used to demonstrate the progress of passive events that a person watching it has no effect on.
    - do: Use it to demonstrate the progress of server states.,Use it to show task SLA status.
    - donts: No donts

    ### HorizontalScroll
    - description: <p>HorizontalScroll is a mechanism that enable scroll for different components like Tabs, Buttons, Tags, etc...</p>
    - do: Use it to for interactive components.,Use it when there's not space to show all the items.
    - donts: No donts

    ### IconButton
    - description: <p>Icon buttons highlight actions that users can take, used in compact or crowded layouts.</p>
    - do: Add tooltip labels to icon buttons using a <Tooltip/>.,Only use icon buttons for low-emphasis actions.,Use them in compact or crowded layouts.,Make sure the meaning of the icons are simple and unambiguous.
    - donts: No donts

    ### Image
    - description: <p>Images communicate product information to users with visuals.  </p><p></p><p></p>
    - do: Use them to display images like product thumbnails.
    - donts: No donts

    ### ImageViewer
    - description: <p>Image viewers let users display images with built-in functions like upload, update and remove.</p>
    - do: Use them to upload images, such as event covers.,Use them to display images that can be updated or removed.
    - donts: No donts

    ### InfoIcon
    - description: <p>The <InfoIcon/> provides additional information when hovering over the icon. It’s used in multiple components, and sometimes by itself, next to various actions or features.</p>
    - do: Use it when features can be explained in one sentence.
    - donts: No donts

    ### Input
    - description: <p>Inputs let users enter short values into a text field. It can be used for forms and tables, or to build other form components like <AutoComplete/> or <NumberInput/>.</p>
    - do: Use it to insert names, titles, addresses, and other areas where users will enter short bits of text.,Use it to build custom input fields.
    - donts: No donts

    ### InputArea
    - description: <p>Input areas let users insert long text values. The large size of the field indicates that a user is expected to insert at least a few sentences.</p>
    - do: Use it to insert multiple lines of text.
    - donts: No donts

    ### InputShell
    - description: <p>Input shell is an atomic input component, it can replace the regular <Input /> or <Dropdown  /> components in cases where you need a value which is not a string. i.e. Font dropdown.</p>
    - do: Use <InputShell /> to preview non-string values.
    - donts: No donts

    ### InputWithLabel
    - description: InputWithLabel allows you to insert short text values in a field with a built-in label. It’s constructed by wrapping a regular `<Input/>` component with `<LabeledElement/>`.
    - do: Use it to insert text values in the Wix Premium checkout form.
    - donts: No donts

    ### InputWithOptions
    - description: No description
    - do: No do
    - donts: No donts

    ### Layout
    - description: <p>Layout is a wrapper component that allows users to arrange children items in a grid of columns and rows. It's based on the CSS grid.</p>
    - do: Use it to structure content inside of a <Page/> .,Use it to organize form fields inside of a <Card/> .
    - donts: No donts

    ### LinearProgressBar
    - description: No description
    - do: No do
    - donts: No donts

    ### ListItemAction
    - description: <p>ListItemAction component is used to build menu like components.</p>
    - do: Use it to build navigation menus
    - donts: No donts

    ### ListItemEditable
    - description: No description
    - do: No do
    - donts: No donts

    ### ListItemSection
    - description: <p> List item section allows you to group or divide list options or actions.</p>
    - do: Use it to build Dropdown, Multiselect, Search dropbox values or custom lists.
    - donts: No donts

    ### ListItemSelect
    - description: <p>List Item Select represents a single option of any select component. It's highly configurable and can appear in Dropdown, Multiselect or Search components.</p>
    - do: Use it to build Dropdown, Multiselect, Search dropbox values or custom lists.
    - donts: No donts

    ### ListItemSelectIcon
    - description: No description
    - do: No do
    - donts: No donts

    ### LiveRegion
    - description: <p>Live region is a mechanism that broadcasts a message for screen reader users to inform them about the change in the page layout or the status.</p>
    - do: Use it to inform users with visual impairments about change in page content,Use it to inform users with visual impairments about page status change without moving users' focus
    - donts: No donts

    ### Loader
    - description: <p>Loader is used to show users when an action is being processed.</p>
    - do: Use to show that the requested action has started and will be completed soon, like changes on a page being saved.,Use when task completion time is unknown.,Place in the vertical and horizontal center of a layout.
    - donts: No donts

    ### MarketingLayout
    - description: <p>Marketing layout is a standardized card-like layout for encouraging users to take an action. It is quicker and easier to use than a customizable card.</p>
    - do: Use it to promote existing features or products that users could benefit from.,Wrap it in a <Card/>, which provides a white background.
    - donts: No donts

    ### MarketingPageLayout
    - description: Marketing page layout presents a product and its key features for first time users.
    - do: Use it to onboard users during their first visit.,Use it to promote a product the user may not be aware of.
    - donts: No donts

    ### MarketingPageLayoutContent
    - description: Marketing page layout content is an internal component used to display content of `<MarketingPageLayout/>`.
    - do: Use it as a building part of <MarketingPage/>.,Use it to layout promotional content inside of a page.
    - donts: No donts

    ### MediaOverlay
    - description: Media overlay is a container that allows users to place any content on top of a media such as an image or a video.
    - do: Use it to place a badge, text or other content on top of a media.,Use it to reveal duration or other static data on media element hover.,Use it to reveal related actions on media element hover.
    - donts: No donts

    ### MessageBoxFunctionalLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### MessageBoxMarketerialLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### MessageModalLayout
    - description: <p>Message modals display short messages letting users confirm or cancel an action before moving forward. They're used inside <code><Modal/></code> overlays.</p><p></p>
    - do: Get confirmation before destructive or irreversible actions.,Update users about important changes, e.g., updated terms and conditions.,Inform users that selected features are Premium and upgrading is required.,Use it after an intentional user action and only when it is completely necessary. Because they are intrusive, modals should be used sparingly.
    - donts: No donts

    ### MobilePreviewWidget
    - description: No description
    - do: No do
    - donts: No donts

    ### Modal
    - description: <p>Modal is the overlay that appears as the background for all types of modal layouts. It is triggered by a user’s action and is a container for components like <code><CustomModalLayout/></code> and <code><MessageModalLayout/></code>.</p>
    - do: Use it as the background for all types of modal layouts.,Use it only when it is completely necessary. Because they are intrusive, modals should be used sparingly.
    - donts: No donts

    ### ModalMobileLayout
    - description: Use this component together with to display content in this layout. You may place a title and/or a footer with actions relevant to the displayed content.
    - do: No do
    - donts: No donts

    ### FullScreenModalLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### ModalPreviewLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### ModalSelectorLayout
    - description: No description
    - do: No do
    - donts: No donts

    ### MultiSelect
    - description: <p>Multiselect allows users to enter and display multiple keyword tags.</p>
    - do: Use it when the site owner needs to enter multiple keywords like names, emails, countries, etc.,Use it as a tag input.
    - donts: No donts

    ### MultiSelectCheckbox
    - description: MultiSelectCheckbox allows to select multiple items from a predefined list of options.
    - do: Use it to select multiple items from a list of options.,Use it as a filter for data sets.
    - donts: No donts

    ### NestableList
    - description: <p>Nestable lists let users sort their list items into sub-levels using drag and drop.</p>
    - do: Organize items into sub-levels and categories.,Create lists that users can add to.
    - donts: No donts

    ### NestableListBase
    - description: No description
    - do: No do
    - donts: No donts

    ### Notification
    - description: No description
    - do: No do
    - donts: No donts

    ### NumberInput
    - description: <p>Number inputs allow users to enter and edit numeric values in a single line input field. The value can be inserted using the keyboard or incremented using the arrow controls.</p>
    - do: Use it to enter custom numeric values, e.g., amount, price, quantity.,Use it to adjust values by a specific amount, e.g., the number of items in a shopping cart.
    - donts: No donts

    ### NavigationToast
    - description: No description
    - do: Provide a clear action that's explicit and guides user to the intended destination, e.g., "Go to Settings" or "Scroll back to top".,Only use the toast to direct users to environments or actions that are immediately relevant to their current context.,Use short, actionable text for the title and description.
    - donts: No donts

    ### Page
    - description: <p>Use the page component to build the structure of each page. It's designed for Business Manager applications but can be customized for other use cases too.</p>
    - do: Use it to build all standard Business Manager pages.,Customize it as you need for other use cases. 
    - donts: No donts

    ### Pagination
    - description: <p>Pagination splits up large amounts of content into multiple pages.</p>
    - do: Use it to let users navigate between content on multiple pages.,Use it to show small chunks of content at a time.
    - donts: No donts

    ### Palette
    - description: Palette displays a set of colors.
    - do: Use it to represent a set of solid colors, gradients or images.,Use it to display available styles to choose from.
    - donts: No donts

    ### Popover
    - description: No description
    - do: No do
    - donts: No donts

    ### PopoverMenu
    - description: <p>A popover menu displays a list of actions when a user either clicks or hovers on a trigger element.</p>
    - do: Display a list of actions when there is not enough space to expose them right away.,Display secondary actions that are hidden to the user until clicked or hovered on.
    - donts: No donts

    ### PreviewWidget
    - description: No description available
    - do: No do available
    - donts: No donts available

    ### Proportion
    - description: No description
    - do: No do
    - donts: No donts

    ### PulseAnimation
    - description: No description
    - do: No do
    - donts: No donts

    ### RadarChart
    - description: Radar chart allows users to display how a measured item is effective in different numerical parameters. It can indicate it’s relative influence to business, marketing campaigns, sales and similar criteria.
    - do: Use it to visualise influence of multiple data parameters.,Use it to display performance in multiple areas.
    - donts: No donts

    ### Radio
    - description: <p>A radio represents an item in a single selection list. It is used as an internal part of <code><RadioGroup/></code>, but can be used as a standalone item in a custom form or layout.</p>
    - do: Use it to recreate <RadioGroup/> in a custom design.
    - donts: No donts

    ### RadioGroup
    - description: <p>Radio groups (radio buttons) allow users to choose a single item from a list of options.</p>
    - do: Allow the user to select a single item from a short list of options (e.g., 2-5 items).,Use it to show all available options.,Have a preselected option where possible, or add a neutral option (e.g., "None" or "All").
    - donts: No donts

    ### Range
    - description: Range allows users to enter a range of values or dates. It’s a container that wraps and merges two input fields such as `<Input/> ` or `<Datepicker/>`.
    - do: Use it to specify a range of dates,Use it to specify a range of numeric values such as duration
    - donts: No donts

    ### RichTextInputArea
    - description: <p>Rich text input areas let users insert and format long sections of text, and add lists and links.</p>
    - do: Let users add multiple sentences or paragraphs.,Let users format the text they write.
    - donts: No donts

    ### Search
    - description: <p>Search lets users enter a keyword or phrase into a text field to find relevant results.   </p>
    - do: Use it to find relevant information on a page.,Use it to filter data in a table.,Use it to find relevant pages for easy navigation.
    - donts: No donts

    ### SectionHeader
    - description: <p>Section headers are used to group together content or items under a unifying title. They help users understand what the following section is about.</p>
    - do: Use it in a <SidePanel/> to introduce a new section of related content.,Use it in an <Accordion/> or a <Card/> to group together related items.
    - donts: No donts

    ### SectionHelper
    - description: <p>Section helper is a notification message that allows us to communicate with users and provide feedback anywhere on the page. </p>
    - do: Use it to provide information about application status, for example to inform about the expired payment method.,Use it to share the status of application sections, for example to inform that settings are turned on the way users might not see a benefit.
    - donts: No donts

    ### SegmentedToggle
    - description: <p>Segmented toggles are sets of buttons that allow users to choose from multiple options. Only a single option can be selected at a time.</p>
    - do: Allow users to switch between alternative views of data, or to change the status of an item.,Allow users to toggle between options.
    - donts: No donts

    ### SelectableAccordion
    - description: <p>Selectable accordion is a list of interactive items, which show and collapse additional content when they are selected and deselected.</p>
    - do: Use it to organize complex settings by grouping them into collapsible sections.,Use it to show additional information or settings only when an item is selected.
    - donts: No donts

    ### Selector
    - description: No description
    - do: No do
    - donts: No donts

    ### SelectorButton
    - description: No description
    - do: Use it as an entry point to a selection list in an additional panel or modal.,Use it to prompt users to open link selection or font picker panels.,After selection is made, communicate it with the component text.
    - donts: No donts

    ### SelectorList
    - description: <p>Selector lists allow users to select one or multiple items within a data set. They have built-in search and loading behaviors.</p>
    - do: Use when users can select one or multiple items in data sets.,Use when there's a long list of items and searching is helpful.,Use inside parent containers such as a <CustomModalLayout/>.
    - donts: No donts

    ### SidePanel
    - description: <p>Side panel is a component that presents supplementary information, navigation options, or controls alongside or overlaying the main content of the page.</p>
    - do: Display supplementary actions or settings that affect the main page content, such as data filters.,Display tools that can be used on the page.,Provide more details in context.,Allow to interact with the main page when side panel is open.
    - donts: No donts

    ### Sidebar
    - description: No description
    - do: No do
    - donts: No donts

    ### SidebarBackButton
    - description: No description
    - do: No do
    - donts: No donts

    ### SidebarDivider
    - description: No description
    - do: No do
    - donts: No donts

    ### SidebarDividerNext
    - description: <p>SidebarDividerNext allows to group a list of options. This component is part of SidebarNext component.</p>
    - do: Use it to build <SidebarNext/> navigation
    - donts: No donts

    ### SidebarHeader
    - description: No description
    - do: No do
    - donts: No donts

    ### SidebarHeaderNext
    - description: <p>SidebarHeaderNext displays a key information of site or other CMS application. This component is part of SidebarNext component.</p><p></p><p></p>
    - do: Use it to build <SidebarNext/> navigation
    - donts: No donts

    ### SidebarItemNext
    - description: <p>SidebarItemNext is a navigation action that reflects a single option in sidebar navigation list.</p>
    - do: Use it to build <SidebarNext/> navigation
    - donts: No donts

    ### SidebarNext
    - description: <p>SidebarNext is a major navigation element for Business Manager or Account level applications.</p>
    - do: Use it to create a navigation between Business Manager applications.,Use it to create a navigation in various content management systems.
    - donts: No donts

    ### SidebarSectionItem
    - description: No description
    - do: No do
    - donts: No donts

    ### SidebarSectionTitle
    - description: No description
    - do: No do
    - donts: No donts

    ### SidebarSubMenuNext
    - description: <p>SidebarSubMenuNext allows to put a list of options into a collapsible group. This component is part of SidebarNext component.</p>
    - do: Use it to build <SidebarNext/> navigation
    - donts: No donts

    ### SidebarTitleItemNext
    - description: <p>SidebarTitleItemNext allows to put a list of options into a group with a title. This component is part of SidebarNext component.</p>
    - do: Use it to build <SidebarNext/> navigation
    - donts: No donts

    ### Skeleton
    - description: No description
    - do: No do
    - donts: No donts

    ### SkeletonCircle
    - description: No description
    - do: No do
    - donts: No donts

    ### SkeletonGroup
    - description: No description
    - do: No do
    - donts: No donts

    ### SkeletonLine
    - description: No description
    - do: No do
    - donts: No donts

    ### SkeletonRectangle
    - description: No description
    - do: No do
    - donts: No donts

    ### Slider
    - description: Slider is an input field that enables our users to select a value within a given number range. It’s handy when a user needs an approximate but not a precise value.
    - do: Use it to adjust settings, such as opacity, brightness or volume.,Use it to specify an accepted range of values, such as price range.,Use it to control color opacity.
    - donts: No donts

    ### SocialButton
    - description: <p>Social button allow users to share content or follow social media channels.</p>
    - do: Use it to encourage users to share content.
    - donts: No donts

    ### SocialPostPreview
    - description: No description available
    - do: No do available
    - donts: No donts available

    ### SocialPreview
    - description: Social Preview allows users to see what information will be displayed once the URL address is shared on social media platforms.
    - do: Use it when the site owner needs to preview how page information will be displayed on social media. 
    - donts: No donts

    ### SortableGridBase
    - description: No description
    - do: No do
    - donts: No donts

    ### SortableListBase
    - description: No description
    - do: No do
    - donts: No donts

    ### SparklineChart
    - description: No description
    - do: No do
    - donts: No donts

    ### StackedBarChart
    - description: No description
    - do: No do
    - donts: No donts

    ### StarsRatingBar
    - description: A star rating bar allows the user to rate the quality of an item or an experience, such as a purchased product, completed service or received meal from a restaurant.
    - do: Use it to collect feedback about the quality an item or a service.,Use it to display the rating of an item or a service.
    - donts: No donts

    ### StatisticsWidget
    - description: No description
    - do: No do
    - donts: No donts

    ### StatusIndicator
    - description: <p>A status indicator highlights the status of UI elements with an explanatory message that’s displayed in a tooltip. It’s an internal component of various form inputs.</p>
    - do: Use it to provide information about component status in compact layouts, where providing it below the component is not possible.
    - donts: No donts

    ### StatusToast
    - description: <p>A status toast notifies users about a status change in an application. </p>
    - do: Use it to provide contextual feedback on the outcome of user action.,Use clear language and provide an actionable next step when applicable.,Provide one main action only (e.g., "Dismiss" or "Retry") to avoid complexity.,Use it to communicate status changes even when the user is inside a modal.
    - donts: No donts

    ### Stepper
    - description: <p>Stepper displays the path a user needs to follow to complete a process.</p>
    - do: Use it to divide a complex form or a process into a sequence of steps.,Use it to let users navigate across different steps.
    - donts: No donts

    ### Swatches
    - description: Swatches allows to display a list of predefined color options to choose from.
    - do: Use it to select a single color from a predefined color palette.,Use it to display solid color options.,Use it to create a list of color options when used with ColorPicker.
    - donts: No donts

    ### Table
    - description: <p>Table is a component used to display data in rows and columns. It organizes information in a way that is easy to scan.</p>
    - do: Use it to organize and display information from a dataset.,Use it to display data for comparison and analysis.
    - donts: No donts

    ### TableActionCell
    - description: <p>Table action cell is a built-in solution that displays actions inside of table cells. The primary action is displayed as a button, while secondary actions are displayed either as multiple icon buttons or listed in a popover menu. Component should be rendered in the last column of a data row.</p>
    - do: Use it to display actions that a user can take on a specific table row.,Render it in the last column of a table row.,Group similar items together using dividers in popover menu for easy readability.
    - donts: No donts

    ### TableListHeader
    - description: <p>Table list headers are used to provide column titles for custom list layouts.</p><p></p>
    - do: Provide column titles for data lists.
    - donts: No donts

    ### TableListItem
    - description: <p>A table list item is a single row of a table or a list, that allows users to scan and compare sets of data. These sets can be a list of similar items, like products, posts or contacts. </p>
    - do: Use this component for a simple list when a <Table/> is too complex.,Group similar items together for improved readability.,Organize important information for users. 
    - donts: No donts

    ### TableToolbar
    - description: <p>Table toolbars allow users to organize their table title, filters, and actions into 2 containers: left and right.</p>
    - do: Use it to display the title of the table.,Use it to display and organize filters.,Use it to display and organize bulk actions.
    - donts: No donts

    ### Tabs
    - description: <p>Tabs enable users to navigate between different content sections on the same page, card, or a panel.</p>
    - do: Use it to organize multiple content sections within the same context.,Use it to enhance usability by grouping information or forms into smaller, easily digestible parts.,Use short and descriptive tab titles.
    - donts: No donts

    ### Tag
    - description: A tag is a label used to categorize content or display an active selection that will be applied to a product or service.
    - do: Use it to label, categorize or organize content using descriptive keywords,Use it to visualize selected values
    - donts: No donts

    ### TagList
    - description: <p>Tag lists are groups of tag and button components. They show active keywords or filters applied to a data table.</p>
    - do: Display a summary of applied filters in a table.,Control the applied filters individually or all at once.
    - donts: No donts

    ### TestimonialList
    - description: Testimonial list allows users to promote a product or service by listing down user reviews or testimonials. It’s used in `<MarketingPage/>` component.
    - do: Display it in a footer area of a <MarketingPage/>,Use it to list down testimonials about a product or service
    - donts: No donts

    ### Text
    - description: <p>Text is a typography component used to create a wide variety of content including guidance, information, descriptions, labels and more. </p>
    - do: Use it to display text paragraphs formed from a single sentence, or multiple sentences.,Use it to display form element values and labels.
    - donts: No donts

    ### TextButton
    - description: <p>Text buttons communicate low-emphasis actions that users can take.</p>
    - do: Use it for optional actions on a page or a widget.
,Use it to navigate to another page.,Use it to display a large list of optional actions.
    - donts: No donts

    ### ThemeProvider
    - description: No description
    - do: No do
    - donts: No donts

    ### Thumbnail
    - description: Thumbnail allows to display a specified object as a select item.
    - do: Use it to select single or multiple items from a mixed list of options.,Use it when select items need to be emphasised with graphics or images.,Use it to build gallery selections.
    - donts: No donts

    ### TimeInput
    - description: <p>Time inputs allow users to to enter or select a specific time value.</p>
    - do: Use time input to select a specific time. For example, to set an event start time, schedule an appointment, or set an alarm.
    - donts: No donts

    ### TimeTable
    - description: No description
    - do: No do
    - donts: No donts

    ### Timeline
    - description: Timeline displays a vertical list of past events in a chronological order.
    - do: Use it to log and illustrate a history of events (newest on top, oldest at the bottom).,Use it when the list of events is actionable (e.g., user can view event’s documents).
    - donts: No donts

    ### Toast
    - description: No description
    - do: No do
    - donts: No donts

    ### ToggleButton
    - description: <p>Toggle button allows users to switch between states or trigger actions through clicking or selection, and is commonly used in toolbars.</p>
    - do: Use it to build composer actions like Undo and Redo.,Use it in toolbars for actions like bolding or aligning text.,Use it as a tab to navigate in a composer interface.,Use it in main layouts to enable users to switch between two states.
    - donts: No donts

    ### ToggleSwitch
    - description: <p>Toggle switch turns settings on/off. It lets users switch between two mutually exclusive states.</p>
    - do: Use it to turn a state, setting, or function on or off.,Use it to activate or deactivate something immediately.

    - donts: No donts

    ### Tooltip
    - description: <p>Tooltips provide additional explanation on how a specific element functions.  A user can trigger a tooltip by mouse hover, keyboard focus or touch.  </p>
    - do: Give additional information about interactive controls.,Describe or label non-interactive elements, such as icons or images.,Provide labels to <IconButton/>.,Use 'aria-describedby' prop to connect the tooltip’s content to its trigger element for assistive technologies.
    - donts: No donts

    ### TopBanner
    - description: <p>Banners let's user know about ongoing promotions or marketing deals on their site. </p>
    - do: Use it to promote premium related offers or market features under premium plans. ,Use it with short and clear content. ,Provide a clear action that user can take with "action" property.,Allow users to dismiss it.
    - donts: No donts

    ### Transition
    - description: <p>Transition is a wrapper that allows animations of other components.</p>
    - do: Use it to animate components that need a visual explanation of their origin or termination. For example tooltip appearance animation.,Use it for animated transitions between object states to provide clarity of change.
    - donts: No donts

    ### TrendIndicator
    - description: No description
    - do: No do
    - donts: No donts

    ### VariableInput
    - description: <p>Variable input allows you to display <code><Tag/></code> components in between plain text. Each tag represents a known variable. Input recognizes predefined text strings and matches them with an assigned variable when input loses focus (on blur).</p>
    - do: Use it to automatically generate a message or a value that includes one or multiple dynamic values.
    - donts: No donts

    ### VerticalTabs
    - description: <p>Vertical tabs let users vertically navigate between different content sections within a page, card, or panel. </p><p></p>
    - do: Use it to organize multiple content sections within the same context.,Use short and descriptive tab titles.
    - donts: No donts

    ### VerticalTabsItem
    - description: <p>A vertical tabs item is a single row of content in  <VerticalTabs/>.</p>
    - do: Use this as a part of the <VerticalTabs/> component.
    - donts: No donts

    ### VerticalTabsIconItem
    - description: No description
    - do: No do
    - donts: No donts

    ### WixDesignSystemProvider
    - description: No description available
    - do: No do available
    - donts: No donts available

    ### WixStyleReactEnvironmentProvider
    - description: WixStyleReactEnvironmentProvider is a wrapper component for an app to hold cross library global configuration such as locale, rtl and others
    - do: No do
    - donts: No donts

    ### WixStyleReactMaskingProvider
    - description: No description available
    - do: No do available
    - donts: No donts available



