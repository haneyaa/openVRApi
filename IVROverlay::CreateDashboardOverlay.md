`VROverlayError CreateDashboardOverlay( const char *pchOverlayKey, const char *pchOverlayFriendlyName, VROverlayHandle_t * pMainHandle, VROverlayHandle_t *pThumbnailHandle )`

Creates a VR Dashboard overlay and returns its handles.

* `const char *pchOverlayKey` - Key to use for the new overlay. Must be unique
* `const char *pchOverlayFriendlyName` - Name to use for the overlay's tab in the VR Dashboard
* `VROverlayHandle_t * pMainHandle` - Receives the handle of the main overlay view
* `VROverlayHandle_t *pThumbnailHandle` - Receives the handle of the icon overlay

**Description**

Creates an overlay that the user will see when they hit the system button on their controller. The main handle should be set to the UI view.  The thumbnail handle should be set to the icon for this overlay.

See the [helloworldoverlay sample](https://github.com/ValveSoftware/openvr/tree/master/samples/helloworldoverlay) for an example of how to implement a VR Dashboard overlay using Qt.