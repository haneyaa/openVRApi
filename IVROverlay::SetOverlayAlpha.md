`VROverlayError SetOverlayAlpha( VROverlayHandle_t ulOverlayHandle, float fAlpha )`
`VROverlayError GetOverlayAlpha( VROverlayHandle_t ulOverlayHandle, float *pfAlpha )`

Sets/gets the alpha of the overlay quad. Use 1.0 for 100 percent opacity and 0.0 for 0 percent opacity.

* `VROverlayHandle_t ulOverlayHandle` - Overlay to get/set alpha for
* `float fAlpha` - Alpha value to set. This should be a value between 0 (fully transparent) and 1.0 (fully opaque).
* `float *pfAlpha` - Receives the current alpha value of the overlay
