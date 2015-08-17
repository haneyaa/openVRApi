`VROverlayError SetOverlayTransformAbsolute( VROverlayHandle_t ulOverlayHandle, TrackingUniverseOrigin eTrackingOrigin, const HmdMatrix34_t *pmatTrackingOriginToOverlayTransform )`

`VROverlayError GetOverlayTransformAbsolute( VROverlayHandle_t ulOverlayHandle, TrackingUniverseOrigin *peTrackingOrigin, HmdMatrix34_t *pmatTrackingOriginToOverlayTransform )`

Sets the overlay to use an absolute transform or gets the current absolute transform.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set/get absolute transform for
* `TrackingUniverseOrigin eTrackingOrigin` - Tracking origin to set transform relative to
* `TrackingUniverseOrigin *peTrackingOrigin` - Receives tracking origin that the transform is relative to
* `HmdMatrix34_t *pmatTrackingOriginToOverlayTransform` - Transform relative to the specified tracking origin

**Description**

Sets the overlay to use an absolute transform or gets the current absolute transform. Get will return an error if overlay transform is not VROverlayTransform_Absolute.
