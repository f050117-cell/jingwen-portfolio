# 冯婧雯｜个人作品集

静态响应式作品集网站，采用 Apple 风格的简约视觉。页面展示 AI × 实拍、商业/实拍视频、动画项目，并在每个项目旁说明创意思路和个人参与。视频弹窗支持手机端行内播放；网站适配 iOS 全面屏安全区。

## 本地预览

在 `outputs` 文件夹运行 `python3 -m http.server 8000`，再打开 `http://localhost:8000`。

## 准备 Netlify 发布文件

`media/videos/` 保存原始视频。网站改用 `media/web/` 中的 H.264 网页播放版本，便于手机播放并减少流量。运行 `./prepare-site.sh` 后，`publish/` 会生成可发布文件，不会把原始视频打包进去。

Netlify 发布时选择 `publish/` 文件夹；使用 CLI 时在项目根目录执行：

```sh
netlify deploy --prod --dir=outputs/publish
```

## 更换视频

1. 把原片放到 `media/videos/`。
2. 导出 H.264 编码 MP4 网页版并放入 `media/web/`，沿用相同文件名。
3. 如需新增项目，在 `script.js` 对应项目数据的 `video` 字段填入 `media/web/文件名.mp4`。
4. 运行 `./prepare-site.sh`，然后重新发布 `publish/`。

发布前请确认作品画面和联系方式可公开展示。项目画面从你提供的作品集 PDF 中提取；联系方式由你提供。
