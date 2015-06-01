This interface is defined in openvr_driver.h in the SDK. It is used in the application process itself for various client-side operations.

**`HmdError Init( IDriverLog *pDriverLog, vr::IClientDriverHost *pDriverHost, const char *pchUserDriverConfigDir, const char *pchDriverInstallDir )`**

Initializes the driver. This will be called before any other methods are called,
except BIsHmdPresent(). BIsHmdPresent is called outside of the Init/Cleanup pair.
If Init returns anything other than HmdError_None the driver DLL will be unloaded.

* pchUserDriverConfigDir - The absolute path of the directory where the driver should store user config files.
* pchDriverInstallDir - The absolute path of the root directory for the driver.


**`void Cleanup()`**;

Cleans up the driver right before it is unloaded


**`bool BIsHmdPresent( const char *pchUserConfigDir )`**

Called when the client needs to inform an application if an HMD is attached that uses
this driver. This method should be as lightweight as possible and should have no side effects
such as hooking process functions or leaving resources loaded. Init will not be called before 
this method and Cleanup will not be called after it.


**`HmdError SetDisplayId( const char *pchDisplayId )`**

Called when the client inits an HMD to let the client driver know which one is in use.


**`bool AttachToWindow( void *hWnd )`**

[Windows Only]

Notifies the driver that the VR output will appear in a particular window.


**`HiddenAreaMesh_t GetHiddenAreaMesh( Hmd_Eye eEye )`**

Returns the stencil mesh information for the current HMD. If this HMD does not have a stencil mesh the vertex data and count will be
NULL and 0 respectively. This mesh is meant to be rendered into the stencil buffer (or into the depth buffer setting nearz) before rendering
each eye's view. The pixels covered by this mesh will never be seen by the user after the lens distortion is applied and based on visibility to the panels.
This will improve perf by letting the GPU early-reject pixels the user will never see before running the pixel shader.

**NOTE:** Render this mesh with backface culling disabled since the winding order of the vertices can be different per-HMD or per-eye.
	