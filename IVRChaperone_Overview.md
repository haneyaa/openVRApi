Notes:
* GetSoftBoundsInfo is being deprecated.  We are planning to adopt a series of discrete play volumes which will allow devs to target, and consumers to verify they have enough room to play.
* GetHardBoundsInfo currently returns a single quad which is used to define the extents of the playable space (typically aligned to the physical walls of the room).  To be forward compatible, you should check that the count is 1 since this may return higher detailed geometry in the future, resulting in the first quad not necessarily representing the total available space.
* Calibrations are saved per "universe" which with lighthouse corresponds to a set of basestations.  We attempt to update the universe when basestations are moved.  These functions will only return valid data once we've determined which known universe you are currently in.  Therefore, you may need to poll the functions until they return true (which will happen after establishing tracking for the hmd).
* You can (and likely should) also poll for VREvent_ChaperoneDataHasChanged to update things if the chaperone data changes.

	/** Get the current state of Chaperone calibration. This state can change at any time during a session due to physical base station changes. (NOTE: Some of these error codes are never returned as implementation for the error states is still a work in progress.) */
	virtual ChaperoneCalibrationState GetCalibrationState() = 0;

	/** Returns the 4 corner positions of the Soft Bounds (also know as Safe Zone and Play Space). */
	virtual bool GetSoftBoundsInfo( ChaperoneSoftBoundsInfo_t *pInfo ) = 0;

	/** Returns the quads representing the Hard Bounds (static physical obstacles). */
	virtual bool GetHardBoundsInfo( VR_OUT_ARRAY_COUNT(punQuadsCount) HmdQuad_t *pQuadsBuffer, uint32_t* punQuadsCount ) = 0;

	/** Returns the preferred seated position and front edge of their desk. (NOTE: Desk position is currently not set in room Calibration and unused. In the future this interface will expand to include tagged markup of the physical space by position, angles, and dimensions.) */
	virtual bool GetSeatedBoundsInfo( ChaperoneSeatedBoundsInfo_t *pInfo ) = 0;