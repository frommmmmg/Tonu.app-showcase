<div align="center">

# Tonu.app

[English](README.md) · [中文](README.zh.md) · [Español](README.es.md) · [Deutsch](README.de.md) · Français

</div>

> **Ce dépôt est une vitrine, pas une publication de code source.** Tonu.app est un projet privé : il n'y a donc pas de code ici, seulement ce qu'il fait, comment il est construit et à quoi il ressemble. Pour en discuter, contactez-moi via mon [profil GitHub](https://github.com/frommmmmg).

**Déposez une photo, obtenez une douzaine d'affiches de palette dans le style des flux d'inspiration, choisissez-en une, retouchez-la, enregistrez le PNG ou partagez-la.** Tout se passe dans le navigateur. Rien n'est envoyé, sauf si vous choisissez de partager.


**Points forts**

- **Extraction de couleurs perceptuelle.** L'image est réduite, convertie en **OKLab**, regroupée avec **k-means++**, chaque groupe est noté, puis un échantillonnage pondéré du point le plus éloigné choisit des couleurs à la fois représentatives et distinctes.
- **Des noms de couleurs honnêtes.** Les noms viennent de l'entrée la plus proche dans des tables publiques (ISCC-NBS, CSS, Tailwind, Material, xkcd) selon la distance OKLab, sans traduction automatique.
- **Un moteur de styles, pas un gabarit.** Un style est une spécification JSON. **15 moteurs de mise en page et 33 préréglages**, dont huit mises en page circulaires (roue, éventail, orbite, bulles et plus), avec ombres, textures, finitions, cadres et traitements photo en option.
- **Un export fidèle à l'écran.** Les polices sont intégrées pour que le PNG soit identique partout, et le menu de partage natif est utilisé sur mobile.
- **Gestion des polices soignée.** 12 polices sous licence libre incluses, plus vos propres fichiers, URL ou polices installées, avec la responsabilité de licence clairement indiquée.

**Technologies :** JavaScript natif · OKLab · html-to-image · Cloudflare Workers + KV + D1 pour les affiches partagées

En ligne sur **[tonu.app](https://tonu.app)**.

## Captures d'écran

![Trois des styles d'affiche générés. La photo est un échantillon synthétique.](assets/tonu-posters.png)
*Trois des styles d'affiche générés. La photo est un échantillon synthétique.*

![L'éditeur : galerie de styles à gauche, noms de couleurs et export à droite. (L'interface est actuellement en chinois.)](assets/tonu-editor.png)
*L'éditeur : galerie de styles à gauche, noms de couleurs et export à droite. (L'interface est actuellement en chinois.)*

## Comment ça marche

![Tout, de l'extraction des couleurs à l'export, s'exécute dans le navigateur.](assets/tonu-extraction-pipeline.svg)
*Tout, de l'extraction des couleurs à l'export, s'exécute dans le navigateur.*

![Les styles sont des spécifications JSON que les moteurs de mise en page transforment en affiches.](assets/tonu-style-engine.svg)
*Les styles sont des spécifications JSON que les moteurs de mise en page transforment en affiches.*

---

<div align="center">

<sub>Les captures n'utilisent que des données d'exemple ou publiques. © Tous droits réservés. Les descriptions peuvent être citées avec attribution ; le logiciel lui-même ne peut pas être redistribué.</sub>

</div>
