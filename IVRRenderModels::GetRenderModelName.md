`uint32_t GetRenderModelName( uint32_t unRenderModelIndex, char *pchRenderModelName, uint32_t unRenderModelNameLen )`

Returns the name of the Nth render model.

* `unRenderModelIndex` - Index of the model to return the name for.
* `pchRenderModelName` - A buffer provided by the application to fill with the render model name.
* `unRenderModelNameLen` - The size of the provided buffer in bytes.

** Description **

Returns the name of the Nth render model that is provided by the OpenVR runtime. The provided index is not a tracked device index, but rather is a number between 0 and the return value of `GetRenderModelCount()-1`. If the index is out of range the function will return 0. In all other cases the function returns the required buffer size to hold the name, which is the length of the name plus one for the null terminator. If the provided buffer was long enough the name will be copied into it.
