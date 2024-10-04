# Grass Texture Atlas Templates

{% embed url="https://youtu.be/JCWJ-2YOd2I" %}

Creating a texture atlas manually is tedious and time-consuming. Texture Atlas Templates automate this process, effectivly eliminating the manual work, once the individual textures have been created.

### How-To: Create a Texture Atlas Template

1.  Create your grass textures. Each texture should have exactly one blade of grass. They should be in sRGB mode (as color textures should always be; unless you know what you're doing).

    Try to have as little empty space as possible, you don't have to add a border padding, the template can handle that for you. The height and width of each texture should be approximately the same, however, this isn't a hard requirement. The template will balance them automatically.
2. Right-click in your project folder > `Stix Games` > `Grass Texture Atlas Template`
3. Rename and select your new template
4. Change settings, like texture size, rows, etc.
5. Lock your inspector, with the lock icon in the top right of the inspector, so you can select other files, while the template is still selected.
6. Select all your blade of grass textures, then drag and drop them into the textures field of the template. You could also set them individually, no locking will be necessary.
7. Unlock your inspector again.
8. Press the `Create texture` button and create the texture where you want it.

### Texture dilation

{% hint style="warning" %}
Dilation works well for textures with very hard borders, e.g. full alpha where the grass is visible and zero alpha where the grass isn't. Textures with smooth borders can cause problems, so you should set dilation steps to 0.
{% endhint %}

Textures have a color value, even when the texture is actually transparent at this position. If the color is black, this can cause black borders around the texture, when mipmaps are used, or the alpha cutoff isn't set perfectly. Texture dilation takes the color of the texture and copies it into the transparent areas.

### Random variations

Instead of fitting all blades of grass into a texture atlas, you can also decide to create random combinations of each blade of grass. Each variation will be a random selection of blades of grass.

The number of blades per texture can be changed with the `Overdraw` setting.

`Variations` defines how many textures will be created.
