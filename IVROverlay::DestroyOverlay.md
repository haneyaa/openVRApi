`VROverlayError DestroyOverlay( VROverlayHandle_t ulOverlayHandle )`

Destroys the specified overlay. When an application calls VR_Shutdown all overlays created by that app are
automatically destroyed. Applications can only destroy overlays created in the same process.

* `VROverlayHandle_t ulOverlayHandle` - The handle of the overlay to destroy. 
