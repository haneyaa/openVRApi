Computes the overlay-space pixel coordinates of where the ray intersects the overlay with the specified settings. Returns false if there is no intersection.

	virtual bool ComputeOverlayIntersection( const Compositor_OverlaySettings* pSettings, float fAspectRatio, vr::TrackingUniverseOrigin eOrigin, vr::HmdVector3_t vSource, vr::HmdVector3_t vDirection, vr::HmdVector2_t *pvecIntersectionUV, vr::HmdVector3_t *pvecIntersectionTrackingSpace ) = 0;
