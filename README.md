# releases — VIQ landing pages

> Repo de déploiement automatique des landing pages de sorties musicales VIQ. Chaque dossier correspond à une release, accessible via `go.viqmusic.net/{slug}`.
>
> ⚡ Les fichiers de ce repo sont générés et publiés automatiquement par [generator-tools.html](https://github.com/sodanexus/Release-Royalities-Manager). Ne pas éditer manuellement.

![GitHub Pages](https://img.shields.io/badge/hébergement-GitHub%20Pages-black) ![Auto-generated](https://img.shields.io/badge/généré_par-Release_Manager-F55036)

---

## Structure

```
releases/
├── {slug}/
│   ├── index.html      ← Landing page self-contained
│   ├── cover.jpg       ← Pochette de la release
│   └── og.jpg          ← Image Open Graph (1200×630)
├── {slug}/
│   └── ...
└── README.md
```

Chaque `{slug}` correspond au titre de la sortie normalisé en minuscules sans espaces, ex. `missed-call`, `neon-drive`.

---

## Ce que contient chaque landing

- **Particles canvas** animé en fond
- **Cover** avec gradient d'intensité configurable
- **Couleur primaire** extraite automatiquement de la pochette
- **Liens streaming** — Spotify, Apple Music, Tidal, Deezer, Amazon, YouTube, Bandcamp, SoundCloud (icônes via SimpleIcons)
- **Réseaux sociaux** — Instagram, TikTok, Facebook + lien site
- **Section merch** Fourthwall si renseignée
- **OG tags complets** — `og:image`, `og:url`, Twitter Card, canonical vers `go.viqmusic.net/{slug}/`
- **Safe area insets** iOS

---

## Déploiement

Les landings sont publiées depuis `generator-tools.html` via l'API GitHub (push direct sur ce repo). Chaque publication pousse 3 fichiers : `index.html`, `cover.jpg`, `og.jpg`.

GitHub Pages sert le contenu statique. Le CNAME `go.viqmusic.net` pointe vers ce repo.

### Ajouter ou modifier une landing manuellement

1. Ouvrir `generator-tools.html` du Release Manager
2. Pour une nouvelle landing : remplir le formulaire → **Publier**
3. Pour modifier une landing existante : glisser l'`index.html` existant dans la zone d'import → modifier → **Publier**

---

## Configuration GitHub Pages

- **Source** : branche `main`, dossier `/`
- **CNAME** : `go.viqmusic.net`
- Chaque sous-dossier `/{slug}/` est automatiquement servi comme page statique
