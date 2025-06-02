
# Site Dynamique EPGT avec Netlify CMS

Ce site statique utilise **Netlify CMS** pour permettre la gestion dynamique de contenu (articles) via une interface d'administration simple et accessible depuis un navigateur.

## 🌐 Accès au site

- **Site public** : [https://epgt-dynamique.netlify.app](https://epgt-dynamique.netlify.app)
- **Interface d’administration** : [https://epgt-dynamique.netlify.app/admin](https://epgt-dynamique.netlify.app/admin)

## 🛠 Fonctionnalités

- Rédaction et publication d’articles via une interface graphique
- Stockage des fichiers médias (images) dans le dossier `images`
- Sauvegarde automatique via GitHub (Git Gateway)
- Redirection automatique depuis les liens d’invitation Netlify vers `/admin/`

## 🔁 Redirection

Le fichier `_redirects` à la racine du site permet à Netlify de rediriger toutes les requêtes vers `/admin/*` vers `/admin/index.html` (important pour le bon fonctionnement de Netlify CMS).

## 🌍 Interface en français

Pour passer l’interface de Netlify CMS en français, modifiez le fichier `admin/config.yml` et ajoutez la ligne suivante :

```yaml
locale: 'fr'
```

Exemple :

```yaml
backend:
  name: git-gateway
  branch: main
  repo: ParfaitEGT/epgt-dynamique
  site_domain: epgt-dynamique.netlify.app

locale: 'fr'
site_url: https://epgt-dynamique.netlify.app
local_backend: true

media_folder: "images"
public_folder: "/images"

collections:
  - name: "articles"
    label: "Articles"
    folder: "articles"
    create: true
    slug: "{{slug}}"
    fields:
      - { label: "Titre", name: "title", widget: "string" }
      - { label: "Date", name: "date", widget: "datetime" }
      - { label: "Contenu", name: "body", widget: "markdown" }
```

## 📁 Structure du projet

```
.
├── index.html
├── style.css
├── _redirects
├── README.md
├── articles/
│   └── un-article-exemple.md
├── images/
│   └── image.jpg
└── admin/
    ├── index.html
    └── config.yml
```

## ✉️ Assistance

Pour toute question ou assistance, contacter : `parfaitesaie@gmail.com`
