Updated scene texture to display. If pBounds is NULL the entire texture will be used.

    OpenGL dirty state:
        glBindTexture

	virtual void Submit( Hmd_Eye eEye, void* pTexture, Compositor_TextureBounds* pBounds ) = 0;
