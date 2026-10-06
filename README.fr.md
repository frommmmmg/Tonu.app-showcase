<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · [Español](README.es.md) · [Deutsch](README.de.md) · Français

</div>

> **Ce dépôt est une vitrine, pas une publication de code source.** Tonu.app est un projet privé : il n'y a donc pas de code ici, seulement ce qu'il fait, comment il est construit et à quoi il ressemble. Pour en discuter, contactez-moi via mon [profil GitHub](https://github.com/frommmmmg).

**Déposez une photo, obtenez des dizaines d'affiches de palette dans le style des flux d'inspiration, choisissez-en une, réglez chaque détail, puis enregistrez le PNG ou partagez-la.** Tout se passe dans le navigateur. Rien n'est envoyé, sauf si vous choisissez de partager.

**Points forts**

- **Extraction de couleurs perceptuelle.** L'image est réduite, convertie en **OKLab**, regroupée avec **k-means++**, chaque groupe est noté, puis un échantillonnage pondéré du point le plus éloigné choisit des couleurs à la fois représentatives et distinctes.
- **Des noms de couleurs honnêtes, dans votre langue.** Les noms viennent de l'entrée la plus proche dans des tables publiques (ISCC-NBS, CSS, Tailwind, Material, xkcd) selon la distance OKLab, sans traduction automatique. Des systèmes traditionnels, comme les couleurs traditionnelles japonaises et chinoises, sont intégrés.
- **Un moteur de styles, pas un gabarit.** Un style est une spécification JSON. **15 moteurs de mise en page, plus de 30 préréglages et environ 90 paramètres réglables**, dont huit mises en page circulaires, ombres, textures, finitions, cadres et traitements photo.
- **Faites glisser le bloc de couleurs sur l'affiche.** Déplacez-le librement ou accrochez-le à un côté, ou réglez le décalage exact avec les curseurs. Le glissement ne démarre qu'après quelques pixels : un simple toucher copie toujours la valeur de la couleur.
- **Un aperçu flottant sur mobile.** Pendant que vous faites défiler les réglages, l'affiche reste dans une petite fenêtre que vous pouvez déplacer, redimensionner et épingler. Pincement, molette ou +/- l'agrandissent comme une loupe jusqu'à 8x, pour vérifier un détail pendant que vous changez une valeur.
- **Aperçu au survol.** Pointer une option l'affiche sur l'affiche en cours avant que vous ne la choisissiez.
- **Cinq thèmes d'interface, chacun en clair et en sombre :** Salle d'épreuves, Mur blanc, Journal papier, Multicolore et Terminal. Ils se chargent à la demande et ne changent que l'interface, jamais les affiches.
- **Un panneau ancrable.** Placez-le à gauche, en bas ou à droite, redimensionnez-le en tirant sur le bord ; le choix est mémorisé sur l'appareil.
- **14 langues d'interface.**
- **Un export fidèle à l'écran.** Les polices sont intégrées pour que le PNG soit identique partout, le menu de partage natif est utilisé sur mobile et les travaux récents restent sur l'appareil.
- **Gestion des polices soignée.** 12 polices sous licence libre incluses, plus vos propres fichiers, URL ou polices installées, avec la responsabilité de licence clairement indiquée.

**Technologies :** JavaScript natif · OKLab · html-to-image · Cloudflare Workers + KV + D1 pour les affiches partagées

En ligne sur **[tonu.app](https://tonu.app)**. La photo d'exemple des captures est d'Andrés Beltrán Espinosa sur Unsplash.

## Captures d'écran

![La galerie : une photo, de nombreux styles d'affiche.](assets/tonu-gallery.jpg)
*La galerie : une photo, de nombreux styles d'affiche.*

![La grande vue. Le panneau de réglages reste actif à côté.](assets/tonu-focus.jpg)
*La grande vue. Le panneau de réglages reste actif à côté.*

<table><tr><td align="center" width="33%"><img src="assets/tonu-skin-default.jpg" alt="Salle d'épreuves"><br><sub>Salle d'épreuves</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-white.jpg" alt="Mur blanc"><br><sub>Mur blanc</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-paper.jpg" alt="Journal papier"><br><sub>Journal papier</sub></td></tr><tr><td align="center" width="33%"><img src="assets/tonu-skin-multicolor.jpg" alt="Multicolore"><br><sub>Multicolore</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-terminal.jpg" alt="Terminal"><br><sub>Terminal</sub></td><td align="center" width="33%"><img src="assets/tonu-skin-multicolor-dark.jpg" alt="Multicolore, sombre"><br><sub>Multicolore, sombre</sub></td></tr></table>

*Cinq thèmes d'interface, chacun avec un mode clair et un mode sombre.*

![Faites glisser le bloc de couleurs n'importe où sur l'affiche.](assets/tonu-drag.jpg)
*Faites glisser le bloc de couleurs n'importe où sur l'affiche.*

![Sur mobile : la galerie, l'aperçu flottant au-dessus des réglages et l'aperçu agrandi à 338 %.](assets/tonu-mobile.jpg)
*Sur mobile : la galerie, l'aperçu flottant au-dessus des réglages et l'aperçu agrandi à 338 %.*

<table><tr><td align="center" width="50%"><img src="assets/tonu-dock-bottom.jpg" alt="En bas"><br><sub>En bas</sub></td><td align="center" width="50%"><img src="assets/tonu-dock-left.jpg" alt="À gauche"><br><sub>À gauche</sub></td></tr></table>

*Le panneau ancré en bas et à gauche.*

![Le même écran dans quatre des 14 langues d'interface. Les noms de couleurs suivent la langue, par exemple les couleurs traditionnelles japonaises.](assets/tonu-languages.jpg)
*Le même écran dans quatre des 14 langues d'interface. Les noms de couleurs suivent la langue, par exemple les couleurs traditionnelles japonaises.*

## Comment ça marche

![Un changement met à jour ensemble la galerie, la grande vue et l'aperçu flottant.](assets/tonu-live-sync.svg)
*Un changement met à jour ensemble la galerie, la grande vue et l'aperçu flottant.*

![Tout, de l'extraction des couleurs à l'export, s'exécute dans le navigateur.](assets/tonu-extraction-pipeline.svg)
*Tout, de l'extraction des couleurs à l'export, s'exécute dans le navigateur.*

![Les styles sont des spécifications JSON que les moteurs de mise en page transforment en affiches.](assets/tonu-style-engine.svg)
*Les styles sont des spécifications JSON que les moteurs de mise en page transforment en affiches.*

---

<div align="center">

<sub>Les captures n'utilisent que des données d'exemple ou publiques. © Tous droits réservés. Les descriptions peuvent être citées avec attribution ; le logiciel lui-même ne peut pas être redistribué.</sub>

</div>
