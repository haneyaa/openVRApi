`VROverlayError SetOverlayFromFile( VROverlayHandle_t ulOverlayHandle, const char *pchFilePath )`

Sets the overlay image from a file.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set the texture for
* `const char *pchFilePath` - Path to the file. If a relative path is provided it is assumed to be relative to the resource directory in the OpenVR runtime.

**Description**

Loads the specified file and sets that texture as the contents of the overlay. Textures can be up to 1920x1080 i size. PNG, JPG, and TGA files are supported in 24 or 32 bits.

