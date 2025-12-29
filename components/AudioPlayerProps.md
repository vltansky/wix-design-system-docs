
### dataHook
- type: string
- description: Applies a data-hook HTML attribute that can be used in the tests.
### className
- type: string
- description: Specifies a CSS class name to be appended to the component’s root element.
### src
- type: string
- description: Specifies a link to the source of the track to be loaded for the sound (URL or base64 data URI).
If a file has no extension, you will need to specify the extension using the format property.
### format
- type: string
- description: Specifies a file format in situations where extraction does not work (such as a SoundCloud stream).&lt;br/&gt;
By default, AudioPlayer detects your file format from the extension.
### preload
- type: enum
- description: Determines what to download when the component is rendered: full file, its metadata or nothing at all.
When webAudioAPI = true you can only set it to either &#39;auto&#39; or &#39;none&#39;.
When webAudioAPI = false you can set it to &#39;auto&#39;, &#39;metadata&#39; or &#39;none&#39;.
### autoplay
- type: bool
- description: Start playback automatically when audio is loaded.
### webAudioAPI
- type: bool
- description: Specifies whether to force web audio API. Use it for relatively small audio files only because you have to wait for the full file
to be downloaded and decoded before playing. Web Audio API allows advanced capabilities as described in
[Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API).
### onLoad
- type: func
- description: Defines a callback function which is called when audio is loaded.
### onLoadError
- type: func
- description: Defines a callback function which is called every time audio fails to load.
### onPlay
- type: func
- description: Defines a callback function which is called when audio is played.
### onPause
- type: func
- description: Defines a callback function which is called when audio is paused.
### onEnd
- type: func
- description: Will be called when audio is ended.
### onSeek
- type: func
- description: Defines a callback function which is called when audio is sought explicitly (i.e. when user drags the slider).


