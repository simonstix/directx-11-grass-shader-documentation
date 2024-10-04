# Interaction System

{% embed url="https://youtu.be/ECD5htgbB4k" %}

The interaction system is a flexible and customizable system that can be used to add a variety of effects to your project. While it doesn't contain any simulations, it uses a performance rendering system that enables you to have hundreds of interactors. With careful grouping, even thousands of interactor could be supported.

### How-To: Set up grass interaction rendering in your scene

1. Create a new empty object in your scene.
2. Add Component: `Stix Games > Interaction > Render Texture Interaction`, this will also create a camera component, which should be set up and disabled automatically.
3. Change the Size field on the Camera component. The size will define the area where grass interaction will be rendered. Outside, no grass interaction will occur.
4. Change the settings of the Render Texture Interaction component to fit your use case. Tooltips explain the settings in more detail.
5. Optional: Add Component: `Stix Games > Interaction > Camera Follow`
6. Add your main camera to the Camera Follow component.

If your camera size is large enough, you should never be able to see the area outside of the interaction area, as long as the interaction renderer is kept close to your main camera.

{% hint style="info" %}
Like with any other camera, the interaction renderer can't render anything outside its near and far plane, for example, objects above it. You should try to keep your interaction objects at reasonable heights, even though their height doesn't matter. You could also change the near and far clipping planes as necessary.
{% endhint %}

### How-To: Create an interaction object

### Create an interaction material

1. In the project window, navigate to the folder where you want to create your grass material.
2. Right click > Create > Material
3. Select the shader: `Stix Games / Grass Interaction / Interaction`
4. Add any normal, alpha, or burn maps you require.
5. Create a mesh for your displacement object, for example a quad object, and add the new material as usual.
6. Add Component to the new object: `Stix Games > Interaction > Interaction Object`
7. Disable the mesh renderer, but don't delete it, it is used to store the material. You can enable the mesh renderer for debugging your interaction object.

If your new interaction object is within the render area of your interaction renderer, all grass materials should react to it automatically.

### Interaction Shaders

### Interaction Shader

The Interaction shader can be used for a variety of interaction effects, for example, characters walking through the grass and leaving a trail, explosions burning away grass, new buildings dynamically removing grass, etc.

#### Influence Strength

This setting doesn't change the strength of your setting, but it will change how strongly it will override other interactors. If an interactor with influence 100 is overlapping an interactor with influence strength 1, it first one will override the second one.

You can use this to create an interaction area around your character, that will be stronger than any other interactor effect, so even with trails on the ground or explosion shockwaves, the grass will still move away from the character.

#### Grass Interaction Direction

The Interaction shader has two ways of defining the direction of grass movement:

1. Normal Map: Usually normal maps are used for additional lighting information. They tell the shader which direction the area at the position of each pixel is oriented in, e.g. which normal is at the surface's position.\
   It is the same for the Interaction shader, the grass will move approximately in the direction of your surface normal.
2. The interaction mesh itself. The shader will take the normal / direction of your object and apply the normal map to it. For example, a pyramid without a normal map would push away the grass in 4 separate directions, a cone would push the grass away in a circle.

#### Mask

You can use a mask texture to mask out certain areas of your normal and burn maps.

#### Burn Interaction

The interaction system not only supports moving the grass in any direction but also dynamically removing and coloring grass.

The RGB channels of your burn map and burn color define the color the grass will be burned in, usually, this would be a dark brown. The color is changed with a "Multiply" operation, in other words, the grass color can only be darkened and a white burn color will leave the grass untouched.

The alpha channel of your burn map is used to define how much grass will be removed in the area.

{% hint style="info" %}
You can use this feature for burning grass after explosions or fire, but you could also use it to dynamically remove grass in the area of player-built buildings, or other dynamic elements. Simply leave the burn map empty and the burn color white.
{% endhint %}

### Wind

You can use the wind interaction shader to create wind areas with the same wind algorithm as the global wind in the grass shader. If you disable the global wind on your grass material, you could use interaction objects with this shader to create complex weather systems.

### Interaction Renderers

### Interaction Object

Add this script to an object with a mesh renderer and it will automatically submit it to a render queue for all interaction objects. You don't have to manage the objects layer, simply add the component and the interaction system will be able to handle it.

### Interaction Trail Renderer

The interaction trail renderer, as the name suggests, renders a trail behind an object. It will automatically keep track of the object's position and create a trail dynamically.

The trail renderer's material must have a normal map to define the interaction.

#### Animation curve controls

The trail renderer uses animation curves to give more customizability to some of its controls. This might seem strange at first, but it's quite easy to use.

The animation curve is used to calculate the value depending on its lifetime, it starts at 0 and ends at 1 (the end of the trails lifetime). At each point, the base value of the parameter (like width) is multiplied by the corresponding animation curve.

For example: If you have a width of 1 and an animation curve that linearly decreases from 1 to 0, your trial will have a width of 1 at the start and linearly get smaller with age, until it has a width of 0. You can use this to create complex patterns and have perfect control over your application.

In this example, you can see an animation curve for the `Strength` variable. The strength starts at `Base Strength` (1), slowly starts to decrease and smoothly fades to 0, where the trail won't be visible at all.

{% hint style="info" %}
You should try to smooth the strength (and/or width) to 0 at the end of the trails lifetime (time value 1), so the trail doesn't end abruptly.
{% endhint %}

#### Jump Detection

If enabled, the jump detection will check the current distance from the defined floor layers. While the object is further down than the Jump Detection Distance, the trail will not be rendered, leaving a gap between the start and the end of the trail.

### Performance

To support multiple interactors to stack on top of each other, without losing information, it was necessary to create a custom renderer. Each render pass causes a fairly large overhead (compared to other render passes), so it is recommended to either keep the interactors as low as possible or combine multiple interactors into one. For example, if you have a large number of Units in an RTS game, where you are sure that they will never occupy the same grass area, you could create a custom mesh, where each unit has a textured quad centered at its position. If you are doing this correctly, it can be very fast. The interaction renderer will then use this procedural mesh to render a single pass, which reduces the overhead significantly.

As long as you stay below several hundreds of interactors, this should not be a problem, however. I would recommend using the profiler to find your performance bottlenecks in general.
