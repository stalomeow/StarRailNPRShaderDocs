# 安装

## 要求

- Unity >= 2022.3.20
- Core RP Library >= 14.0.10
- Universal RP >= 14.0.10

由于一些 API 经常发生变化，建议别用太高的版本。如果安装后有报错，就是版本不合适。

## 从 git URL 安装

1. 在 Package Manager 的添加菜单中选择 `Add package from git URL...`。

    ![安装](../assets/images/install.png)

2. 在文本框中输入：

    ``` txt
    https://github.com/stalomeow/StarRailNPRShader.git
    ```

3. 选择 `Add`。

## 渲染管线设置

- 在 Universal Renderer 上添加 `Honkai Star Rail` Renderer Feature。它内置了屏幕空间阴影，所以接下来要把 URP 的 `ScreenSpaceShadows` Renderer Feature 都移除掉。

    ![Renderer Feature](../assets/images/renderer-feature.png)

- 使用 Linear Color Space。

    ![Linear Color Space](../assets/images/linear-color-space.png)

- 使用 Forward 或 Forward+ 渲染路径，并关闭 Depth Priming。

    ![渲染路径](../assets/images/rendering-path.png)

- 推荐打开 HDR。

    ![HDR](../assets/images/hdr.png)

## 后处理设置

后处理很重要，请务必加上它。

![后处理设置](../assets/images/postprocessing.png)
