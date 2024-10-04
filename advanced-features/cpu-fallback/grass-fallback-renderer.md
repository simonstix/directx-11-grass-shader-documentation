# Grass Fallback Renderer

The controls for the grass fallback renderer are created to mimic the behavior of the grass shader. Further visual improvements can be expected in future updates.

## Instancing

Grass fallback can be run purely on the CPU, or use GPU instancing to optimize the renderer. If your hardware supports it, you should probably use instancing.

## Levels of Detail

The fallback renderer runs on the CPU, so we can have more control over LOD than with the shader.

Set the number of levels in the LOD array, then configure the following settings:

* **Density**: The number of billboards per unit.
* **Fade Start**: The distance at which the billboards will start to fade away.
* **Fade End**: The distance where the level of detail will be completely faded away.

{% hint style="info" %}
Unlike the grass shader, where Target Density is still a fairly vague value, the density for the grass fallback represents the number of billboards per Unity unit (meter).
{% endhint %}
