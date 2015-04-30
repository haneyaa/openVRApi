	/** Get the current state of Chaperone calibration. This state can change at any time during a session due to physical base station changes. (NOTE: Some of these error codes are never returned as implementation for the error states is still a work in progress.) */
	virtual ChaperoneCalibrationState GetCalibrationState() = 0;

	/** Returns the 4 corner positions of the Soft Bounds (also know as Safe Zone and Play Space). */
	virtual bool GetSoftBoundsInfo( ChaperoneSoftBoundsInfo_t *pInfo ) = 0;

	/** Returns the quads representing the Hard Bounds (static physical obstacles). */
	virtual bool GetHardBoundsInfo( VR_OUT_ARRAY_COUNT(punQuadsCount) HmdQuad_t *pQuadsBuffer, uint32_t* punQuadsCount ) = 0;

	/** Returns the preferred seated position and front edge of their desk. (NOTE: Desk position is currently not set in room Calibration and unused. In the future this interface will expand to include tagged markup of the physical space by position, angles, and dimensions.) */
	virtual bool GetSeatedBoundsInfo( ChaperoneSeatedBoundsInfo_t *pInfo ) = 0;
