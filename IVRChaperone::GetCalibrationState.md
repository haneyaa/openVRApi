Get the current state of Chaperone calibration. This state can change at any time during a session due to physical base station changes. (NOTE: Some of these error codes are never returned as implementation for the error states is still a work in progress.)

	virtual ChaperoneCalibrationState GetCalibrationState() = 0;