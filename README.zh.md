<div align="center">

# Tonu.app

[English](README.md) · 中文 · [Español](README.es.md) · [Deutsch](README.de.md) · [Français](README.fr.md)

</div>

> **本仓库仅用于展示，不公开源码。** Tonu.app 是私有项目，所以这里没有代码，只介绍它做什么、怎么构建、长什么样。想聊聊它，请通过我的 [GitHub 主页](https://github.com/frommmmmg)联系我。

**丢进一张照片，得到十几张设计灵感流风格的色板海报，挑一张微调，保存 PNG 或直接分享。** 全部在浏览器里完成，除非你主动分享，否则不会上传任何东西。


**亮点**

- **按感知取色。** 图片先缩小，转到 **OKLab**，用 **k-means++** 聚类并给每个簇打分，再用加权最远点采样挑出既有代表性又彼此区分的颜色。
- **老实的颜色命名。** 名称取自公开色名表（ISCC-NBS、CSS、Tailwind、Material、xkcd）中 OKLab 距离最近的一项，不做机器翻译。
- **是样式引擎，不是模板。** 一个样式就是一份 JSON 规格。**15 种布局引擎、33 个预设**，其中有 8 种圆形布局（色盘、色扇、环绕、气泡等），还有可选的阴影、质感、光泽、边框和照片处理。
- **导出与屏幕所见一致。** 字体会嵌进图片，PNG 在任何设备上都一样；手机上直接调起系统分享面板。
- **字体处理规范。** 内置 12 款开源授权字体，也支持载入你自己的文件、网址或本机已安装字体，并明确写出授权责任。

**技术栈：** 原生 JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1（用于分享的海报）

线上地址：**[tonu.app](https://tonu.app)**

## 截图

![生成的海报样式中的三种。照片是合成的示例图。](assets/tonu-posters.png)
*生成的海报样式中的三种。照片是合成的示例图。*

![编辑器：左侧是样式画廊，右侧是色名与导出设置。](assets/tonu-editor.png)
*编辑器：左侧是样式画廊，右侧是色名与导出设置。*

## 工作原理

![从取色到导出，全部在浏览器里运行。](assets/tonu-extraction-pipeline.svg)
*从取色到导出，全部在浏览器里运行。*

![样式是 JSON 规格，由布局引擎渲染成海报。](assets/tonu-style-engine.svg)
*样式是 JSON 规格，由布局引擎渲染成海报。*

---

<div align="center">

<sub>截图只使用示例或公开数据。© 保留所有权利。描述文字可注明出处后引用，软件本身不可再分发。</sub>

</div>
