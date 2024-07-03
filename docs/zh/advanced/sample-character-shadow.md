# 采样角色阴影

## 使用屏幕空间阴影

角色的逐物体阴影和 Unity 内置的阴影会被合并到一张屏幕空间阴影图上。

根据前面的渲染流程图，如果你的材质在 `URP Opaque` 阶段被渲染，只需要给它加上 `_MAIN_LIGHT_SHADOWS_SCREEN` Keyword，然后用 URP 默认方法采样主光源阴影即可。

## 手动采样

对于其他阶段被渲染的材质，以及不支持屏幕空间阴影的透明材质，可以手动采样角色阴影。

开启软阴影。

``` hlsl
#pragma multi_compile_fragment _ _SHADOWS_SOFT
```

引入文件。

``` hlsl
#include "Packages/com.stalomeow.star-rail-npr-shader/Shaders/Shadow/PerObjectShadow.hlsl"
```

使用世界空间坐标采样所有角色阴影。

``` hlsl
float shadow = MainLightPerObjectSceneShadow(positionWS);
```
