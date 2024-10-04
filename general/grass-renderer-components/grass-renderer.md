# Grass Renderer

The grass renderer takes the processed mesh from the Nature Mesh Filter and renders your grass material.

It can also be used to automatically set the floor color and texture for your material, you should be careful not to use the same material with multiple renderers in this case, or they might interfere with each other.

{% hint style="info" %}
The grass material could also be used like a regular material, however, you need to duplicate the floor object for this. This way you lose the ability of mesh normalization and grass fallback, so it is recommended that you always use the Nature Mesh Filter and Grass Renderer components. If your project was made with pre 2.0 versions of the shader you can still use the old workflow, but I would recommend migrating to the new system.
{% endhint %}
