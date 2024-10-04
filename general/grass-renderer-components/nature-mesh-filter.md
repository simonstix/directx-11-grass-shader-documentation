# Nature Mesh Filter

The Nature Mesh Filter is the bridge between the regular Mesh Filter or Unity Terrain, the Grass Renderer, and the Grass Fallback Renderer. It also supports preprocessing the mesh, so deformed meshes with irregular polygon sizes can automatically be processed, so the blades of grass appear smooth and without artifacts.

The mesh normalization should only be enabled when necessary and you should try to use as little polygons as possible, to improve performance.

{% hint style="info" %}
The Nature Mesh Filter works with regular meshes and Unity terrain, you can treat them the same and the filter will take care of the conversion.
{% endhint %}
