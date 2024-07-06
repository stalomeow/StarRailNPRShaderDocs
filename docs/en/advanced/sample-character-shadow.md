# Sample Character Shadow

## Using Screen Space Shadow

The per-object shadow of characters and Unity's built-in shadow will be combined into a single screen space shadow map.

According to the previous rendering flowchart, if your material is rendered in the `URP Opaque` pass, you only need to add the `_MAIN_LIGHT_SHADOWS_SCREEN` keyword to it. Then, you can sample the main light shadow using URP's default method.

## Manual Sampling

For materials rendered in other passes and transparent materials that do not support screen space shadow, you can manually sample character shadow.

Enable soft shadow.

```hlsl
#pragma multi_compile_fragment _ _SHADOWS_SOFT
```

Include the file.

```hlsl
#include "Packages/com.stalomeow.star-rail-npr-shader/Shaders/Shadow/PerObjectShadow.hlsl"
```

Sample all character shadow using world space position.

```hlsl
float shadow = MainLightPerObjectSceneShadow(positionWS);
```
