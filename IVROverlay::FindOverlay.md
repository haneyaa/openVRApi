`VROverlayError FindOverlay( const char *pchOverlayKey, VROverlayHandle_t * pOverlayHandle )`

Finds an existing overlay with the specified key. If the overlay can't be found pOverlayHandle is set to k_ulOverlayHandleInvalid and VROverlayError_UnknownOverlay is returned.

* `const char *pchOverlayKey` - The overlay to search for.
* `VROverlayHandle_t *pOverlayHandle` - Used to return the overlay handle if it is found.
