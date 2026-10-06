<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · [Español](README.es.md) · Deutsch · [Français](README.fr.md)

</div>

> **Dieses Repository ist ein Schaufenster, keine Quellcode-Veröffentlichung.** Tonu.app ist ein privates Projekt, deshalb gibt es hier keinen Code, nur was es kann, wie es gebaut ist und wie es aussieht. Wenn du darüber sprechen möchtest, melde dich über mein [GitHub-Profil](https://github.com/frommmmmg).

**Foto hineinwerfen, ein Dutzend Farbpaletten-Poster im Stil von Inspirations-Feeds erhalten, eines auswählen, anpassen, als PNG speichern oder teilen.** Alles passiert im Browser. Es wird nichts hochgeladen, außer du entscheidest dich zum Teilen.


**Highlights**

- **Wahrnehmungsbasierte Farbextraktion.** Das Bild wird verkleinert, in **OKLab** umgerechnet, mit **k-means++** geclustert und jedes Cluster bewertet. Eine gewichtete Farthest-Point-Auswahl wählt Farben, die repräsentativ und zugleich unterscheidbar sind.
- **Ehrliche Farbnamen.** Namen stammen vom nächstgelegenen Eintrag in öffentlichen Farbtabellen (ISCC-NBS, CSS, Tailwind, Material, xkcd) nach OKLab-Abstand, nicht aus maschineller Übersetzung.
- **Eine Stil-Engine, keine Vorlage.** Ein Stil ist eine JSON-Spezifikation. **15 Layout-Engines und 33 Presets**, darunter acht kreisförmige Layouts (Farbrad, Fächer, Orbit, Blasen und mehr), dazu optionale Schatten, Texturen, Oberflächen, Rahmen und Foto-Behandlungen.
- **Export wie auf dem Bildschirm.** Schriften werden eingebettet, damit das PNG überall gleich aussieht, auf dem Handy öffnet sich das native Teilen-Menü.
- **Schriften sauber gehandhabt.** 12 mitgelieferte Open-Source-Schriften, dazu eigene Dateien, URLs oder installierte Schriften, mit klar benannter Lizenzverantwortung.

**Technik:** Vanilla JavaScript · OKLab · html-to-image · Cloudflare Workers + KV + D1 für geteilte Poster

Live unter **[tonu.app](https://tonu.app)**.

## Screenshots

![Drei der erzeugten Poster-Stile. Das Foto ist ein synthetisches Beispiel.](assets/tonu-posters.png)
*Drei der erzeugten Poster-Stile. Das Foto ist ein synthetisches Beispiel.*

![Der Editor: links die Stil-Galerie, rechts Farbnamen und Export. (Die Oberfläche ist derzeit auf Chinesisch.)](assets/tonu-editor.png)
*Der Editor: links die Stil-Galerie, rechts Farbnamen und Export. (Die Oberfläche ist derzeit auf Chinesisch.)*

## So funktioniert es

![Alles von der Farbextraktion bis zum Export läuft im Browser.](assets/tonu-extraction-pipeline.svg)
*Alles von der Farbextraktion bis zum Export läuft im Browser.*

![Stile sind JSON-Spezifikationen, die die Layout-Engines in Poster verwandeln.](assets/tonu-style-engine.svg)
*Stile sind JSON-Spezifikationen, die die Layout-Engines in Poster verwandeln.*

---

<div align="center">

<sub>Screenshots verwenden nur Beispiel- oder öffentliche Daten. © Alle Rechte vorbehalten. Beschreibungen dürfen mit Quellenangabe zitiert werden; die Software selbst darf nicht weitergegeben werden.</sub>

</div>
