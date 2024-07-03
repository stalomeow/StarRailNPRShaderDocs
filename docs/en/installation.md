# Installation

## Requirements

- Unity >= 2022.3.20
- Core RP Library >= 14.0.10
- Universal RP >= 14.0.10

Since the API frequently changes, it is recommended not to use a version that is too high. If any error occurs after installation, the version is inappropriate.

## Install via git URL

1. Select `Add package from git URL...` from the add menu of Package Manager.

    ![Install](../assets/images/install.png)

2. Enter the following in the text box:

    ```txt
    https://github.com/stalomeow/StarRailNPRShader.git
    ```

3. Select `Add`.

## Render Pipeline Settings

- Add `Honkai Star Rail` Renderer Feature to the Universal Renderer. It has built-in screen space shadows, so remove the `ScreenSpaceShadows` Renderer Feature of URP.

    ![Renderer Feature](../assets/images/renderer-feature.png)

- Use Linear Color Space.

    ![Linear Color Space](../assets/images/linear-color-space.png)

- Use Forward or Forward+ Rendering Path and disable Depth Priming.

    ![Rendering Path](../assets/images/rendering-path.png)

- It is recommended to enable HDR.

    ![HDR](../assets/images/hdr.png)

## Post-processing Settings

Post-processing is important; be sure to add it.

![Post-processing Settings](../assets/images/postprocessing.png)
