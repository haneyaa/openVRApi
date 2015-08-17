`VROverlayError SetOverlayMouseScale( VROverlayHandle_t ulOverlayHandle, const HmdVector2_t *pvecMouseScale )`

`VROverlayError GetOverlayMouseScale( VROverlayHandle_t ulOverlayHandle, HmdVector2_t *pvecMouseScale )`

Sets/gets the mouse scaling factor that is used for mouse events. The actual texture may be a different size, but this is typically the size of the underlying UI in pixels.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to get/set mouse scale for
* `HmdVector2_t *pvecMouseScale` - The mouse scale to get/set

