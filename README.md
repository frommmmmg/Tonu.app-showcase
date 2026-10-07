<div align="center">

# Tonu.app

English · [中文](README.zh.md) · [Español](README.es.md) · [Deutsch](README.de.md) · [Français](README.fr.md)

🌐 **[tonu.app](https://tonu.app)** · [GitHub @frommmmmg](https://github.com/frommmmmg)

</div>

> **This repository is a showcase, not a source release.** Tonu.app is closed-source, so there is no code here, only what it does, how it is built and what it looks like. To talk about it, get in touch through my [GitHub profile](https://github.com/frommmmmg).

**Drop in a photo, get a few dozen palette posters in the style of design-inspiration feeds, pick one, tune every detail, then save the PNG or share it.** Everything happens in the browser. Nothing is uploaded unless you choose to share.

Good designers keep a private stash of palettes. Tonu turns any reference image into one. It began as a poster generator and grew into a small colour toolbox: extract colours the way the eye sees them, name them honestly, tune the look, then carry the palette into the tools designers already use.

| | |
|---|---|
| **Website** | **[tonu.app](https://tonu.app)** |
| **Role** | One person: product, interface, colour science, front end and a tiny edge back end |
| **Status** | Live in production, 14 interface languages |
| **Privacy** | Photos stay in the browser. Saving never uploads; sharing uploads the poster for 24 hours to make a share page |
| **Stack** | Vanilla JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1 |

### What it does

**Extract and name**
- **Perceptual colour extraction.** The image is downsampled, converted to **OKLab**, clustered with **k-means++**, scored per cluster, and a weighted farthest-point pass picks colours that are both representative and distinct.
- **Honest colour naming, in your own language.** Each name comes from the nearest entry in public colour tables (ISCC-NBS, CSS, Tailwind, Material, xkcd and a large name library) by OKLab distance, never from machine translation. Traditional systems such as Japanese and Chinese traditional colours are built in, and a switch can snap swatches to the standard value so name and value match exactly.

**Design and tune**
- **A style engine, not a template.** A style is a JSON spec. **15 layout engines, over 30 presets and about 90 adjustable parameters**, including eight circular layouts, shadows, textures, finishes, frames and photo treatments.
- **Drag the colour block on the poster.** Move it freely or snap it to a side, or set the exact offset with the sliders. Dragging only starts after a few pixels, so a tap still copies a colour value.
- **Hover to preview.** Pointing at an option shows it on the current poster before you commit.
- **A floating preview on phones.** While you scroll through the settings, the poster stays in a small window you can drag, resize and pin. Pinch, mouse wheel or +/- zoom it like a loupe, up to 8x, so you can check a detail while you change a value.
- **Five interface skins, each in light and dark:** Proofing room, White wall, Paper journal, Multicolor and Terminal. **A dockable inspector** goes left, bottom or right and remembers its size. **14 interface languages.**

**Export and share**
- **Export that matches the screen.** Fonts are embedded so the PNG looks the same everywhere, the native share sheet is used on phones, and recent work is kept on the device.
- **Files for the tools designers use.** Adobe Swatch Exchange (`.ase`), Procreate (`.swatches`), GIMP (`.gpl`), W3C Design Tokens and Flutter, all written by hand in the browser. Copy a palette as HEX, RGB, HSL, CMYK, LAB, OKLCH or P3, or as CSS variables, SCSS, Tailwind, SwiftUI, Swift or Android XML.
- **Palette links and import.** A link like `tonu.app/#b2e1e7-4893b2` reopens a palette, and Tonu reads Coolors links or a plain list of HEX values.
- **An accessibility report.** A WCAG contrast matrix for every pair of colours, saved as a PNG card.
- **Fonts done properly.** 12 bundled open-licence fonts, plus your own files, URLs or installed fonts, with the licensing responsibility stated clearly.

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

<!--notes-->
## Engineering notes

- **No backend for the core.** Colour extraction, naming, rendering and every export run on the client. A small Worker with KV and D1 exists only for share pages, and the editor itself is served as static assets, so using it costs no Worker requests.
- **File formats written by hand.** The Adobe `.ase` binary and the Procreate `.swatches` archive (a zip around one JSON file, with the colour-profile hash checked against a real Procreate file) are produced with no libraries.
- **One render per frame.** Slider drags can fire faster than the screen refreshes, so the active poster is re-rendered at most once per frame, and the gallery, large view and floating preview all update from the same change.
- **Skins that cost nothing until used.** Each interface skin is a single scoped stylesheet fetched the first time it is picked. A returning visitor's skin loads during page load, with the page held back briefly so the default never flashes first. Posters are never restyled.
- **Lean internationalisation.** English is written into the HTML, other languages are single script files fetched on demand, links like `?lang=` work, and a checker script warns about missing keys.
- **Honest about its limits.** The interface translations are machine-made and not yet reviewed by native designers, and that is stated in the project's own notes.

**Other showcases:** [AffProof](https://github.com/frommmmmg/AffProof-showcase) · [AutoPin-CS](https://github.com/frommmmmg/AutoPin-CS-showcase) · [AffiliateScraper](https://github.com/frommmmmg/AffiliateScraper-showcase)

---

<div align="center">

<sub>Screenshots use sample or public data only. © All rights reserved. Descriptions may be quoted with attribution; the software itself is not for redistribution.</sub>

</div>
