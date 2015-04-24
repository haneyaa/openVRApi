Returns pose(s) to use to render scene.

	virtual void WaitGetPoses( VR_ARRAY_COUNT(unPoseArrayCount) TrackedDevicePose_t* pPoseArray, uint32_t unPoseArrayCount ) = 0;

For more information on poses, see [`IVRSystem::GetDeviceToAbsoluteTrackingPose`](https://github.com/ValveSoftware/openvr/wiki/IVRSystem::GetDeviceToAbsoluteTrackingPose).