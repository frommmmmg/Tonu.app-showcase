<div align="center">

# Tonu.app

English · [中文](README.zh.md) · [Español](README.es.md) · [Deutsch](README.de.md) · [Français](README.fr.md)

</div>

> **This repository is a showcase, not a source release.** Tonu.app is a private project, so there is no code here, only what it does, how it is built and what it looks like. To talk about it, get in touch through my [GitHub profile](https://github.com/frommmmmg).

**Drop in a photo, get a dozen palette posters in the style of design-inspiration feeds, pick one, tweak it, save the PNG or share it.** Everything happens in the browser. Nothing is uploaded unless you choose to share.


**Highlights**

- **Perceptual colour extraction.** The image is downsampled, converted to **OKLab**, clustered with **k-means++**, scored per cluster, and a weighted farthest-point pass picks colours that are both representative and distinct.
- **Honest colour naming.** Names come from the nearest entry in public colour tables (ISCC-NBS, CSS, Tailwind, Material, xkcd) by OKLab distance, not machine translation.
- **A style engine, not a template.** A style is a JSON spec. **15 layout engines and 33 presets**, including eight circular layouts (wheel, fan, orbit, bubbles and more), plus optional shadows, textures, finishes, frames and photo treatments.
- **Export that matches the screen.** Fonts are embedded so the PNG looks the same everywhere, and the native share sheet is used on phones.
- **Font handling done properly.** 12 bundled open-licence fonts, plus your own files, URLs or installed fonts, with the licensing responsibility stated clearly.

**Stack:** Vanilla JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1 for shared posters

Live at **[tonu.app](https://tonu.app)**.

## Screenshots

![Three of the generated poster styles. The photo is a synthetic sample.](assets/tonu-posters.png)
*Three of the generated poster styles. The photo is a synthetic sample.*

![The editor: style gallery on the left, colour naming and export on the right. (The interface is currently in Chinese.)](assets/tonu-editor.png)
*The editor: style gallery on the left, colour naming and export on the right. (The interface is currently in Chinese.)*

## How it works

![Everything from colour extraction to export runs in the browser.](assets/tonu-extraction-pipeline.svg)
*Everything from colour extraction to export runs in the browser.*

![Styles are JSON specs that the layout engines turn into posters.](assets/tonu-style-engine.svg)
*Styles are JSON specs that the layout engines turn into posters.*

---

<div align="center">

<sub>Screenshots use sample or public data only. © All rights reserved. Descriptions may be quoted with attribution; the software itself is not for redistribution.</sub>

</div>
