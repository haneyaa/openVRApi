`VROverlayError SetOverlayTextureBounds( VROverlayHandle_t ulOverlayHandle, const VRTextureBounds_t *pOverlayTextureBounds )`
`VROverlayError GetOverlayTextureBounds( VROverlayHandle_t ulOverlayHandle, VRTextureBounds_t *pOverlayTextureBounds )`

Sets/gets the part of the texture to use for the overlay.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to get/set texture bounds for
* `VRTextureBounds_t *pOverlayTextureBounds` - Bounds to get/set

Sets the part of the texture to use for the overlay. UV Min is the upper left corner and UV Max is the lower right corner. By default overlays use the entire texture.
