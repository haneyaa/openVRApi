`VROverlayError SetOverlayTransformTrackedDeviceRelative( VROverlayHandle_t ulOverlayHandle, TrackedDeviceIndex_t unTrackedDevice, const HmdMatrix34_t *pmatTrackedDeviceToOverlayTransform )`
`VROverlayError GetOverlayTransformTrackedDeviceRelative( VROverlayHandle_t ulOverlayHandle, TrackedDeviceIndex_t *punTrackedDevice, HmdMatrix34_t *pmatTrackedDeviceToOverlayTransform )`

Sets the transform relative to the specified tracked device or gets the existing tracked device relative transform.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to interact with
* `TrackedDeviceIndex_t unTrackedDevice` - Tracked device to move the overlay relative to
* `TrackedDeviceIndex_t *punTrackedDevice` - Receives tracked device index that the overlay is moving relative to
* `HmdMatrix34_t *pmatTrackedDeviceToOverlayTransform` - Overlay's transform relative to the tracked device


**Description**

Use these functions to set up an overlay to move around as a tracked device does. Further transform updates for the overlay will happen automatically as the tracked device moves.

Get will return an error if the transform type is not VROverlayTransform_TrackedDeviceRelative.
