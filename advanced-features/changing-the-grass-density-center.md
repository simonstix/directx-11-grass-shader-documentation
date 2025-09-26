# Changing the grass density center

When working with a top-down perspective, it's often preferable to move the center of the grass density somewhere other than the camera. Since version `2.10.0` it's possible to do that by adding the `Grass Density Center Override` component to the object you want as the new center. The script automatically sets the required shader keywords and updates the density center to the transform's position in `LateUpdate`.

If you want to switch between camera-based and object-based density centers, you can disable or remove the component.&#x20;

{% hint style="warning" %}
Make sure that only one Grass Density Center Override is active at a time. If more than one is active during the components `OnEnable` event, the second component will be ignored and won't function until you disable and re-enable it again.
{% endhint %}
