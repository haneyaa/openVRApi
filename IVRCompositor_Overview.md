#Overview#

The vr::IVRCompositor interfaces provides access to the Compositor subsystem.  The Compositor simplifies the process of displaying images to the user by taking care of distortion, prediction, synchronization and other subtle issues that can be a challenge to get operating properly for a solid VR experience.

Applications call WaitGetPoses to get the set of poses used to render the camera and other tracked objects, render the left and right eyes as normal (using the info provided by IVRSystem) and finally Submit those undistorted textures for the Compositor to display in its own window.

It is recommended that you continue Presenting your application's own window, reusing either the left or right eye camera render target to draw a single quad (perhaps cropped to a lower fov to hide the hidden area mask).

Example:

    SetGraphicsDevice
    while Running:
        WaitGetPoses
        Render Left and Right cameras
        Submit Left and Right render targets
        Update game logic

Alternatively, you may wish to render serially in order to share a single render target across cameras:

    SetGraphicsDevice
    while Running:
        WaitGetPoses
        Render(L)
        Submit(L)
        Render(R)
        Submit(R)
        Update game logic

#Enumerations#

    /** Identifies the graphics API for the associated device */
    enum Compositor_DeviceType
    {
        Compositor_DeviceType_None,
        Compositor_DeviceType_D3D9,
        Compositor_DeviceType_D3D9Ex,
        Compositor_DeviceType_D3D10,
        Compositor_DeviceType_D3D11,
        Compositor_DeviceType_OpenGL
    };

    /** Provides a single frame's timing information to the app */
    struct Compositor_FrameTiming
    {
        uint32_t size; // sizeof(Compositor_FrameTiming)
        double frameStart;
        float frameVSync; // seconds from frame start
        uint32_t droppedFrames;
        uint32_t frameIndex;
        vr::TrackedDevicePose_t pose;
    };

    /** Allows the application to control what part of the provided texture will be used in the
    * frame buffer. */
    struct Compositor_TextureBounds
    {
        float uMin, vMin;
        float uMax, vMax;
    };

#Interfaces#

The vr::IVRCompositor interface contains the following functions:

	/** Returns the last error that occurred in the compositor */
	virtual uint32_t GetLastError( VR_OUT_STRING() char* pchBuffer, uint32_t unBufferSize ) = 0;

	/** Turns vsync on or off on the compositor window */
	virtual void SetVSync( bool bVSync ) = 0;

	/** Returns true if vsync is enabled in the compositor window */
	virtual bool GetVSync() = 0;

	/** Sets gamma for the compositor window */
	virtual void SetGamma( float fGamma ) = 0;

	/** Returns the gamma for the compositor window */
	virtual float GetGamma() = 0;

	/** Sets the graphics device or context for the application that is going to feed 
	* images to the compositor. The type of the pDevice parameter must match the 
	* type that is provided:
	*	Compositor_DeviceType_D3D9		IDirect3DDevice9*
	*	Compositor_DeviceType_D3D9Ex	IDirect3DDevice9Ex*
	*	Compositor_DeviceType_D3D10		ID3D10Device*
	*	Compositor_DeviceType_D3D11		ID3D11Device*
	*	Compositor_DeviceType_OpenGL	HGLRC
	*
	* Note: D3D9 and D3D9Ex are not implemented at this time
	*/
	virtual void SetGraphicsDevice( Compositor_DeviceType eType, void* pDevice ) = 0;

	/** Returns pose(s) to use to render scene. */
	virtual void WaitGetPoses( VR_ARRAY_COUNT(unPoseArrayCount) TrackedDevicePose_t* pPoseArray, uint32_t unPoseArrayCount ) = 0;

	/** Updated scene texture to display. If pBounds is NULL the entire texture will be used.
	*
	* OpenGL dirty state:
	*	glBindTexture
	*/
	virtual void Submit( Hmd_Eye eEye, void* pTexture, Compositor_TextureBounds* pBounds ) = 0;

	/** Clears the frame that was sent with the last call to Submit. This will cause the 
	* compositor to show the grid until Submit is called again. */
	virtual void ClearLastSubmittedFrame() = 0;

	/** returns the default settings that will be used for the overlay texture. Fetching these defaults 
	* can be useful if you mostly want the default values but want to change a few settings. */
	virtual void GetOverlayDefaults( Compositor_OverlaySettings* pSettings ) = 0;

	/** Texture to draw over the scene at distortion time. This texture will appear over the world on a quad.
	* The pSettings parameter controls the size and position of the quad. */
	virtual void SetOverlay(void* pTexture, Compositor_OverlaySettings* pSettings ) = 0;

	/** Separate interface for providing the data as a stream of bytes, but there is an upper bound on data that can be sent */
	virtual void SetOverlayRaw(void* buffer, uint32_t width, uint32_t height, uint32_t depth, Compositor_OverlaySettings* pSettings ) = 0;

	/** Separate interface for providing the image through a filename: 
	* can be png or jpg, and should not be bigger than 1920x1080 */
	virtual void SetOverlayFromFile( const char *pchFilePath, Compositor_OverlaySettings* pSettings ) = 0;

	/** Removes the scene overlay texture. */
	virtual void ClearOverlay() = 0;

	/** Returns true if timing data is filled it.  Sets oldest timing info if nFramesAgo is larger than the stored history.
	* Be sure to set timing.size = sizeof(Compositor_FrameTiming) on struct passed in before calling this function. */
	virtual bool GetFrameTiming( Compositor_FrameTiming *pTiming, uint32_t unFramesAgo = 0 ) = 0;

	/** Fades the view on the HMD to the specified color. The fade will take fSeconds, and the color values are between 
	* 0.0 and 1.0. This color is faded on top of the scene based on the alpha parameter. Removing the fade color instantly 
	* would be FadeToColor( 0.0, 0.0, 0.0, 0.0, 0.0 ). */
	virtual void FadeToColor( float fSeconds, float fRed, float fGreen, float fBlue, float fAlpha, bool bBackground = false ) = 0;

	/** Fading the Grid in or out in fSeconds */
	virtual void FadeGrid( float fSeconds, bool bFadeIn ) = 0;

	/** Brings the compositor window to the front. This is useful for covering any other window that may be on the HMD 
	* and is obscuring the compositor window. */
	virtual void CompositorBringToFront() = 0;

	/** Pushes the compositor window to the back. This is useful for allowing other applications to draw directly to the HMD. */
	virtual void CompositorGoToBack() = 0;

	/** Tells the compositor process to clean up and exit. You do not need to call this function at shutdown. Under normal 
	* circumstances the compositor will manage its own life cycle based on what applications are running. */
	virtual void CompositorQuit() = 0;
	
	/** Return whether the compositor is fullscreen */
	virtual bool IsFullscreen() = 0;

	/** Computes the overlay-space pixel coordinates of where the ray intersects the overlay with the
	* specified settings. Returns false if there is no intersection. */
	virtual bool ComputeOverlayIntersection( const Compositor_OverlaySettings* pSettings, float fAspectRatio, vr::TrackingUniverseOrigin eOrigin, vr::HmdVector3_t vSource, vr::HmdVector3_t vDirection, vr::HmdVector2_t *pvecIntersectionUV, vr::HmdVector3_t *pvecIntersectionTrackingSpace ) = 0;
