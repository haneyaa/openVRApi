`void GetProjectionRaw( Hmd_Eye eEye, float *pfLeft, float *pfRight, float *pfTop, float *pfBottom )`

Returns the raw project values to use for the specified eye. Most games should use GetProjectionMatrix instead of this method, but sometimes a game needs to do something fancy with its projection and can use these values to compute its own matrix.

These values can be turned into a projection matrix with the function below. If you are using OpenGL you can accomplish the same thing with a call to glFrustum.

    void ComposeProjection(float fLeft, float fRight, float fTop, float fBottom, float zNear, float zFar,  HmdMatrix44_t *pmProj )
    {
        float idx = 1.0f / (fRight - fLeft);
        float idy = 1.0f / (fBottom - fTop);
        float idz = 1.0f / (zFar - zNear);
        float sx = fRight + fLeft;
        float sy = fBottom + fTop;

        float (*p)[4] = pmProj->m;
        p[0][0] = 2*idx; p[0][1] = 0;     p[0][2] = sx*idx;    p[0][3] = 0;
        p[1][0] = 0;     p[1][1] = 2*idy; p[1][2] = sy*idy;    p[1][3] = 0;
        p[2][0] = 0;     p[2][1] = 0;     p[2][2] = -zFar*idz; p[2][3] = -zFar*zNear*idz;
        p[3][0] = 0;     p[3][1] = 0;     p[3][2] = -1.0f;     p[3][3] = 0;
    }

* `eEye` - Eye_Left or Eye_Right. Determines which eye the function should return the projection for.
* `pfLeft` - coordinate for the left clipping plane
* `pfRight` - coordinate for the right clipping plane
* `pfTop` - coordinate for the top clipping plane
* `pfBottom` - coordinate for the bottom clipping plane

