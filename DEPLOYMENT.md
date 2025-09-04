# Instructions de déploiement du site Z-Cleaner

Ce document fournit les instructions pour déployer le site web Z-Cleaner en production.

## Prérequis

- Un compte sur un service d'hébergement statique (Netlify, Vercel, GitHub Pages, etc.)
- Git installé sur votre machine
- Node.js (recommandé pour certains services de déploiement)

## Options de déploiement

### 1. Déploiement sur Netlify

Netlify est une plateforme d'hébergement gratuite pour les sites statiques avec des fonctionnalités avancées.

#### Déploiement manuel

1. Créez un compte sur [Netlify](https://www.netlify.com/)
2. Dans le tableau de bord Netlify, cliquez sur "New site from Git"
3. Connectez votre dépôt Git (GitHub, GitLab, Bitbucket)
4. Sélectionnez le dépôt contenant le site Z-Cleaner
5. Configurez les paramètres de build:
   - Dossier de publication: `website`
   - Commande de build: laissez vide (site statique)
6. Cliquez sur "Deploy site"

#### Déploiement via Netlify CLI

1. Installez Netlify CLI: `npm install -g netlify-cli`
2. Authentifiez-vous: `netlify login`
3. Déployez le site: `netlify deploy --dir=website --prod`

### 2. Déploiement sur GitHub Pages

1. Créez un dépôt GitHub nommé `z-cleaner` ou `z-cleaner-website`
2. Poussez le contenu du dossier `website` vers ce dépôt
3. Dans les paramètres du dépôt, activez GitHub Pages
4. Sélectionnez la branche `main` et le dossier `/` (racine)
5. Votre site sera disponible à l'adresse `https://[votre-nom-utilisateur].github.io/z-cleaner`

### 3. Déploiement sur Vercel

1. Créez un compte sur [Vercel](https://vercel.com/)
2. Importez votre projet depuis GitHub, GitLab ou Bitbucket
3. Configurez les paramètres:
   - Dossier racine: `website`
   - Commande de build: laissez vide
   - Dossier de sortie: `.`
4. Cliquez sur "Deploy"

## Mise à jour des liens de téléchargement

Avant le déploiement en production, assurez-vous de mettre à jour les liens de téléchargement dans le fichier `index.html` pour qu'ils pointent vers les fichiers DMG et EXE générés:

```html
<!-- Pour macOS -->
<a href="https://votre-serveur.com/downloads/Z-Cleaner-1.0.0-arm64.dmg">
    Télécharger pour macOS
</a>

<!-- Pour Windows -->
<a href="https://votre-serveur.com/downloads/Z-Cleaner-1.0.0-win.exe">
    Télécharger pour Windows
</a>
```

## Configuration d'un nom de domaine personnalisé

Pour utiliser un nom de domaine personnalisé (comme `z-cleaner.com`):

1. Achetez un nom de domaine auprès d'un registrar (Namecheap, GoDaddy, OVH, etc.)
2. Dans les paramètres de votre service d'hébergement, ajoutez votre domaine personnalisé
3. Configurez les enregistrements DNS selon les instructions du service d'hébergement
4. Attendez la propagation DNS (peut prendre jusqu'à 48h)

## Optimisations recommandées pour la production

- Minifiez les fichiers HTML, CSS et JavaScript
- Optimisez les images avec des outils comme ImageOptim
- Ajoutez un fichier robots.txt pour le référencement
- Configurez un certificat SSL pour HTTPS
- Ajoutez des méta-tags pour les réseaux sociaux (Open Graph, Twitter Cards)
