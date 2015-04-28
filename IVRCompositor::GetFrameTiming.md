Returns true if timing data is filled it.  Sets oldest timing info if nFramesAgo is larger than the stored history.

Be sure to set timing.size = sizeof(Compositor_FrameTiming) on struct passed in before calling this function.

History buffer currently stores last 16 frames of data.

	virtual bool GetFrameTiming( Compositor_FrameTiming *pTiming, uint32_t unFramesAgo = 0 ) = 0;
