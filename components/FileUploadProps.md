
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### children
- type: (params: FileUploadChildrenProps) =&gt; ReactNode
- description: Accepts any kind of component as a child item that calls out the file picker.
##### Syntax:
function({ openFileUpload }): element
* `openFileUpload`: A function that will open a file upload dialog when triggered.
* return: A react element
### multiple
- type: boolean
- description: Allows you to select and upload multiple files at once.
### accept
- type: string
- description: Defines which file types to accept (i.e. .jpeg, .gif, .png). Each format should be separated by a comma.
### capture
- type: FileUploadCapture
- description: Specifies that a new file should be captured and which camera to use to capture the image or video data.
`Use user` for the user-facing camera and `environment`  for the outward-facing camera.
##### Note: This only works on mobile devices;
If your device is a desktop computer, you&#39;ll get a standard file picker.
### name
- type: string
- description: Specifies a form data name to be submitted along with the control value.
### onChange
- type: (files: FileList) =&gt; void
- description: Defines a standard input onChange callback.


