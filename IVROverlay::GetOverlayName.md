`uint32_t GetOverlayName( VROverlayHandle_t ulOverlayHandle, char *pchValue, uint32_t unBufferSize, VROverlayError *pError = 0L )`

Gets the string name from the specified overlay.

* `VROverlayHandle_t ulOverlayHandle` - The handle of the overlay to fetch a name for.
* `char *pchValue` - An application-provided buffer to put the name in. 
* `uint32_t unBufferSize` - The size of the provided buffer. k_unVROverlayMaxNameLength will be enough bytes to fit the string.
* `VROverlayError *pError` - Contains the result code of this request.

**Description**

Fills the provided buffer with the string name of the overlay. Returns the size of buffer required to store the name, including the terminating null character. k_unVROverlayMaxNameLength will be enough bytes to fit the string.
