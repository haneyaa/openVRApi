`bool LoadRenderModel( const char *pchRenderModelName, RenderModel_t *pRenderModel )`
	
Loads and returns a render model for use in the application.

* `pchRenderModelName` - Name of the render model to load.
* `RenderModel_t *pRenderModel` - struct to receive the render model.

**Description**

Loads and returns a render model for use in the application. pchRenderModelName should be a render model name
from the Prop_RenderModelName_String property or an absolute path name to a render model on disk. 

The resulting render model is valid until VR_Shutdown() is called or until FreeRenderModel() is called. When the 
application is finished with the render model it should call FreeRenderModel() to free the memory associated
with the model.

The method returns false if the model could not be loaded.

The API expects that this function will be called at startup or when tracked devices are connected and disconnected.
If it is called every frame it will hurt performance.

**Render model structs**

These structures are used by the render model functions:
	/** a single vertex in a render model */
	struct RenderModel_Vertex_t
	{
		HmdVector3_t vPosition;		// position in meters in device space
		HmdVector3_t vNormal;		
		float rfTextureCoord[ 2 ];
	};

	/** A texture map for use on a render model */
	struct RenderModel_TextureMap_t
	{
		uint16_t unWidth, unHeight; // width and height of the texture map in pixels
		const uint8_t *rubTextureMapData;	// Map texture data. All textures are RGBA with 8 bits per channel per pixel. Data size is width * height * 4ub
	};

	/** Contains everything a game needs to render a single tracked or static object for the user. */
	struct RenderModel_t
	{
		uint64_t ulInternalHandle;					// Used internally by SteamVR
		const RenderModel_Vertex_t *rVertexData;			// Vertex data for the mesh
		uint32_t unVertexCount;						// Number of vertices in the vertex data
		const uint16_t *rIndexData;						// Indices into the vertex data for each triangle
		uint32_t unTriangleCount;					// Number of triangles in the mesh. Index count is 3 * TriangleCount
		RenderModel_TextureMap_t diffuseTexture;	// RGBA diffuse texture for the model
	};
