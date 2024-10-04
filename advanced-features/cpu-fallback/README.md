# CPU Fallback

{% embed url="https://youtu.be/EmygWbou-uM" %}

The CPU Fallback is meant as an easy to use alternative to the DirectX 11 Grass shader. As Unity's OpenGL cross compiler has some problems and instabilities when used with high-end shader effects (e.g. geometry shaders and tessellation), it is still impossible to use the grass shader for consoles and mobile devices (although some consoles have been reported to work, you should try it yourself to be sure).

Instead of having to create a billboard texture manually, the goal of the grass fallback system is to automatically render a snapshot of your grass material in action, which can then be used on non-PC hardware, or lower end devices.

Alternatively, you could also use it as your main grass solution, by designing the material with the shader and using the fallback as your main grass renderer.
