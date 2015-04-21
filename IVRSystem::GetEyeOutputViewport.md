`void GetEyeOutputViewport( Hmd_Eye eEye, GraphicsAPIConvention eAPIType, uint32_t *pnX, uint32_t *pnY, uint32_t *pnWidth, uint32_t *pnHeight )`

Returns the viewport in pixels in display space that the game should render into for the specified eye.

* `eEye` - Eye_Left or Eye_Right. Determines which eye the function should return the viewport for.
* `eAPIType` - Modifies the return values to match the conventions of the specified API. One of:
  * `API_DirectX`
  * `API_OpenGL
* `pnX` - X position of the eye's viewport within the window
* `pnY` - Y position of the eye's viewport within the window
* `pnWidth` - width of the eye's viewport within the window
* `pnHeight` - height of the eye's viewport within the window
