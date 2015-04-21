`TrackedDeviceClass GetTrackedDeviceClass( vr::TrackedDeviceIndex_t unDeviceIndex )`

Returns the device class of a tracked device. 

* `vr::TrackedDeviceIndex unDeviceIndex` - Index of the device to get the device class for.

Returns the device class of a tracked device. If there has not been a device connected in this slot
since the application started this function will return TrackedDevice_Invalid. For previous detected
devices the function will return the previously observed device class. 

To determine which devices exist on the system, just loop from 0 to k_unMaxTrackedDeviceCount and check
the device class. Every device with something other than TrackedDevice_Invalid is associated with an 
actual physical device.

