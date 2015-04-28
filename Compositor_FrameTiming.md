Provides a single frame's timing information to the app


Always set 'size' to sizeof(Compositor_FrameTiming) for proper versioning and avoid memory corruption.  In C# use:

	(uint)System.Runtime.InteropServices.Marshal.SizeOf(typeof(Compositor_FrameTiming));

### Properties ###

**frameStart** - Time reference for each frame.  This won't necessarily be evenly spaced.

**frameVSync** - Time from frameStart until the next VSync.  Using (current.frameStart + current.frameVSync) - (previous.frameStart + previous.frameVSync) should be a reliable way to measure frame intervals.

**droppedFrames** - Number of droppedFrames as reported by DXGI's GetFrameStatistics since the previous frame.  This is a delta of PresentRefreshCount since the last time we called it.  It is stored unsigned, but has been known to go negative, so should be cast to an int before using.

**frameIndex** - Incremented each frame.  Can be used to call [GetFrameTiming](https://github.com/ValveSoftware/openvr/wiki/IVRCompositor::GetFrameTiming) at a lower frequency than it's being updated to iterate through the history until you see a frame you recognize.

**pose** - Hmd pose used to render this frame.

    struct Compositor_FrameTiming
    {
        uint32_t size; // sizeof(Compositor_FrameTiming)
        double frameStart;
        float frameVSync; // seconds from frame start
        uint32_t droppedFrames;
        uint32_t frameIndex;
        vr::TrackedDevicePose_t pose;
    };

