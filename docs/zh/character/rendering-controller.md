# 渲染控制器

角色的根物体上会自动添加 `StarRail Character Rendering Controller` 组件。

![角色渲染控制器](../../assets/images/character-rendering-controller.png)

## 控制渲染

修改该组件面板上的参数就能控制一部分渲染效果。

## 同步 MMD 模型的头骨骼

如果使用 MMD 模型，需要将头部骨骼的 `Transform` 拖给 `Head Bone` 字段。

![同步头骨骼](../../assets/images/mmd-head-bone-sync.png)

## C# API

### Properties

|名称|描述|
|:-|:-|
|`RampCoolWarmMix`|冷暖 Ramp 图的混合程度。0 是冷，1 是暖。范围 `[0, 1]`。|
|`DitherAlpha`|角色的透明度。范围 `[0, 1]`。|
|`ExpressionCheekIntensity`|脸颊泛红程度。范围 `[0, 1]`。|
|`ExpressionShyIntensity`|害羞程度。范围 `[0, 1]`。|
|`ExpressionShadowIntensity`|黑脸程度。范围 `[0, 1]`。|
|`IsCastingShadow`|是否投射阴影。|

### Methods

|名称|描述|
|:-|:-|
|`UpdateRendererList`|更新控制器内部缓存的 `Renderer` 列表。|

## SRP Batcher

- Editor 下使用 [`MaterialPropertyBlock`](https://docs.unity3d.com/ScriptReference/MaterialPropertyBlock.html)，不支持 [SRP Batcher](https://docs.unity3d.com/Manual/SRPBatcher.html)。
- Build 后使用 [`Renderer.material`](https://docs.unity3d.com/ScriptReference/Renderer-material.html)，支持 [SRP Batcher](https://docs.unity3d.com/Manual/SRPBatcher.html)。
