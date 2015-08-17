`VROverlayError SetHighQualityOverlay( VROverlayHandle_t ulOverlayHandle )`

Specify which overlay to use the high quality render path.

* `VROverlayHandle_t ulOverlayHandle `

**Description**

Specify which overlay to use the high quality render path.  This overlay will be composited in during the distortion pass which
results in it drawing on top of everything else, but also at a higher quality as it samples the source texture directly rather than
rasterizing into each eye's render texture first.  Because if this, only one of these is supported at any given time.  It is most useful
for overlays that are expected to take up most of the user's view (e.g. streaming video).

Note: VR Dashboard overlays may not use the High Quality path.
