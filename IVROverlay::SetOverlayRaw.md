`VROverlayError SetOverlayRaw( VROverlayHandle_t ulOverlayHandle, void *pvBuffer, uint32_t unWidth, uint32_t unHeight, uint32_t unDepth )`

Sets the overlay's texture from raw bytes in system memory.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set the texture for
* `void *pvBuffer` - Pointer to the texture data
* `uint32_t unWidth` - Width of the texture in pixels
* `uint32_t unHeight` - Height of the texture in pixels
* `uint32_t unDepth` - Depth of the texture in bytes

**Description**

Sets the overlay's texture from raw bytes in system memory. When possible, SetOverlayTexture should be used instead of SetOverlayRaw.



