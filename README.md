# AIGC Studio

一个纯前端的 Agnes AI 图像与视频创作工作台。项目只有静态文件，可以直接部署到 GitHub Pages 使用。

## 功能

- 图片生成：支持文生图、图生图。
- 视频生成：支持文生视频、图生视频、多图视频、关键帧动画。
- 参考图上传：本地图片会在浏览器中转成 Data URI Base64，不依赖 S3 或对象存储。
- 参数配置：支持尺寸、分辨率、时长、帧率、反向提示词、种子、推理步数和 `extra_body`。
- 视频任务：创建任务后自动轮询，完成后可在线播放和下载。
- 主题切换：支持午夜、晨光、胶片三套主题。
- 请求预览：页面会展示当前表单对应的请求体，便于调试。

## 使用方式

直接打开 `index.html` 即可使用。

首次使用时点击右上角“令牌设置”，填入 Agnes API Key。令牌只保存在当前浏览器的 `localStorage` 中，不会写入代码文件。

## 部署到 GitHub Pages

1. 将本项目推送到 GitHub 仓库。
2. 打开仓库的 `Settings`。
3. 进入 `Pages`。
4. 在 `Build and deployment` 中选择：
   - `Source`: `Deploy from a branch`
   - `Branch`: `main`
   - `Folder`: `/ (root)`
5. 保存后等待 GitHub Pages 完成部署。

如果仓库名为 `aigc-studio`，部署地址通常是：

```text
https://zyscodes.github.io/aigc-studio/
```

## 接口

默认 API Base URL：

```text
https://apihub.agnes-ai.com
```

使用的模型：

- 图片：`agnes-image-2.1-flash`
- 视频：`agnes-video-v2.0`

## 安全说明

不要把 API Key 写进 `index.html`、`README.md` 或任何提交到 GitHub 的文件中。

GitHub Pages 是公开网页，任何访问页面的人都应该使用自己的 Agnes API Key。
