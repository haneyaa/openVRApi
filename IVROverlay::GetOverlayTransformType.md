`VROverlayError GetOverlayTransformType( VROverlayHandle_t ulOverlayHandle, VROverlayTransformType *peTransformType )`

Retrieves the transform type of this overlay.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to get the transform type for
* `VROverlayTransformType *peTransformType` - Receives the transform type.

**Description**

Transform type will be one of:
* `VROverlayTransform_Absolute` - Overlay is in some absolute position in space
* `VROverlayTransform_TrackedDeviceRelative` - Overlay is relative to some tracked device
* `VROverlayTransform_SystemOverlay` - Overlay is part of the dashboard and is positioned with the rest of the VR Dashboard
