# Material Settings

{% embed url="https://youtu.be/kiMk--uVFFI" %}
A general introduction for the DirectX 11 Grass Shader
{% endembed %}

This section will walk though the material settings, which includes most visual and performance related options of the asset.

## Shader Versions

* `Stix Games / Grass`: The regular grass shader with all its features
* `Stix Games / Grass Forward Only`: Like the regular grass, but deferred shading is disabled. Use this to enable all lighting features in deferred rendering. Be aware that this might cause performance loss.

## Shader Settings

Material settings for the DirectX 11 Grass Shader can be categorized in the following categories

* [shader-variants.md](shader-variants.md "mention"): Settings that change the general behavior of the shader.
* [performance-settings.md](performance-settings.md "mention"): Settings that change the density and level of detail of the grass. They have a high impact on performance.
* [visual-settings.md](visual-settings.md "mention"): Settings that change how the grass looks. They generally have a low impact on performance.

{% hint style="warning" %}
This documentation is meant as a general overview of the concepts used in the shader, if you want to know what a specific setting does, look at its tooltip for more information.
{% endhint %}
