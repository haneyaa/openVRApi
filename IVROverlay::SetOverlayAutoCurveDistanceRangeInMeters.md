`VROverlayError SetOverlayAutoCurveDistanceRangeInMeters( VROverlayHandle_t ulOverlayHandle, float fMinDistanceInMeters, float fMaxDistanceInMeters )`
`VROverlayError GetOverlayAutoCurveDistanceRangeInMeters( VROverlayHandle_t ulOverlayHandle, float *pfMinDistanceInMeters, float *pfMaxDistanceInMeters )`

Sets/gets the distance range in meters used to curve the overlay around the viewer. This is only used by the high-quality overlay.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set/get the ranges for
* `float fMinDistanceInMeters` - Distance where the overlay will be the most curved
* `float fMaxDistanceInMeters` - Distance where the overlay will be the least curved
* `float *pfMinDistanceInMeters` - Receives distance where the overlay will be the most curved
* `float *pfMaxDistanceInMeters` - Receives distance where the overlay will be the least curved

**Description**
For high-quality curved overlays only, sets the distance range in meters from the overlay used to automatically curve the surface around the viewer.  Min is distance is when the surface will be most curved.  Max is when least curved.
