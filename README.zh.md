<div align="center">

# Tonu.app

[English](README.md) · 中文 · [Español](README.es.md) · [Deutsch](README.de.md) · [Français](README.fr.md)

🌐 **[tonu.app](https://tonu.app)** · [GitHub @frommmmmg](https://github.com/frommmmmg)

</div>

> **本仓库仅用于展示，不公开源码。** Tonu.app 不开源，所以这里没有代码，只介绍它做什么、怎么构建、长什么样。想聊聊它，请通过我的 [GitHub 主页](https://github.com/frommmmmg)联系我。

**丢进一张照片，得到几十张设计灵感流风格的色板海报，挑一张，调好每个细节，再保存 PNG 或分享。** 全部在浏览器里完成，除非你主动分享，否则不会上传任何东西。

好设计师都有一份私藏的色卡。Tonu 把任何一张参考图变成这样一份色卡。它最初是个海报生成器，后来长成了一个小小的色彩工具箱：按眼睛看到的方式取色，老老实实地命名，调出想要的样子，再把色卡带进设计师本来就在用的工具里。

| | |
|---|---|
| **网站** | **[tonu.app](https://tonu.app)** |
| **我的角色** | 一个人完成产品、界面、色彩算法、前端和一个很小的边缘后端 |
| **状态** | 已在生产环境运行，14 种界面语言 |
| **隐私** | 照片留在浏览器里。保存不会上传；分享时海报会上传 24 小时，用来生成分享页 |
| **技术栈** | 原生 JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1 |

### 它能做什么

**取色与命名**
- **按感知取色。** 图片先缩小，转到 **OKLab**，用 **k-means++** 聚类并给每个簇打分，再用加权最远点采样挑出既有代表性又彼此区分的颜色。
- **老实的颜色命名，而且按你的语言。** 每个名称都取自公开色名表（ISCC-NBS、CSS、Tailwind、Material、xkcd 和一个大型色名库）中 OKLab 距离最近的一项，不做机器翻译。日本传统色、中国传统色等体系已经内置，还有一个开关可以把色块吸附到标准色值，让名称和色值完全对应。

**设计与调整**
- **是样式引擎，不是模板。** 一个样式就是一份 JSON 规格。**15 种布局引擎、30 多个预设、约 90 个可调参数**，包括 8 种圆形布局、阴影、质感、光泽、边框和照片处理。
- **可以在海报上直接拖动色板。** 自由移动或吸附到某一侧，也可以用滑块精确设置偏移量。拖动要移动几个像素后才开始，所以轻点仍然是复制色值。
- **悬停即预览。** 鼠标指到某个选项上，就能在当前海报上看到效果，确定后再选。
- **手机上的悬浮预览窗。** 你往下滚动调参数时，海报会留在一个可拖动、可缩放、可固定的小窗里。双指捏合、鼠标滚轮或 +/- 都能像放大镜一样放大，最高 8 倍，改参数的同时可以盯着细节看。
- **5 套界面皮肤，各有亮色和暗色：** 校样室、白墙、纸刊、多彩、终端。**可停靠的操作台**可以放在左边、下边或右边，并记住大小。**14 种界面语言。**

**导出与分享**
- **导出与屏幕所见一致。** 字体会嵌进图片，PNG 在任何设备上都一样；手机上直接调起系统分享面板，最近的作品保存在本机。
- **直接给设计师工具用的文件。** Adobe Swatch Exchange（`.ase`）、Procreate（`.swatches`）、GIMP（`.gpl`）、W3C Design Tokens 和 Flutter，全部在浏览器里手写生成。色板可以复制成 HEX、RGB、HSL、CMYK、LAB、OKLCH 或 P3，也可以复制成 CSS 变量、SCSS、Tailwind、SwiftUI、Swift 或 Android XML。
- **色板链接与导入。** 形如 `tonu.app/#b2e1e7-4893b2` 的链接可以重新打开一份色板，Tonu 也能读取 Coolors 链接或一串 HEX 色值。
- **无障碍报告。** 每两种颜色之间的 WCAG 对比度矩阵，保存为一张 PNG 卡片。
- **字体处理规范。** 内置 12 款开源授权字体，也支持载入你自己的文件、网址或本机已安装字体，并明确写出授权责任。

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

<!--notes-->
## 工程笔记

- **核心功能没有后端。** 取色、命名、渲染和所有导出都在客户端完成。只有分享页用到一个带 KV 和 D1 的小 Worker，编辑器本身以静态资源提供，所以使用它不消耗 Worker 请求。
- **文件格式全部手写。** Adobe 的 `.ase` 二进制文件和 Procreate 的 `.swatches` 压缩包（一个 zip 包着一份 JSON，色彩配置文件的哈希已对照真实的 Procreate 文件验证）都不依赖任何库。
- **每帧只渲染一次。** 滑块拖动的触发频率可能比屏幕刷新更快，所以当前海报每帧最多重新渲染一次，画廊、大图和悬浮预览窗都从同一次修改更新。
- **皮肤不用就不花成本。** 每套界面皮肤都是一份限定作用域的样式表，第一次选中时才加载。回访用户的皮肤会在页面加载期间载入，并让页面稍作等待，避免先闪一下默认样式。海报永远不会被改样式。
- **精简的国际化。** 英文直接写在 HTML 里，其他语言是按需获取的单个脚本文件，支持 `?lang=` 这样的链接，还有一个检查脚本会提示缺失的键。
- **对局限很坦率。** 界面译文是机器翻译，还没有母语设计师审校，项目自己的笔记里也这样写明。

**其他项目展示:** [AffProof](https://github.com/frommmmmg/AffProof-showcase) · [AutoPin-CS](https://github.com/frommmmmg/AutoPin-CS-showcase) · [AffiliateScraper](https://github.com/frommmmmg/AffiliateScraper-showcase)

---

<div align="center">

<sub>截图只使用示例或公开数据。© 保留所有权利。描述文字可注明出处后引用，软件本身不可再分发。</sub>

</div>
