Allows the application to customize how the overlay appears in the compositor.

	struct Compositor_OverlaySettings
	{
		uint32_t size; // sizeof(Compositor_OverlaySettings)
		bool curved, antialias;
		float scale, distance, alpha;
		float uOffset, vOffset, uScale, vScale;
		float gridDivs, gridWidth, gridScale;
		HmdMatrix44_t transform;
	};
