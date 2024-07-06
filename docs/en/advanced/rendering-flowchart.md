# Rendering Flowchart

``` mermaid
flowchart TD
    URPShadowCaster[URP ShadowCaster] --> StarRail1

    subgraph StarRail1[Honkai Star Rail]
        PerObjShadowCaster([MainLight Per-Object ShadowCaster])
    end

    StarRail1 --> URPDepthPrepass[URP DepthPrepass]
    URPDepthPrepass --> StarRail2

    subgraph StarRail2[Honkai Star Rail]
        HairDepthPrepass([Hair DepthPrepass]) --> EnableScreenSpaceShadow([Enable ScreenSpaceShadow])
    end

    StarRail2 --> URPOpaque[URP Opaque]
    URPOpaque --> StarRail3

    subgraph StarRail3[Honkai Star Rail]
        DisableScreenSpaceShadow([Disable ScreenSpaceShadow]) --> SROpaque([Opaque & Outline])
    end

    StarRail3 --> URPSkyboxTrans[URP Skybox & Transparent]
    URPSkyboxTrans --> StarRail4

    subgraph StarRail4[Honkai Star Rail]
        SRTransparent([Transparent & Outline]) --> SRPost([Bloom & Tonemapping])
    end

    StarRail4 --> URPPost[URP PostProcess]
```

---

Transparent objects using normal URP Shader and transparent objects on characters are divided into two groups for rendering, which may cause problems.
