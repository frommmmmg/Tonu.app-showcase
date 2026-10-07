<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · [Español](README.es.md) · Deutsch · [Français](README.fr.md)

🌐 **[tonu.app](https://tonu.app)** · [GitHub @frommmmmg](https://github.com/frommmmmg)

</div>

> **Dieses Repository ist ein Schaufenster, keine Quellcode-Veröffentlichung.** Tonu.app ist nicht quelloffen, deshalb gibt es hier keinen Code, nur was es kann, wie es gebaut ist und wie es aussieht. Wenn du darüber sprechen möchtest, melde dich über mein [GitHub-Profil](https://github.com/frommmmmg).

**Foto hineinwerfen, Dutzende Farbpaletten-Poster im Stil von Inspirations-Feeds erhalten, eines auswählen, jedes Detail anpassen und als PNG speichern oder teilen.** Alles passiert im Browser. Es wird nichts hochgeladen, außer du entscheidest dich zum Teilen.

Gute Designer führen eine private Sammlung von Paletten. Tonu macht aus jedem Referenzbild eine. Es begann als Poster-Generator und wuchs zu einem kleinen Farb-Werkzeugkasten: Farben so extrahieren, wie das Auge sie sieht, sie ehrlich benennen, den Look anpassen und die Palette in die Werkzeuge mitnehmen, die Designer ohnehin nutzen.

| | |
|---|---|
| **Website** | **[tonu.app](https://tonu.app)** |
| **Meine Rolle** | Eine Person: Produkt, Oberfläche, Farbwissenschaft, Frontend und ein winziges Edge-Backend |
| **Status** | Live im Produktivbetrieb, 14 Oberflächensprachen |
| **Datenschutz** | Fotos bleiben im Browser. Speichern lädt nie etwas hoch; Teilen lädt das Poster für 24 Stunden hoch, um eine Teilen-Seite zu erzeugen |
| **Technik** | Vanilla JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1 |

### Was es kann

**Extrahieren und benennen**
- **Wahrnehmungsbasierte Farbextraktion.** Das Bild wird verkleinert, in **OKLab** umgerechnet, mit **k-means++** geclustert und jedes Cluster bewertet. Eine gewichtete Farthest-Point-Auswahl wählt Farben, die repräsentativ und zugleich unterscheidbar sind.
- **Ehrliche Farbnamen, in deiner Sprache.** Jeder Name stammt vom nächstgelegenen Eintrag in öffentlichen Farbtabellen (ISCC-NBS, CSS, Tailwind, Material, xkcd und eine große Namensbibliothek) nach OKLab-Abstand, nicht aus maschineller Übersetzung. Traditionelle Systeme wie die traditionellen Farben Japans und Chinas sind eingebaut, und ein Schalter rastet Farbfelder auf den Standardwert ein, damit Name und Wert exakt zusammenpassen.

**Gestalten und anpassen**
- **Eine Stil-Engine, keine Vorlage.** Ein Stil ist eine JSON-Spezifikation. **15 Layout-Engines, über 30 Presets und rund 90 einstellbare Parameter**, darunter acht kreisförmige Layouts, Schatten, Texturen, Oberflächen, Rahmen und Foto-Behandlungen.
- **Farbblock direkt auf dem Poster ziehen.** Frei verschieben oder an einer Seite einrasten lassen, oder den genauen Versatz per Schieberegler setzen. Das Ziehen beginnt erst nach ein paar Pixeln, ein Tippen kopiert also weiterhin den Farbwert.
- **Hover-Vorschau.** Zeigst du auf eine Option, siehst du sie am aktuellen Poster, bevor du dich entscheidest.
- **Schwebende Vorschau auf dem Handy.** Beim Scrollen durch die Einstellungen bleibt das Poster in einem kleinen Fenster, das du verschieben, in der Größe ändern und anheften kannst. Mit Pinch, Mausrad oder +/- zoomst du wie mit einer Lupe bis 8x und prüfst ein Detail, während du einen Wert änderst.
- **Fünf Oberflächen-Skins, jeweils hell und dunkel:** Korrekturraum, Weiße Wand, Papierjournal, Multicolor und Terminal. **Ein andockbares Bedienfeld** links, unten oder rechts, das seine Größe merkt. **14 Oberflächensprachen.**

**Exportieren und teilen**
- **Export wie auf dem Bildschirm.** Schriften werden eingebettet, damit das PNG überall gleich aussieht, auf dem Handy öffnet sich das native Teilen-Menü, und die letzten Arbeiten bleiben auf dem Gerät.
- **Dateien für die Werkzeuge der Designer.** Adobe Swatch Exchange (`.ase`), Procreate (`.swatches`), GIMP (`.gpl`), W3C Design Tokens und Flutter, alle im Browser von Hand geschrieben. Eine Palette lässt sich als HEX, RGB, HSL, CMYK, LAB, OKLCH oder P3 kopieren, oder als CSS-Variablen, SCSS, Tailwind, SwiftUI, Swift oder Android XML.
- **Palettenlinks und Import.** Ein Link wie `tonu.app/#b2e1e7-4893b2` öffnet eine Palette wieder, und Tonu liest Coolors-Links oder eine einfache Liste von HEX-Werten.
- **Barrierefreiheits-Bericht.** Eine WCAG-Kontrastmatrix für jedes Farbpaar, gespeichert als PNG-Karte.
- **Schriften sauber gehandhabt.** 12 mitgelieferte Open-Source-Schriften, dazu eigene Dateien, URLs oder installierte Schriften, mit klar benannter Lizenzverantwortung.

## Screenshots

![Die Galerie: ein Foto, viele Poster-Stile.](assets/tonu-gallery.jpg)
*Die Galerie: ein Foto, viele Poster-Stile.*

![Die große Ansicht. Das Einstellungsfeld bleibt daneben aktiv.](assets/tonu-focus.jpg)
*Die große Ansicht. Das Einstellungsfeld bleibt daneben aktiv.*

<table><tr><td align="center" width="33%"><img src="assets/tonu-skin-default.jpg" alt="Korrekturraum"><br><sub>Korrekturraum</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-white.jpg" alt="Weiße Wand"><br><sub>Weiße Wand</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-paper.jpg" alt="Papierjournal"><br><sub>Papierjournal</sub></td></tr><tr><td align="center" width="33%"><img src="assets/tonu-skin-multicolor.jpg" alt="Multicolor"><br><sub>Multicolor</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-terminal.jpg" alt="Terminal"><br><sub>Terminal</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-multicolor-dark.jpg" alt="Multicolor, dunkel"><br><sub>Multicolor, dunkel</sub></td></tr></table>

*Fünf Oberflächen-Skins, jeweils mit hellem und dunklem Modus.*

![Den Farbblock an eine beliebige Stelle des Posters ziehen.](assets/tonu-drag.jpg)
*Den Farbblock an eine beliebige Stelle des Posters ziehen.*

![Auf dem Handy: die Galerie, die schwebende Vorschau über den Einstellungen und die auf 338 % vergrößerte Vorschau.](assets/tonu-mobile.jpg)
*Auf dem Handy: die Galerie, die schwebende Vorschau über den Einstellungen und die auf 338 % vergrößerte Vorschau.*

<table><tr><td align="center" width="50%"><img src="assets/tonu-dock-bottom.jpg" alt="Unten"><br><sub>Unten</sub></td><td align="center" width="50%"><img src="assets/tonu-dock-left.jpg" alt="Links"><br><sub>Links</sub></td></tr></table>

*Das Bedienfeld unten und links angedockt.*

![Derselbe Bildschirm in vier der 14 Oberflächensprachen. Farbnamen folgen der Sprache, zum Beispiel die traditionellen Farben Japans.](assets/tonu-languages.jpg)
*Derselbe Bildschirm in vier der 14 Oberflächensprachen. Farbnamen folgen der Sprache, zum Beispiel die traditionellen Farben Japans.*

## So funktioniert es

![Eine Änderung aktualisiert Galerie, große Ansicht und schwebende Vorschau gleichzeitig.](assets/tonu-live-sync.svg)
*Eine Änderung aktualisiert Galerie, große Ansicht und schwebende Vorschau gleichzeitig.*

![Alles von der Farbextraktion bis zum Export läuft im Browser.](assets/tonu-extraction-pipeline.svg)
*Alles von der Farbextraktion bis zum Export läuft im Browser.*

![Stile sind JSON-Spezifikationen, die die Layout-Engines in Poster verwandeln.](assets/tonu-style-engine.svg)
*Stile sind JSON-Spezifikationen, die die Layout-Engines in Poster verwandeln.*

<!--notes-->
## Technische Notizen

- **Kein Backend für den Kern.** Farbextraktion, Benennung, Rendering und jeder Export laufen im Client. Ein kleiner Worker mit KV und D1 existiert nur für Teilen-Seiten, und der Editor selbst wird als statische Dateien ausgeliefert, seine Nutzung verursacht also keine Worker-Anfragen.
- **Dateiformate von Hand geschrieben.** Die Adobe-`.ase`-Binärdatei und das Procreate-`.swatches`-Archiv (ein Zip um eine JSON-Datei, mit gegen eine echte Procreate-Datei geprüftem Farbprofil-Hash) entstehen ohne Bibliotheken.
- **Ein Rendering pro Frame.** Schieberegler-Ziehen kann schneller Ereignisse feuern, als der Bildschirm aktualisiert, daher wird das aktive Poster höchstens einmal pro Frame neu gerendert, und Galerie, große Ansicht und schwebende Vorschau aktualisieren sich aus derselben Änderung.
- **Skins, die nichts kosten, bis man sie nutzt.** Jeder Oberflächen-Skin ist ein einzelnes, gekapseltes Stylesheet, das beim ersten Auswählen geladen wird. Der Skin eines wiederkehrenden Besuchers wird beim Seitenaufbau geladen, die Seite wird kurz zurückgehalten, damit nicht zuerst der Standard aufblitzt. Poster werden nie umgestaltet.
- **Schlanke Internationalisierung.** Englisch steht im HTML, andere Sprachen sind einzelne Skriptdateien, die bei Bedarf geladen werden, Links wie `?lang=` funktionieren, und ein Prüfskript warnt vor fehlenden Schlüsseln.
- **Ehrlich über die Grenzen.** Die Oberflächenübersetzungen sind maschinell und noch nicht von muttersprachlichen Designern geprüft, und das steht auch in den eigenen Projektnotizen.

**Weitere Projekte:** [AffProof](https://github.com/frommmmmg/AffProof-showcase) · [AutoPin-CS](https://github.com/frommmmmg/AutoPin-CS-showcase) · [AffiliateScraper](https://github.com/frommmmmg/AffiliateScraper-showcase)

---

<div align="center">

<sub>Screenshots verwenden nur Beispiel- oder öffentliche Daten. © Alle Rechte vorbehalten. Beschreibungen dürfen mit Quellenangabe zitiert werden; die Software selbst darf nicht weitergegeben werden.</sub>

</div>
