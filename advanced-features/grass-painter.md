# Grass Painter

{% embed url="https://youtu.be/CFql3cRzsf4" %}

The grass painter is a tool that simplifies the creation of density textures. Instead of having to edit the texture in an external program, you can paint directly on your mesh or terrain. It also includes some helper functionallity, like changing the density mode and creating textures automatically.

{% hint style="info" %}
Alternatively, you can still create the texture in any application you want, for example procedurally create it in substance designer, or your terrain creator of choice.
{% endhint %}

## Opening the grass painter

To open the grass painter window you can either select the grass object, expand the Grass Renderers material settings and click on the button _"Open Grass Painter"_ in the material settings, or click the menu item `Window / Stix Games / Grass Painter`.

{% hint style="danger" %}
Closing the grass painter window or switching grass objects will make changes permanent, so undoing previous changes will be impossible.
{% endhint %}

## Targets

* **Color / Height**: Modifies the color and height of your grass material. On the texture, the channels RGB are used for color, and the alpha channel is used for height.
* **Density**: Modifies the density of your grass material. Each color channel represents one grass type.

## Brush Mode

* **Add**: Add more grass. By drawing on the same area, you will add grass depending on your strength setting, until you reach the maximum.
* **Remove**: Remove grass. By drawing on the same area, you will remove grass depending on your strength setting, until no grass is left.
* **Set**: Set the amount of grass exactly to your strength setting. Drawing on the same area will not make changes, once you’ve reached the desired density.

## Other Settings

Check the tooltips of each setting for more information.

## Careful: Material Duplication

Be careful when using the same material on multiple objects. Changing one object will edit the grass on all other objects.

To solve this, you can duplicate the material and duplicate the changed textures.

{% hint style="danger" %}
If you don't remove or duplicate the textures you wish to paint on the duplicated material, you will still paint on the same texture, even though it's a different material.
{% endhint %}

