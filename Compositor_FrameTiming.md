Provides a single frame's timing information to the app

    struct Compositor_FrameTiming
    {
        uint32_t size; // sizeof(Compositor_FrameTiming)
        double frameStart;
        float frameVSync; // seconds from frame start
        uint32_t droppedFrames;
        uint32_t frameIndex;
        vr::TrackedDevicePose_t pose;
    };