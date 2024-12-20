# Global Shader Variables

You can use global shader variables to change all materials at once. This can be helpful for creating in-game graphics settings.

{% hint style="warning" %}
Global Shader Variables stay changed when you exit Play Mode!
{% endhint %}

The following table contains the currently supported global shader variables.

| Shader Variable                  | Description                                                                                                                                                                                                                                                                                    |
| -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `_GlobalTargetDensityMultiplier` | <p>Gets multiplied with the Target Density of each grass material.<br>Since Target Density is higher when the number is smaller (for historical reasons), be careful: A multiplier above 1 <strong>reduces</strong> the density, while a multiplier below 1 <strong>increases it</strong>.</p> |
|                                  |                                                                                                                                                                                                                                                                                                |
|                                  |                                                                                                                                                                                                                                                                                                |
|                                  |                                                                                                                                                                                                                                                                                                |
|                                  |                                                                                                                                                                                                                                                                                                |



