---
layout: default
title: OCG Properties
parent: MapPreset
nav_order: 5
---

# OCG Setting Properties

In this step, you will configure the Procedural Content Generation (PCG) settings. The PCG settings provide various options related to how the level is generated. Select the **PCG Settings** tab in the OCG window and adjust the necessary settings.

## 1. Biome Settings

{: .warning }
> The **order of Layers** in the Landscape Material's Layer Blend **must match the order of Biomes** for PCG to **spawn meshes in the correct areas**.
> For example, if the layer order in the Landscape Material is `Grass`, `Forest`, `Mountain`, the Biome order must also be **the same**: `Grass`, `Forest`, `Mountain`.

![PCG Settings Tab]({{ site.baseurl }}/assets/images/tutorials/basic_tutorial/biome_settings.png)

| Property Name  | Description                                                                                                                     |
| :------------- | :------------------------------------------------------------------------------------------------------------------------------ |
| Biome Name     | The name of the biome. This is used to identify the biome in the system.                                                        |
| Temperature    | The temperature of the biome, which can affect the types of vegetation and terrain features generated.                          |
| Humidity       | The humidity level of the biome, influencing water features and vegetation density.                                             |
| Weight         | The weight of the biome in the overall generation process. Higher weights increase the likelihood of this biome being selected. |
| Mountain Ratio | The ratio of mountains in the biome, affecting the terrain's elevation and features.                                            |

## 2. Hierarchy Data Settings

{: .warning }
> The indices in the Hierarchy Data Settings are **applied sequentially.**
> Areas where points have already been generated by a higher-priority index are **excluded from the regions where subsequent indices can generate points** (this does not apply to entries within the same biome).

![Hierarchy Data Settings]({{ site.baseurl }}/assets/images/tutorials/basic_tutorial/hierarchy_data_settings.png)

<details markdown="1">
  <summary>Basic Settings</summary>

| Property Name                 | Description                                                                                                                                                                                                                                     |
| :---------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Biome Name                    | The name of the biome. This is used to identify the biome in the system.                                                                                                                                                                        |
| Selected Landscape Layer Name | The name of the selected Landscape Layer. The biome will be applied to this layer. <br> If it shows `None`, the Biome Name may be incorrect, or the Landscape Material has not been set.                                                        |
| Seed                          | Sets the random seed. <br> This value determines the randomness when the biome's meshes are spawned. <br> Using the same seed will produce the same results.                                                                                    |
| Blending Ratio                | The blending ratio of the biome. This value determines how smoothly the boundary between biomes is blended. <br> A value of 0.0 results in a sharp boundary, while 1.0 is fully blended.                                                        |
| Points Per Square Meter       | Determines the density of points for spawning meshes in the biome. <br> This value controls how finely the biome's meshes are spawned. <br> For example, a value of 10 generates 10 points per square meter.                                    |
| Looseness                     | Determines the looseness of the points where the biome's meshes are spawned.                                                                                                                                                                    |
| Point Extents                 | Determines the size of the area where meshes will be spawned. <br> This value affects the calculation of the number of points and defines the spawning area size. <br> For example, 100 means meshes will spawn in a 100x100 square meter area. |
| Point Steepness               | Determines how far apart points will be from each other when spawned. <br> A higher value results in meshes being spawned further apart.                                                                                                        |
| Slope Limits                  | Determines the range of slopes on which meshes can be spawned. <br> For example, if Min Angle is 0° and Max Angle is 45°, meshes will only spawn on slopes between 0° and 45°.                                                                  |
| Transform Point               | Determines the transform of the point. <br> This value controls the position, rotation, and scale of the mesh when it is spawned.                                                                                                               |
| Pruning Overlapped Points     | Determines whether to remove overlapped points.                                                                                                                                                                                                 |
| Meshes                        | Selects the meshes to spawn. <br> This determines which meshes will be used when the biome's meshes are spawned. <br> You can select multiple meshes, and one will be chosen randomly.                                                          |
| Point Debug Color             | Sets the debug color for the points. <br> This value determines the debug color when points are spawned, allowing you to visually confirm their locations.                                                                                      |

</details>

<details markdown="1">
  <summary>Optimization Settings</summary>

| Property Name                  | Description                                                                                                                                                                                                                                                                   |
| :----------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| WPO Disable Distance           | Determines the distance at which to disable World Position Offset (WPO). <br> Meshes beyond this distance will not have WPO applied. <br> For example, a value of 1000 means WPO is disabled for meshes more than 1000 meters away.                                           |
| Start Cull Distance            | Sets the distance at which culling begins.                                                                                                                                                                                                                                    |
| End Cull Distance              | Sets the distance at which culling ends. <br> This determines how far away a spawned mesh must be before it is culled (not rendered). <br> For example, with a Start Cull Distance of 1000 and an End Cull Distance of 2000, meshes will become invisible beyond 1000 meters. |
| Affect Distance Field Lighting | Determines whether the mesh affects Distance Field Lighting. <br> Enabling this allows the mesh to contribute to Distance Field Lighting. <br> This can impact performance, so it is recommended to enable it only when necessary.                                            |
| Execute on GPU                 | Determines whether to execute the generation on the GPU. <br> If enabled, meshes will be generated on the GPU.                                                                                                                                                                |

</details>
