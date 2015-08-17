`uint32_t GetOverlayKey( VROverlayHandle_t ulOverlayHandle, VR_OUT_STRING() char *pchValue, uint32_t unBufferSize, VROverlayError *pError = 0L )`

Gets the string key from the specified overlay.

* `VROverlayHandle_t ulOverlayHandle` - The handle of the overlay to fetch a key for.
* `char *pchValue` - An application-provided buffer to put the key in. 
* `uint32_t unBufferSize` - The size of the provided buffer. k_unVROverlayMaxKeyLength will be enough bytes to fit the string.
* `VROverlayError *pError` - Contains the result code of this request.

**Description**

Fills the provided buffer with the string key of the overlay. Returns the size of buffer required to store the key, including the terminating null character. k_unVROverlayMaxKeyLength will be enough bytes to fit the string.

