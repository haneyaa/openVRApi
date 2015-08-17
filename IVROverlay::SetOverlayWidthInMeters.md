`VROverlayError SetOverlayWidthInMeters( VROverlayHandle_t ulOverlayHandle, float fWidthInMeters )`

`VROverlayError GetOverlayWidthInMeters( VROverlayHandle_t ulOverlayHandle, float *pfWidthInMeters )`

Sets/gets the width of the overlay quad in meters. 

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set/get width for
* `float fWidthInMeters` - Width of the overlay in meters
* `float *pfWidthInMeters` - Receives width of the overlay in meters

**Description** 

Sets/gets the width of the overlay quad in meters. By default overlays are rendered on a quad that is 1 meter across.

Overlays are rendered at the aspect ratio of their underlying texture and texture bounds. Height is a function of width and that aspect ratio. An overlay that is 1.6 meters wide and has a 1920x1080 texture would be 0.9 meters tall.


