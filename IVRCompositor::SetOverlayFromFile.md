Separate interface for providing the image through a filename: can be png or jpg, and should not be bigger than 1920x1080.

	virtual void SetOverlayFromFile( const char *pchFilePath, Compositor_OverlaySettings* pSettings ) = 0;
