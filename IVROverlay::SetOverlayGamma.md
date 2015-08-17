`VROverlayError SetOverlayGamma( VROverlayHandle_t ulOverlayHandle, float fGamma )`

`VROverlayError GetOverlayGamma( VROverlayHandle_t ulOverlayHandle, float *pfGamma )`

Sets/gets the gamma of the overlay quad. Use 2.2 when providing a texture in linear color space. By default overlays are rendered with 1.0 gamma. 

* `VROverlayHandle_t ulOverlayHandle` - Overlay to get/set gamma for
* `float fGamma` - Gamma value to set
* `float *pfGamma` - Receives gamma value

