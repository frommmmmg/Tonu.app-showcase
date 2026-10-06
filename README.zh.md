<div align="center">

# Tonu.app

[English](README.md) · 中文 · [Español](README.es.md) · [Deutsch](README.de.md) · [Français](README.fr.md)

</div>

> **本仓库仅用于展示，不公开源码。** Tonu.app 是私有项目，所以这里没有代码，只介绍它做什么、怎么构建、长什么样。想聊聊它，请通过我的 [GitHub 主页](https://github.com/frommmmmg)联系我。

**丢进一张照片，得到几十张设计灵感流风格的色板海报，挑一张，调好每个细节，再保存 PNG 或分享。** 全部在浏览器里完成，除非你主动分享，否则不会上传任何东西。

**亮点**

- **按感知取色。** 图片先缩小，转到 **OKLab**，用 **k-means++** 聚类并给每个簇打分，再用加权最远点采样挑出既有代表性又彼此区分的颜色。
- **老实的颜色命名，而且按你的语言。** 名称取自公开色名表（ISCC-NBS、CSS、Tailwind、Material、xkcd）中 OKLab 距离最近的一项，不做机器翻译。日本传统色、中国传统色等传统色名体系已经内置。
- **是样式引擎，不是模板。** 一个样式就是一份 JSON 规格。**15 种布局引擎、30 多个预设、约 90 个可调参数**，包括 8 种圆形布局、阴影、质感、光泽、边框和照片处理。
- **可以在海报上直接拖动色板。** 自由移动或吸附到某一侧，也可以用滑块精确设置偏移量。拖动要移动几个像素后才开始，所以轻点仍然是复制色值。
- **手机上的悬浮预览窗。** 你往下滚动调参数时，海报会留在一个可拖动、可缩放、可固定的小窗里。双指捏合、鼠标滚轮或 +/- 都能像放大镜一样放大，最高 8 倍，改参数的同时可以盯着细节看。
- **悬停即预览。** 鼠标指到某个选项上，就能在当前海报上看到效果，确定后再选。
- **5 套界面皮肤，各有亮色和暗色：** 校样室、白墙、纸刊、多彩、终端。按需加载，只改界面，不改海报。
- **可停靠的操作台。** 设置面板可以放在左边、下边或右边，拖动边缘调整大小，选择会记在这台设备上。
- **14 种界面语言。**
- **导出与屏幕所见一致。** 字体会嵌进图片，PNG 在任何设备上都一样；手机上直接调起系统分享面板，最近的作品保存在本机。
- **字体处理规范。** 内置 12 款开源授权字体，也支持载入你自己的文件、网址或本机已安装字体，并明确写出授权责任。

**技术栈：** 原生 JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1（用于分享的海报）

线上地址：**[tonu.app](https://tonu.app)**。截图里的示例照片来自 Unsplash，作者 Andrés Beltrán Espinosa。

## 截图

![画廊：一张照片，多种海报样式。](assets/tonu-gallery.jpg)
*画廊：一张照片，多种海报样式。*

![大图视图，设置面板在旁边实时生效。](assets/tonu-focus.jpg)
*大图视图，设置面板在旁边实时生效。*

<table><tr><td align="center" width="33%"><img src="assets/tonu-skin-default.jpg" alt="校样室"><br><sub>校样室</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-white.jpg" alt="白墙"><br><sub>白墙</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-paper.jpg" alt="纸刊"><br><sub>纸刊</sub></td></tr><tr><td align="center" width="33%"><img src="assets/tonu-skin-multicolor.jpg" alt="多彩"><br><sub>多彩</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-terminal.jpg" alt="终端"><br><sub>终端</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-multicolor-dark.jpg" alt="多彩（暗色）"><br><sub>多彩（暗色）</sub></td></tr></table>

*5 套界面皮肤，每套都有亮色和暗色模式。*

![在海报上任意拖动色板。](assets/tonu-drag.jpg)
*在海报上任意拖动色板。*

![手机上：画廊、设置上方的悬浮预览窗，以及放大到 338% 的预览。](assets/tonu-mobile.jpg)
*手机上：画廊、设置上方的悬浮预览窗，以及放大到 338% 的预览。*

<table><tr><td align="center" width="50%"><img src="assets/tonu-dock-bottom.jpg" alt="下边"><br><sub>下边</sub></td><td align="center" width="50%"><img src="assets/tonu-dock-left.jpg" alt="左边"><br><sub>左边</sub></td></tr></table>

*操作台停靠在下边和左边。*

![同一个界面的四种语言（共 14 种）。色名会跟着语言走，比如日本传统色。](assets/tonu-languages.jpg)
*同一个界面的四种语言（共 14 种）。色名会跟着语言走，比如日本传统色。*

## 工作原理

![一次修改，画廊、大图和悬浮预览窗同时更新。](assets/tonu-live-sync.svg)
*一次修改，画廊、大图和悬浮预览窗同时更新。*

![从取色到导出，全部在浏览器里运行。](assets/tonu-extraction-pipeline.svg)
*从取色到导出，全部在浏览器里运行。*

![样式是 JSON 规格，由布局引擎渲染成海报。](assets/tonu-style-engine.svg)
*样式是 JSON 规格，由布局引擎渲染成海报。*

---

<div align="center">

<sub>截图只使用示例或公开数据。© 保留所有权利。描述文字可注明出处后引用，软件本身不可再分发。</sub>

</div>
