Sets the graphics device or context for the application that is going to feed images to the compositor. The type of the pDevice parameter must match the type that is provided:

	Compositor_DeviceType_D3D9		IDirect3DDevice9*
	Compositor_DeviceType_D3D9Ex	IDirect3DDevice9Ex*
	Compositor_DeviceType_D3D10		ID3D10Device*
	Compositor_DeviceType_D3D11		ID3D11Device*
	Compositor_DeviceType_OpenGL	HGLRC

Note: D3D9 and D3D9Ex are not implemented at this time

	virtual void SetGraphicsDevice( Compositor_DeviceType eType, void* pDevice ) = 0;