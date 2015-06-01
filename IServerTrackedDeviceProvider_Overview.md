`IServerTrackedDeviceProvider` is requested and used in vrserver to query tracking and other information about tracked devices. It must be implemented in driver dynamic libraries.


**`HmdError Init( IDriverLog *pDriverLog, vr::IServerDriverHost *pDriverHost, const char *pchUserDriverConfigDir, const char *pchDriverInstallDir )`**

initializes the driver. This will be called before any other methods are called.
If Init returns anything other than HmdError_None the driver DLL will be unloaded.

* pchUserDriverConfigDir - The absolute path of the directory where the driver should store user config files.
* pchDriverInstallDir - The absolute path of the root directory for the driver.


**`void Cleanup()`**

Cleans up the driver right before it is unloaded.


**`uint32_t GetTrackedDeviceCount()`**

Returns the number of tracked devices that this driver manages that are physically connected. This is used at startup to initialize the tracked device list for the driver.

**`ITrackedDeviceServerDriver *GetTrackedDeviceDriver( uint32_t unWhich )`**

Returns a single tracked device interface.


**`ITrackedDeviceServerDriver* FindTrackedDeviceDriver( const char *pchId )`**

Returns a single tracked device by serial number.


**`void RunFrame()`**

Allows the driver do to some work in the main loop of the server. This can be useful to avoid the need for a main thread in your driver.

