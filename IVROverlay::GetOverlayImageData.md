`VROverlayError GetOverlayImageData( VROverlayHandle_t ulOverlayHandle, void *pvBuffer, uint32_t unBufferSize, uint32_t *punWidth, uint32_t *punHeight )`

Gets the raw image data from an overlay.

* `VROverlayHandle_t ulOverlayHandle` - Overlay to get image data for
* `void *pvBuffer` - Application provided buffer to put image data in
* `uint32_t unBufferSize` - Size of the provided buffer in bytes
* `uint32_t *punWidth` - Width of the overlay image in pixels
* `uint32_t *punHeight` - Height of the overlay image in pixels

**Description**

Gets the raw image data from an overlay. Overlay image data is always returned as RGBA data, 4 bytes per pixel. If the buffer is not large enough, width and height will be set and VROverlayError_ArrayTooSmall is returned.
