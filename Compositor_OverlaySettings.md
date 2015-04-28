Allows the application to customize how the overlay appears in the compositor.  The overlay is a special surface used to present 2D content in a high res manner by sampling the source texture directly rather than rasterizing into the scene view first.  It is, however, quite expensive, and only one surface is supported currently.

Use [IVRCompositor::GetOverlayDefaults](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetOverlayDefaults) to fill out default settings.

Always set 'size' to sizeof(Compositor_OverlaySettings) for proper versioning and avoid memory corruption.  This includes calling GetOverlayDefaults.  In C# use:

	(uint)System.Runtime.InteropServices.Marshal.SizeOf(typeof(Compositor_OverlaySettings));

### Properties ###

**curved** _[default: true]_ - Toggles between drawing as a segment of a cylinder which flexes as you approach the surface, or simply a flat plane.

**antialias** _[default: true]_ - Controls applying a 2x2 RGSS filter when rendering the surface.

**scale** _[default: 3.0]_ - The implicit surface is 1m wide, adopting the aspect ratio of the source texture.  This value allows you to adjust that size.

**distance** _[default: 1.25]_ - Number of meters the surface is drawn from its transform.  By default the overlay is placed at the origin, with the surface rendered 1.25 meters away from and facing the camera.

**alpha** _[default: 1.0]_ - Ramp to control blending with the scene.  Note: The overlay always draws on top - it does not respect the depth buffer.

**uOffset** _[default: 0.0]_ - Used to horizontally shift the contents of the source texture relative to the implicit surface.

**vOffset** _[default: 0.0]_ - Used to vertically shift the contents of the source texture relative to the implicit surface.

**uScale** _[default: 1.0]_ - Used to horizontally scale the contents of the source texture relative to the implicit surface.

**vScale** _[default: 1.0]_ - Used to vertically scale the contents of the source texture relative to the implicit surface.

**transform** _[default: identity]_ - Controls position and orientation of the implicit surface.

	struct Compositor_OverlaySettings
	{
		uint32_t size; // sizeof(Compositor_OverlaySettings)
		bool curved, antialias;
		float scale, distance, alpha;
		float uOffset, vOffset, uScale, vScale;
		float gridDivs, gridWidth, gridScale;
		HmdMatrix44_t transform;
	};