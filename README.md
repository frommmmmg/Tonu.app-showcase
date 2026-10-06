<div align="center">

# Tonu.app

English · [中文](README.zh.md) · [Español](README.es.md) · [Deutsch](README.de.md) · [Français](README.fr.md)

</div>

> **This repository is a showcase, not a source release.** Tonu.app is a private project, so there is no code here, only what it does, how it is built and what it looks like. To talk about it, get in touch through my [GitHub profile](https://github.com/frommmmmg).

**Drop in a photo, get a few dozen palette posters in the style of design-inspiration feeds, pick one, tune every detail, then save the PNG or share it.** Everything happens in the browser. Nothing is uploaded unless you choose to share.

**Highlights**

- **Perceptual colour extraction.** The image is downsampled, converted to **OKLab**, clustered with **k-means++**, scored per cluster, and a weighted farthest-point pass picks colours that are both representative and distinct.
- **Honest colour naming, in your own language.** Names come from the nearest entry in public colour tables (ISCC-NBS, CSS, Tailwind, Material, xkcd) by OKLab distance, never from machine translation. Traditional systems such as Japanese and Chinese traditional colours are built in.
- **A style engine, not a template.** A style is a JSON spec. **15 layout engines, over 30 presets and about 90 adjustable parameters**, including eight circular layouts, shadows, textures, finishes, frames and photo treatments.
- **Drag the colour block on the poster.** Move it freely or snap it to a side, or set the exact offset with the sliders. Dragging only starts after a few pixels, so a tap still copies a colour value.
- **A floating preview on phones.** While you scroll through the settings, the poster stays in a small window you can drag, resize and pin. Pinch, mouse wheel or +/- zoom it like a loupe, up to 8x, so you can check a detail while you change a value.
- **Hover to preview.** Pointing at an option shows it on the current poster before you commit to it.
- **Five interface skins, each in light and dark:** Proofing room, White wall, Paper journal, Multicolor and Terminal. They load on demand and restyle only the interface, never the posters.
- **A dockable inspector.** Put the settings on the left, bottom or right, resize them by dragging the edge, and the choice is remembered on the device.
- **14 interface languages.**
- **Export that matches the screen.** Fonts are embedded so the PNG looks the same everywhere, the native share sheet is used on phones, and recent work is kept on the device.
- **Fonts done properly.** 12 bundled open-licence fonts, plus your own files, URLs or installed fonts, with the licensing responsibility stated clearly.

**Stack:** Vanilla JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1 for shared posters

Live at **[tonu.app](https://tonu.app)**. The sample photo in the screenshots is by Andrés Beltrán Espinosa on Unsplash.

## Screenshots

![The gallery: one photo, many poster styles.](assets/tonu-gallery.jpg)
*The gallery: one photo, many poster styles.*

![The large view. The settings panel stays live beside it.](assets/tonu-focus.jpg)
*The large view. The settings panel stays live beside it.*

<table><tr><td align="center" width="33%"><img src="assets/tonu-skin-default.jpg" alt="Proofing room"><br><sub>Proofing room</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-white.jpg" alt="White wall"><br><sub>White wall</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-paper.jpg" alt="Paper journal"><br><sub>Paper journal</sub></td></tr><tr><td align="center" width="33%"><img src="assets/tonu-skin-multicolor.jpg" alt="Multicolor"><br><sub>Multicolor</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-terminal.jpg" alt="Terminal"><br><sub>Terminal</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-multicolor-dark.jpg" alt="Multicolor, dark"><br><sub>Multicolor, dark</sub></td></tr></table>

*Five interface skins, each with a light and a dark mode.*

![Drag the colour block anywhere on the poster.](assets/tonu-drag.jpg)
*Drag the colour block anywhere on the poster.*

![On a phone: the gallery, the floating preview above the settings, and the preview zoomed to 338%.](assets/tonu-mobile.jpg)
*On a phone: the gallery, the floating preview above the settings, and the preview zoomed to 338%.*

<table><tr><td align="center" width="50%"><img src="assets/tonu-dock-bottom.jpg" alt="Bottom"><br><sub>Bottom</sub></td><td align="center" width="50%"><img src="assets/tonu-dock-left.jpg" alt="Left"><br><sub>Left</sub></td></tr></table>

*The inspector docked at the bottom and at the left.*

![The same screen in four of the 14 interface languages. Colour names follow the language, for example Japanese traditional colours.](assets/tonu-languages.jpg)
*The same screen in four of the 14 interface languages. Colour names follow the language, for example Japanese traditional colours.*

## How it works

![One change updates the gallery, the large view and the floating preview together.](assets/tonu-live-sync.svg)
*One change updates the gallery, the large view and the floating preview together.*

![Everything from colour extraction to export runs in the browser.](assets/tonu-extraction-pipeline.svg)
*Everything from colour extraction to export runs in the browser.*

![Styles are JSON specs that the layout engines turn into posters.](assets/tonu-style-engine.svg)
*Styles are JSON specs that the layout engines turn into posters.*

---

<div align="center">

<sub>Screenshots use sample or public data only. © All rights reserved. Descriptions may be quoted with attribution; the software itself is not for redistribution.</sub>

</div>
