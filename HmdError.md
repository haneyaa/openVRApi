HmdError will be one of:

* `HmdError_None` (0) - There was no error
* `HmdError_Unknown` (1) - There was an unknown error

* `HmdError_Init_InstallationNotFound` (100) - The installation folder specified in the path registry doesn't exist.
* `HmdError_Init_InstallationCorrupt` (101) - The installation folder specified in the path registry has no bin folder.
* `HmdError_Init_VRClientDLLNotFound` (102) - The bin folder has no vrclient.dll (or system-appropriate dynamic library.)
* `HmdError_Init_FileNotFound` (103) - A driver could not be loaded.
* `HmdError_Init_FactoryNotFound` (104) - The factory function in vrclient.dll could not be found. Is vrclient.dll corrupt?
* `HmdError_Init_InterfaceNotFound` (105) - The specific interface function requested by VR_Init or VR_GetGenericInterface could not be found. Is the SDK being used newer than the installed runtime?
* `HmdError_Init_InvalidInterface` (106) - This error code is currently unused.
* `HmdError_Init_UserConfigDirectoryInvalid` (107) - The config directory specified in the path registry was not writable.
* `HmdError_Init_HmdNotFound` (108) - Either no HMD was attached to the system or the HMD could not be initialized.
* `HmdError_Init_NotInitialized` (109) - VR_GetGenericInterface will return this error if it is called before VR_Init or after VR_Shutdown.
* `HmdError_Init_PathRegistryNotFound` (110) - The VR path registry file could not be read. Reinstall the OpenVR runtime (or the SteamVR application on Steam.)
* `HmdError_Init_NoConfigPath` (111) - The config path was not specified in the path registry.
* `HmdError_Init_NoLogPath` (112) - The log path was not specified in the path registry.
* `HmdError_Init_PathRegistryNotWritable` (113) - The VR path registry could not be written. 

* `HmdError_Driver_Failed` (200) - A driver failed to initialize. This is an internal error.
* `HmdError_Driver_Unknown` (201) - A driver failed for an unknown reason. This is an internal error.
* `HmdError_Driver_HmdUnknown` (202) - A driver did not detect an HMD. This is an internal error.
* `HmdError_Driver_NotLoaded` (203) - A driver was not loaded before requests were made from that driver. This is an internal error.
* `HmdError_Driver_RuntimeOutOfDate` (204) - For drivers with a runtime of their own, that runtime needs to be updated.
* `HmdError_Driver_HmdInUse` (205) - Another non-OpenVR application is using the HMD.

* `HmdError_IPC_ServerInitFailed` (300) - OpenVR was unable to start vrserver.
* `HmdError_IPC_ConnectFailed` (301) - After repeated attempts, OpenVR was unable to connect to vrserver or vrcompositor.
* `HmdError_IPC_SharedStateInitFailed` (302) - Shared memory with vrserver or vrcompositor could not be opened.
* `HmdError_IPC_CompositorInitFailed` (303) - OpenVR was unable to start vrcompositor.
* `HmdError_IPC_MutexInitFailed` (304) - OpenVR was unable to create a mutex to communicate with vrcompositor.

* `HmdError_VendorSpecific_UnableToConnectToOculusRuntime` (1000) - The connection to the Oculus runtime failed for an unknown reason.

* `HmdError_Steam_SteamInstallationNotFound` (2000) - This error is not currently used.

