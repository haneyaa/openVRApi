`bool ComputeOverlayIntersection( VROverlayHandle_t ulOverlayHandle, const VROverlayIntersectionParams_t *pParams, VROverlayIntersectionResults_t *pResults )`

Computes the overlay-space pixel coordinates of where the ray intersects the overlay. Returns false if there is no intersection.

* `VROverlayHandle_t ulOverlayHandle` - Handle of the overlay to test intersection with
* `const VROverlayIntersectionParams_t *pParams` - The ray to test for intersection
* `VROverlayIntersectionResults_t *pResults` - The details of the results

**Description**

Intersections are tested using these parameter blocks:

	struct VROverlayIntersectionParams_t
	{
		HmdVector3_t vSource;
		HmdVector3_t vDirection;
		TrackingUniverseOrigin eOrigin;
	};

	struct VROverlayIntersectionResults_t
	{
		HmdVector3_t vPoint;
		HmdVector3_t vNormal;
		HmdVector2_t vUVs;
		float fDistance;
	};

