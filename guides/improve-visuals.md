# Improve Visuals

### Grass Density

Depending on your art style, you should try to have dense grass close to the camera and relatively high falloff, so it blends with the floor texture fairly fast. This way you can have a tradeoff between performance, while still having high grass density close to the camera.

### Base Geometry

Having an irregular mesh, for example, using a mesh consisting of very differently shaped polygons can cause artifacts in the grass density. Either use a mesh made out of very regular polygons or enable mesh normalization in the Nature Mesh Filter.

### Fine Tuning Wind

There are no real rules for setting the wind and you will have to find out the details through experimentation, but there might still be some guidelines to get a nicer look:

1. **Making the wind too slow will make the scene look like it's underwater.** While long grass in real life can look remarkably similar to underwater scenes (believe me, I've checked), wrong settings can exaggerate this, which looks unnatural and strange.
2. Try balancing the wind ripples to the weather you are trying to create. Wind waves alone won't be able to create a convincing result. Wind ripples can also help the lessen the underwater look.
3. If you have balanced both wind waves and ripples, but the grass is still looking too regular, try changing the grass disorder parameter.

### Low density when viewed from above

If you are using a top-down camera, like in an RTS or a city building simulator, the grass directly below your camera seems very low density. You can easily fix this, by enabling the "Improve viewing from above" option in the shader variants settings. It makes grass appear wider when directly below the camera.
