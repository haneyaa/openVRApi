Get the current state of Chaperone calibration. This state can change at any time during a session due to physical base station changes. (NOTE: Some of these error codes are never returned as implementation for the error states is still a work in progress.)

	virtual ChaperoneCalibrationState GetCalibrationState() = 0;


	// OK!
	ChaperoneCalibrationState_OK = 1,									// Chaperone is fully calibrated and working correctly

	// Warnings
	ChaperoneCalibrationState_Warning = 100,
	ChaperoneCalibrationState_Warning_BaseStationMayHaveMoved = 101,	// A base station thinks that it might have moved
	ChaperoneCalibrationState_Warning_BaseStationRemoved = 102,			// There are less base stations than when calibrated
	ChaperoneCalibrationState_Warning_SeatedBoundsInvalid = 103,		// Seated bounds haven't been calibrated for the current tracking center

	// Errors
	ChaperoneCalibrationState_Error = 200,
	ChaperoneCalibrationState_Error_BaseStationUninitalized = 201,		// Tracking center hasn't be calibrated for at least one of the base stations
	ChaperoneCalibrationState_Error_BaseStationConflict = 202,			// Tracking center is calibrated, but base stations disagree on the tracking space
	ChaperoneCalibrationState_Error_SoftBoundsInvalid = 203,			// Soft bounds haven't been calibrated for the current tracking center
	ChaperoneCalibrationState_Error_HardBoundsInvalid = 204,			// Hard bounds haven't been calibrated for the current tracking center
};