# Guidegraph

**Créateur d'infographies institutionnelles pas à pas**  
Preuve de concept · Licence CC BY 4.0 · Auteur : Bertrand Formet · v1 · Mars 2026
Co-développé avec Claude Sonnet 4.6

---

## Présentation

Guidegraph est un outil autonome en ligne pour créer des infographies institutionnelles conformes aux bonnes pratiques graphiques. Il fonctionne entièrement dans le navigateur — sans installation, sans serveur, sans transmission de données.

L'outil guide l'utilisateur en **6 étapes** :

1. **Mon objectif** — Choisir le contexte de diffusion (impression, projection, réseaux sociaux, web, affichage, carrousel)
2. **Mon format** — Sélectionner parmi 13 formats standards (A4, 16:9, stories, carré, OG image, etc.)
3. **Ma mise en page** — Choisir l'organisation des blocs de contenu
4. **Ma charte graphique** — Définir les couleurs (règle 60-30-10) et les polices (jusqu'à 2)
5. **Mon contenu** — Remplir chaque bloc (texte, image, icône ou graphique) avec contrôle de l'alignement et de la taille de police
6. **Vérifier & Exporter** — Checklist automatique + exports PNG, SVG, HTML, impression PDF

---

## Démo

Ouvrir `guidegraph.html` dans n'importe quel navigateur moderne. Aucune dépendance externe.

---

## Fonctionnalités

### Éditeur de contenu
- **Texte** — Zone de saisie avec compteur de mots (limite recommandée : 40 mots), choix de la taille de police (8–48 pt)
- **Image** — Import depuis l'ordinateur (JPEG, PNG, GIF, WebP — max 5 Mo)
- **Icône** — Bibliothèque de 78 icônes CC0 organisées en 12 catégories thématiques (personnes, éducation, données, temps, institution, environnement, santé, social, mobilité, numérique, localisation, action)
- **Graphique** — Mini-éditeur intégré : barres, camembert, courbe
- **Alignement** — Contrôle horizontal (gauche / centre / droite) et vertical (haut / milieu / bas) par bloc

### Charte graphique
- Couleur principale → génération automatique de 4 palettes harmonieuses (complémentaire, triadique, analogue, neutre)
- Règle 60-30-10 expliquée et visualisée
- 8 polices système disponibles (sans installation) : Arial/Système, Georgia, Palatino, Trebuchet, Century Gothic, Franklin Gothic, Optima/Segoe UI, Courier New
- Sélection de 2 polices avec indication des rôles (titres / texte courant) et explication de l'association
- Import de police personnalisée (.ttf / .otf)
- Import de logo

### Exports
| Format | Description |
|--------|-------------|
| **PNG** | Image haute résolution (×2) |
| **SVG** | Vectoriel, redimensionnable à l'infini |
| **HTML** | Page web autonome avec l'infographie embarquée |
| **Prêt à imprimer** | Page HTML optimisée pour impression → Ctrl+P → Save as PDF |

### Sauvegarde
- Sauvegarde automatique dans le localStorage du navigateur
- Export / import du projet en JSON

---

## Architecture technique

Guidegraph est un **fichier HTML unique** (~220 ko) sans dépendances externes :

- Zéro framework JavaScript
- Zéro appel réseau (fonctionne hors ligne)
- Zéro tracking, zéro cookie
- Compatible avec tous les navigateurs modernes (Chrome, Firefox, Safari, Edge)

```
guidegraph.html
├── CSS intégré (design system, thème clair/sombre, responsive)
├── HTML (6 sections correspondant aux 6 étapes)
└── JavaScript intégré
    ├── Données : 13 formats × FMT_LAYOUTS (mises en page) × 78 icônes
    ├── Moteur de rendu SVG (aperçu en temps réel + exports)
    ├── Éditeurs : texte, image, icônes, graphiques (barres/camembert/courbe)
    └── Logique de navigation, sauvegarde, exports
```

---

## Référentiel

L'outil est fondé sur un référentiel de bonnes pratiques appuyé sur des sources expertes :

→ **[Lire le référentiel](referentiel.md)]**

Sources principales :
- Bertin, J. (1967). *Sémiologie graphique*
- Tufte, E. R. (1983). *The Visual Display of Quantitative Information*
- Service d'Information du Gouvernement — *Charte graphique de l'État* (2020-2021)
- Nielsen Norman Group — *Designing Effective Infographics* (2018)

---

## Formats supportés

| Famille | Formats |
|---------|---------|
| Portrait | Document A4, Affiche A3, Flyer A5 |
| Paysage | A4 paysage, 16:9 projection, 4:3 classique, 16:10, A3 paysage |
| Carré & réseaux | Carré 1:1, OG image 1200×628 |
| Carrousel | Carrousel LinkedIn, Carrousel Instagram |
| Vertical mobile | Stories 9:16 |

---

## Icônes

78 icônes CC0 (domaine public) en style line art (stroke, viewBox 24×24), organisées en 12 catégories :

> Personnes · Éducation · Données · Temps · Institution · Environnement · Santé · Social · Mobilité · Numérique · Localisation · Action

---

## Accessibilité

- HTML `lang="fr"`, viewport meta
- Lien skip-to-content visible au focus clavier
- `:focus-visible` sur tous les éléments interactifs
- `aria-pressed` et `role="radiogroup"` sur les cartes de sélection
- `aria-label` sur tous les inputs couleur et fichiers cachés
- Contrastes conformes WCAG AA (4,5:1 texte courant, 3:1 grands titres)

---

## Licence

**Creative Commons Attribution 4.0 International (CC BY 4.0)**

Vous êtes libre de copier, modifier, distribuer et utiliser cette œuvre, y compris à des fins commerciales, à condition de citer l'auteur.

> Auteur : **Bertrand Formet** · Mars 2026

[![CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

---

## Contribuer

Ce projet est une preuve de concept. Toute contribution (rapport de bug, suggestion, traduction) est bienvenue via les Issues GitHub.

---

*Guidegraph ne collecte aucune donnée. Toutes les informations restent sur votre appareil.*
