# 🎵 VIQ – Release Landing Page Generator

Outil interne pour générer des landing pages de sortie musicale, prêtes à être uploadées sur GitHub Pages en quelques secondes.

---

## Ce que ça fait

Tu remplis un formulaire → tu télécharges un ZIP → tu uploades sur GitHub Pages → ta page est live sur `go.viqmusic.net/[slug]`.

---

## Fonctionnalités

### Générateur
- **Auto-remplissage des liens** via l'API Odesli — colle un lien Spotify (ou autre) et tous les liens plateformes se remplissent automatiquement
- **12 plateformes supportées** : Spotify, Apple Music, YouTube, YouTube Music, Deezer, SoundCloud, Amazon Music, Tidal, Bandcamp, Pandora, Anghami, Store
- **Optimisation de la cover** — redimensionnement automatique en 1000×1000px JPEG à l'import, avec prévisualisation
- **Extraction de couleur dominante** — la couleur primaire de la cover est extraite automatiquement et injectée dans la landing et l'OG
- **Génération OG image** — une image 1200×630px est générée automatiquement pour Discord, Facebook, Twitter/X
- **Aperçu live** — la landing et l'OG se mettent à jour en temps réel sans avoir à regénérer
- **Slug auto** — généré depuis le titre de la chanson, personnalisable
- **Validation des URLs** — indicateur visuel vert/rouge sur chaque lien
- **Nettoyage des URLs** — suppression automatique des paramètres de tracking (utm, si…) au blur
- **Duplication de config** — clone une page en gardant artiste + réseaux sociaux, vide titre + liens
- **Export ZIP** — dossier `[slug]/` contenant `index.html`, `cover.jpg` et `og.jpg`
- **Drag & drop** sur la zone cover

### Landing page générée
- **Particules animées** flottant vers le haut, tintées dans la couleur de la cover
- **Animation d'entrée** sur la cover (zoom + fade)
- **Hover zoom** sur la cover
- **Layout responsive** — optimisé mobile et desktop
- **Fond dynamique** — cover floue en background avec overlay sombre
- **Bouton Share** — natif sur mobile (Web Share API), copie le lien en fallback
- **Réseaux sociaux** — Instagram, TikTok, Facebook, site web
- **Favicon** = cover de la chanson
- **Balises OG complètes** — og:image, og:title, og:description, twitter:card, canonical

### OG Image
- Cover en plein bord droit, fondue sur la gauche
- Fond = cover floue sur toute l'image
- Nom de l'artiste en grand (serif), titre en light
- Ligne décorative en couleur primaire
- Type de release en lettres espacées
- Barre de couleur en dégradé en bas
- Domaine `viqmusic.net` discret en bas à gauche

---

## Structure du ZIP généré

```
[slug]/
├── index.html   ← landing page complète
├── cover.jpg    ← pochette optimisée 1000×1000
└── og.jpg       ← image OG 1200×630 pour les réseaux
```

---

## Déploiement

1. Générer le ZIP depuis le générateur
2. Décompresser et uploader le dossier `[slug]/` dans le repo GitHub `releases`
3. La page est live sur `go.viqmusic.net/[slug]`
4. Pour forcer le re-scrape Discord/Facebook : [opengraph.xyz](https://www.opengraph.xyz)

---

## Stack

Vanilla HTML/CSS/JS — zéro dépendance serveur, zéro framework.  
Librairies : `JSZip` (génération ZIP côté client) · `Odesli API` via `corsproxy.io` (auto-remplissage liens) · `SimpleIcons CDN` (logos plateformes)
