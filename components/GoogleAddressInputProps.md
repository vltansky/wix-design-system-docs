
### placeholder
- type: string
- description: Placeholder for the input box
### valuePrefix
- type: string
- description: Value to place before every search term (normally should not be used)
### countryCode
- type: string
- description: Country code used to help with suggestions and geocoding
### value
- type: string
- description: Controlled mode - value to display
### types
- type: array
- description: Limit the autocomplete to specific types (see [here](https://developers.google.com/places/supported_types#table3) for list)
### filterTypes
- type: array
- description: Lower level filtering of autocomplete result types (see [here](https://developers.google.com/places/supported_types) for list)
### placeDetailsFields
- type: array
- description: Fields indicating which types of Places data to return (see [here](https://developers.google.com/maps/documentation/javascript/places#place_details)*
### status
- type: enum
- description: Sets UI to indicate a status
### statusMessage
- type: node
- description: The status message to display when hovering the status icon, if not given or empty there will be no tooltip
### onChange
- type: func
- description: No description
### onBlur
- type: func
- description: No description
### onFocus
- type: func
- description: No description
### onKeyDown
- type: func
- description: No description
### onSet
- type: func
- description: Callback for results. Will return an object containing: originValue (value in the search), googleResult (google geocode result for the search), address (which will include: formatted (google formatted address), country, countryCode, street, number, postalCode, latLng (lat, lng))
### Client
- type: func
- description: Google map client implementation (should implement autocomplete and geocode functions). Normally you would use @wix/design-system/clients/GoogleMapsClient
### magnifyingGlass
- type: bool
- description: Show or hide magnifying glass icon
### readOnly
- type: bool
- description: Sets the input to readOnly
### autoSelect
- type: bool
- description: No description
### footer
- type: any
- description: Display a footer as the last suggestion in the list
### footerOptions
- type: object
- description: Set the footer&#39;s options (e.g. disabled, overrideStyles, etc. )
### clearSuggestionsOnBlur
- type: bool
- description: Clear the suggestions list upon input blur
### fallbackToManual
- type: bool
- description: If set to `true`, we will attempt to get a Google location from the input&#39;s text if there are no suggestions. This is useful when looking for locations for which google does not give suggestions - for example: Apartment/Apt
### poweredByGoogle
- type: bool
- description: Shows the Powered By Google credit in a fixed footer
### handler
- type: enum
- description: Sets how to get more details for a place (e.g. geocode, places, etc)


