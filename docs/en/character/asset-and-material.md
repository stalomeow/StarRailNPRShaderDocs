# Asset and Material

## Processing Assets

Textures and models of characters need to be set up correctly before they can be used. This is a repetitive and tedious task, so this project provides an asset processor. After importing an asset, if its path meets certain requirements, the asset processor will automatically apply presets to it without the need for manual modification of the asset settings. For models, it can also automatically smooth their normals.

Default texture filename formats:

- `Avatar_*_Ramp*`
- `Avatar_*_LightMap*`
- `Avatar_*_Color*`
- `Avatar_*_Stockings*`
- `M_*_*_FaceMap*` or `W_*_*_FaceMap*`
- `M_*_*_Face_ExpressionMap*` or `W_*_*_Face_ExpressionMap*`

Default model filename formats:

- `Avatar_*_*.fbx` or `Art_*_*.fbx`

By default, case is ignored. `*` represents zero or more characters.

??? question "Configure Asset Processor"

    The asset processor can be configured in `Project Settings/StarRail NPR Shader/HSR Asset Processors`.

    ![Asset Processor](../../assets/images/asset-processor.png)

    - `Match Mode`: The matching mode for assets.

        - `Name Glob`: `Path Pattern` uses a syntax similar to Unix Glob, ignoring case, to match the asset's name (including the extension).

            - `*`: Matches zero or more characters.
            - `?`: Matches exactly one character.
            - `|`: Separates multiple Globs. For example, `a.* | b.*` means matching either `a.*` or `b.*`.

        - `Regex`: Treats `Path Pattern` as a regular expression to match the complete asset path.
        - `Equals`: Matches successfully if the complete asset path is equal to `Path Pattern`.
        - `Contains`: Matches successfully if the complete asset path contains `Path Pattern`.
        - `Starts With`: Matches successfully if the complete asset path starts with `Path Pattern`.
        - `Ends With`: Matches successfully if the complete asset path ends with `Path Pattern`.

    - `Path Pattern`: The pattern string.
    - `Ignore Case`: Whether to ignore case during matching.
    - `Custom Preset`: Custom preset. If empty, the default preset is used.
    - `Smooth Normal Store Mode`: The mode for storing smoothed normals in models.

## Shaders

- Honkai Star Rail/Character/Body
- Honkai Star Rail/Character/Body (Transparent)
- Honkai Star Rail/Character/EyeShadow
- Honkai Star Rail/Character/Face
- Honkai Star Rail/Character/FaceMask
- Honkai Star Rail/Character/Hair

## Materials

- Remember to reset after changing shaders.
- If there is no Outline/Rim-Light, adjust the `Model Scale` on the Material.
