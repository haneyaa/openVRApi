`VROverlayError CreateOverlay( const char *pchOverlayKey, const char *pchOverlayFriendlyName, VROverlayHandle_t * pOverlayHandle )`

Creates a new named overlay. All overlays start hidden and with default settings.

* `const char *pchOverlayKey` - The key to create the overlay with. Keys must be globally unique and may not be longer than k_unVROverlayMaxKeyLength including the terminating null.
* `const char *pchOverlayFriendlyName` - The friendly, user-visible name of the overlay. When appropriate the name should be provided in UTF-8 in the current system language. This name may not be longer than k_unVROverlayMaxNameLength including the terminating null.
* `VROverlayHandle_t * pOverlayHandle` - Receives the handle of the newly created overlay.

**Description**

Creates a non-VR Dashboard overlay. To create an overlay that appears in the VR dashboard, see [`IVROverlay::CreateDashboardOverlay`](https://github.com/ValveSoftware/openvr/wiki/IVROverlay::CreateDashboardOverlay)

