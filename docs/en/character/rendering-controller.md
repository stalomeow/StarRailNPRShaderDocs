# Rendering Controller

The `StarRail Character Rendering Controller` component is automatically added to the root object of the character.

![Character Rendering Controller](../../assets/images/character-rendering-controller.png)

## Controlling Rendering

You can control some rendering effects by modifying the parameters in the inspector.

## Synchronizing MMD Model's Head Bone

If you are using MMD models, you need to drag the `Transform` of the head bone to the `Head Bone` field.

![Synchronizing Head Bone](../../assets/images/mmd-head-bone-sync.png)

## C# API

### Properties

|Name|Description|
|:-|:-|
|`RampCoolWarmMix`|Blend level of the cool and warm Ramp textures. 0 is cool, 1 is warm. Range `[0, 1]`.|
|`DitherAlpha`|Transparency of the character. Range `[0, 1]`.|
|`ExpressionCheekIntensity`|Degree of cheek blush. Range `[0, 1]`.|
|`ExpressionShyIntensity`|Shyness level. Range `[0, 1]`.|
|`ExpressionShadowIntensity`|Darkening of the face. Range `[0, 1]`.|
|`IsCastingShadow`|Whether to cast shadows.|

### Methods

|Name|Description|
|:-|:-|
|`UpdateRendererList`|Update the internal cached list of `Renderer` in the controller.|

## SRP Batcher

- In Editor, this component uses [`MaterialPropertyBlock`](https://docs.unity3d.com/ScriptReference/MaterialPropertyBlock.html), which does not support the [SRP Batcher](https://docs.unity3d.com/Manual/SRPBatcher.html).
- After Build, this component uses [`Renderer.material`](https://docs.unity3d.com/ScriptReference/Renderer-material.html), which supports the [SRP Batcher](https://docs.unity3d.com/Manual/SRPBatcher.html).
