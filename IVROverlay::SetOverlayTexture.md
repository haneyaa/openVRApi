`VROverlayError SetOverlayTexture( VROverlayHandle_t ulOverlayHandle, GraphicsAPIConvention eTextureType, void* pTexture )`

Texture to draw for the overlay.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to set the texture for
* `GraphicsAPIConvention eTextureType` - Either `API_DirectX` or `API_OpenGL` depending on what the texture pointer refers to
* `void* pTexture` - Pointer to the texture in question. See description

**Description**

Sets an existing application-created graphics resource as the texture for the overlay. The type of the pTexture depends on the eTextureType parameter

* API_DirectX - pTexture must be a pointer to one of:
  * ID3D10Texture*
  * ID3D11Texture*
* API_OpenGL - pTexture must the `GLuint` of the texture
