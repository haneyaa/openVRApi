`VROverlayError SetOverlayColor( VROverlayHandle_t ulOverlayHandle, float fRed, float fGreen, float fBlue )`
`VROverlayError GetOverlayColor( VROverlayHandle_t ulOverlayHandle, float *pfRed, float *pfGreen, float *pfBlue )`

Sets/gets the color tint of the overlay quad. Use 0.0 to 1.0 per channel.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to interact with color on
* `float fRed` - Red value between 0 and 1 to set
* `float fBlue` - Blue value between 0 and 1 to set
* `float fGreen` - Green value between 0 and 1 to set
* `float *pfRed` - Receives red value between 0 and 1
* `float *pfBlue` - Receives blue value between 0 and 1
* `float *pfGreen` - Receives green value between 0 and 1

