# 渲染流程图

``` mermaid
flowchart TD
    URPShadowCaster[URP ShadowCaster] --> StarRail1

    subgraph StarRail1[Honkai Star Rail]
        PerObjSceneShadowCaster([MainLight Per-Object Scene ShadowCaster]) --> PerObjSelfShadowCaster
        PerObjSelfShadowCaster([MainLight Per-Object Self ShadowCaster])
    end

    StarRail1 --> URPDepthPrepass[URP DepthPrepass]
    URPDepthPrepass --> StarRail2

    subgraph StarRail2[Honkai Star Rail]
        HairDepthPrepass([Hair DepthPrepass]) --> EnableScreenSpaceShadow
        EnableScreenSpaceShadow([Enable ScreenSpaceShadow])
    end

    StarRail2 --> URPOpaque[URP Opaque]
    URPOpaque --> StarRail3

    subgraph StarRail3[Honkai Star Rail]
        DisableScreenSpaceShadow([Disable ScreenSpaceShadow])
        DisableScreenSpaceShadow --> SROpaque

        subgraph SROpaque["Opaque"]
            direction LR
            SROpaque1([Opaque 1]) --> SROpaque2([Opaque 2])
            SROpaque2 --> SRHair([Hair])
            SRHair --> SROpaque3([Opaque 3])
            SROpaque3 --> SROpaqueOutline([Outline])
        end
    end

    StarRail3 --> URPSkybox[URP Skybox]
    URPSkybox --> URPTransparent[URP Transparent]
    URPTransparent --> StarRail4

    subgraph StarRail4[Honkai Star Rail]
        SRTransparent(["Transparent"]) --> SRPost

        subgraph SRPost[PostProcess]
            direction LR
            SRBloom([Bloom]) --> SRTonemapping([Tonemapping])
        end
    end

    StarRail4 --> URPPost[URP PostProcess]
```

!!! info "注意"

    使用普通 URP Shader 的透明物体和角色身上的透明物体被分成了两批渲染，可能会出问题。
