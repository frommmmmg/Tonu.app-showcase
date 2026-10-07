<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · [Español](README.es.md) · [Deutsch](README.de.md) · Français

🌐 **[tonu.app](https://tonu.app)** · [GitHub @frommmmmg](https://github.com/frommmmmg)

✍️ Par **姜芊泽 (Jiang Qianze)** · compte officiel WeChat: **Pin海引航**

</div>

> **Ce dépôt est une vitrine, pas une publication de code source.** Tonu.app n'est pas open source : il n'y a donc pas de code ici, seulement ce qu'il fait, comment il est construit et à quoi il ressemble. Pour en discuter, contactez-moi via mon [profil GitHub](https://github.com/frommmmmg).

**Déposez une photo, obtenez des dizaines d'affiches de palette dans le style des flux d'inspiration, choisissez-en une, réglez chaque détail, puis enregistrez le PNG ou partagez-la.** Tout se passe dans le navigateur. Rien n'est envoyé, sauf si vous choisissez de partager.

Les bons designers gardent une réserve privée de palettes. Tonu transforme n'importe quelle image de référence en une palette. Né comme générateur d'affiches, il est devenu une petite boîte à outils de la couleur : extraire les couleurs comme l'œil les voit, les nommer honnêtement, régler le rendu, puis emporter la palette dans les outils que les designers utilisent déjà.

| | |
|---|---|
| **Site web** | **[tonu.app](https://tonu.app)** |
| **Mon rôle** | Une seule personne : produit, interface, science de la couleur, front end et un minuscule back end en périphérie |
| **Statut** | En production, 14 langues d'interface |
| **Confidentialité** | Les photos restent dans le navigateur. Enregistrer n'envoie jamais rien ; partager envoie l'affiche pour 24 heures afin de créer une page de partage |
| **Technologies** | JavaScript natif · OKLab · html-to-image · Cloudflare Workers + KV + D1 |

### Ce qu'il fait

**Extraire et nommer**
- **Extraction de couleurs perceptuelle.** L'image est réduite, convertie en **OKLab**, regroupée avec **k-means++**, chaque groupe est noté, puis un échantillonnage pondéré du point le plus éloigné choisit des couleurs à la fois représentatives et distinctes.
- **Des noms de couleurs honnêtes, dans votre langue.** Chaque nom vient de l'entrée la plus proche dans des tables publiques (ISCC-NBS, CSS, Tailwind, Material, xkcd et une grande bibliothèque de noms) selon la distance OKLab, sans traduction automatique. Des systèmes traditionnels, comme les couleurs traditionnelles japonaises et chinoises, sont intégrés, et un interrupteur aligne les nuances sur la valeur standard pour que nom et valeur coïncident exactement.

**Concevoir et régler**
- **Un moteur de styles, pas un gabarit.** Un style est une spécification JSON. **15 moteurs de mise en page, plus de 30 préréglages et environ 90 paramètres réglables**, dont huit mises en page circulaires, ombres, textures, finitions, cadres et traitements photo.
- **Faites glisser le bloc de couleurs sur l'affiche.** Déplacez-le librement ou accrochez-le à un côté, ou réglez le décalage exact avec les curseurs. Le glissement ne démarre qu'après quelques pixels : un simple toucher copie toujours la valeur de la couleur.
- **Aperçu au survol.** Pointer une option l'affiche sur l'affiche en cours avant que vous ne la choisissiez.
- **Un aperçu flottant sur mobile.** Pendant que vous faites défiler les réglages, l'affiche reste dans une petite fenêtre que vous pouvez déplacer, redimensionner et épingler. Pincement, molette ou +/- l'agrandissent comme une loupe jusqu'à 8x, pour vérifier un détail pendant que vous changez une valeur.
- **Cinq thèmes d'interface, chacun en clair et en sombre :** Salle d'épreuves, Mur blanc, Journal papier, Multicolore et Terminal. **Un panneau ancrable** à gauche, en bas ou à droite, qui mémorise sa taille. **14 langues d'interface.**

**Exporter et partager**
- **Un export fidèle à l'écran.** Les polices sont intégrées pour que le PNG soit identique partout, le menu de partage natif est utilisé sur mobile et les travaux récents restent sur l'appareil.
- **Des fichiers pour les outils des designers.** Adobe Swatch Exchange (`.ase`), Procreate (`.swatches`), GIMP (`.gpl`), W3C Design Tokens et Flutter, tous écrits à la main dans le navigateur. Copiez une palette en HEX, RGB, HSL, CMYK, LAB, OKLCH ou P3, ou en variables CSS, SCSS, Tailwind, SwiftUI, Swift ou Android XML.
- **Liens et import de palettes.** Un lien comme `tonu.app/#b2e1e7-4893b2` rouvre une palette, et Tonu lit les liens Coolors ou une simple liste de valeurs HEX.
- **Un rapport d'accessibilité.** Une matrice de contraste WCAG pour chaque paire de couleurs, enregistrée en carte PNG.
- **Gestion des polices soignée.** 12 polices sous licence libre incluses, plus vos propres fichiers, URL ou polices installées, avec la responsabilité de licence clairement indiquée.

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

<!--notes-->
## Notes d'ingénierie

- **Pas de back end pour l'essentiel.** L'extraction des couleurs, les noms, le rendu et tous les exports s'exécutent côté client. Un petit Worker avec KV et D1 n'existe que pour les pages de partage, et l'éditeur est servi en fichiers statiques : l'utiliser ne consomme aucune requête Worker.
- **Formats de fichiers écrits à la main.** Le binaire `.ase` d'Adobe et l'archive `.swatches` de Procreate (un zip autour d'un JSON, avec le hachage du profil colorimétrique vérifié contre un vrai fichier Procreate) sont produits sans bibliothèque.
- **Un rendu par image.** Faire glisser un curseur peut déclencher des événements plus vite que l'écran ne se rafraîchit : l'affiche active n'est donc recalculée qu'une fois par image au plus, et la galerie, la grande vue et l'aperçu flottant se mettent à jour à partir du même changement.
- **Des thèmes qui ne coûtent rien tant qu'on ne les utilise pas.** Chaque thème d'interface est une feuille de style isolée, chargée la première fois qu'on le choisit. Le thème d'un visiteur de retour est chargé pendant le chargement de la page, retenue un instant pour que le thème par défaut ne clignote pas d'abord. Les affiches ne sont jamais restylées.
- **Une internationalisation légère.** L'anglais est écrit dans le HTML, les autres langues sont des fichiers script récupérés à la demande, les liens comme `?lang=` fonctionnent, et un script de contrôle signale les clés manquantes.
- **Honnête sur ses limites.** Les traductions de l'interface sont automatiques et pas encore relues par des designers natifs, et les notes du projet le disent.

<!--author-->
## À propos de l'auteur

<img src="assets/wechat-qr.png" alt="QR code du compte officiel WeChat Pin海引航" width="200" align="right">

**姜芊泽 (Jiang Qianze)** est un pseudonyme. Je suis un développeur indépendant qui crée des outils, des données et de l'automatisation pour les marques, marchands et créateurs qui visent l'international. Chaque projet de ces vitrines a été conçu, construit et exploité par moi seul, de l'idée du produit jusqu'aux serveurs et à la documentation.

J'écris sur ce travail sur mon compte officiel WeChat, **Pin海引航** (en chinois). Scannez le code pour le suivre, ou retrouvez-moi sur [GitHub](https://github.com/frommmmmg).

<br clear="right">
<!--/author-->

**Autres vitrines:** [AffProof](https://github.com/frommmmmg/AffProof-showcase) · [AutoPin-CS](https://github.com/frommmmmg/AutoPin-CS-showcase) · [AffiliateScraper](https://github.com/frommmmmg/AffiliateScraper-showcase)

---

<div align="center">

<sub>Les captures n'utilisent que des données d'exemple ou publiques. © Tous droits réservés. Les descriptions peuvent être citées avec attribution ; le logiciel lui-même ne peut pas être redistribué.</sub>

</div>
