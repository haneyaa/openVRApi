`VROverlayError SetOverlayInputMethod( VROverlayHandle_t ulOverlayHandle, VROverlayInputMethod eInputMethod )`
`VROverlayError GetOverlayInputMethod( VROverlayHandle_t ulOverlayHandle, VROverlayInputMethod *peInputMethod )`

Gets or sets the input settings for the specified overlay.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to get/set input settings for
* `VROverlayInputMethod eInputMethod` - Input method to set
* `VROverlayInputMethod *peInputMethod` - Receives the overlay's input method

**Description**

Dashboard overlays are always VROverlayInputMethod_Mouse. Other overlays default to VROverlayInputMethod_None, but can be set to use automatic mouse interaction using this function.