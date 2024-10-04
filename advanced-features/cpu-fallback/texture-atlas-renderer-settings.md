# Texture Atlas Renderer Settings

These are the settings for the grass fallback preprocessor. It automatically creates a texture atlas from your grass material (taken from the Grass Renderer component).

Read the tooltips for more information on each setting. If you'd like to have more detailed explanations for one of the parameters, or for the tool in general, please use the contact form for your feedback!

The grass fallback and the grass shader aren't perfectly equivalent, so you'll have to do some fine-tuning yourself. The following settings are the most important ones for achieving this goal are the following:

## Texture Atlas

### Target Texture Size

Sets the size of the fallback texture. All density types will share this atlas, so the texture should be fairly large.

### Rows Per Grass Type

How many variants of each grass type will be used? With one row this will be 4 variants, with two rows 8 variations. Higher values will cause more variations, but lower texture quality, per billboard.

### Dilation Steps

{% hint style="warning" %}
Dilation works well for textures with very hard borders, e.g. full alpha where the grass is visible and zero alpha where the grass isn't. Textures with smooth borders can cause problems, so you should set dilation steps to 0.
{% endhint %}

Textures have a color value, even when the texture is transparent at this position. If the color is black, this can cause black borders around the texture, when mipmaps are used, or the alpha cutoff isn't set perfectly. Texture dilation takes the color of the texture and copies it into the transparent areas.

## Grass Amount

### Blades of grass

Probably the most important setting for visuals. This setting defines how many blades of grass will be rendered per billboard at full grass density. You can use this setting to match the fallback closer to the original shader.

## Density

### Density Cutoff

To prevent grass types with very low density from being rendered, adjust this setting. If one of the grass types is in areas where it shouldn't be, increase this value. If a type isn't rendered in an area for the grass fallback, decrease the cutoff value.

### Density Randomization

In an area with equal density, this setting prevents the same texture being used for all billboards. If the setting is 0, the same density will lead to exactly the same billboard texture. If the setting is too high, grass density will no longer be accurate and densities will appear stronger or weaker than intended.
