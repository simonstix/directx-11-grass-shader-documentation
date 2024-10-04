# Virtual Reality

### Fix visual artifacts

In VR the camera renders 2 perspectives per frame, one for each eye. The billboard, screen-oriented grass looks good in 2D, however, this relies on some visual faking which will cause a perceived flickering in VR. It is recommended to use the randomized grass orientation, which ensures that the grass is rendered perspectively accurate for each eye.

### Optimization

As performance is extremely important in VR, you should look at the page about performance optimization in detail.

### Grass Fallback

Consider using the grass fallback instead of the shader itself. While the grass shader is very performant, it is still a high-end effect. The grass fallback could be used to reduce this performance cost, while still keeping your art style. This is especially useful if you are creating an application or game that supports both 2D and VR: On regular screens, you could use the shader, while in VR the fallback could be used to improve the performance and reach even higher FPS.
