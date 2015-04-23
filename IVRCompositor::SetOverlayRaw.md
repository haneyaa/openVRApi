Separate interface for providing the data as a stream of bytes, but there is an upper bound on data that can be sent.

	virtual void SetOverlayRaw(void* buffer, uint32_t width, uint32_t height, uint32_t depth, Compositor_OverlaySettings* pSettings ) = 0;
