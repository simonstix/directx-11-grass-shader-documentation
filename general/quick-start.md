# Quick Start

{% embed url="https://youtu.be/kiMk--uVFFI" %}
A general introduction for the DirectX 11 Grass Shader
{% endembed %}

## Create a grass material

1. In the project window, navigate to the folder where you want to create your grass material.
2. Right click > Create > Material
3. Select the shader: `Stix Games / Grass` or `Stix Games / Grass Forward Only`

## Render the grass on your custom mesh of Unity terrain

1. Select your floor object. This can be a custom mesh or a Unity terrain, the process is the same. Make sure you have selected the object with the `Mesh Filter` or `Terrain` component.
2. Add Component: `Stix Games > General > Nature Mesh Filter`
3. Add Component: `Stix Games > General > Grass Renderer`
4. Select your grass material in the Grass Renderers Material Field
5. Configure all settings to your liking

## Customize you material

Now it's all about what you want to create. Check the [material-settings](material-settings/ "mention") page, read tooltips, and try playing around with the material. The various settings can drastically change the looks and performance impact of your grass.&#x20;

If you ever get stuck, come back to this documentation, check the [performance-optimization.md](../guides/performance-optimization.md "mention") guide, or contact me via my [support email](mailto:support@stixgames.com), the [contact form](https://stixgames.com/contact), or [Discord](https://discord.gg/jvBFhQA)!
