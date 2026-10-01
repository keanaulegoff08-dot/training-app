# Carnet de Fonte v2 : version iPhone

Ce dossier contient l'application complète, prête à être installée sur l'écran d'accueil de ton iPhone. Elle fonctionne hors ligne, et tes séances, notes et vidéos restent sur ton téléphone.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | L'application (calendrier, programmes, séances, bilans, notes, vidéos) |
| `manifest.webmanifest` | Nom, icône et couleurs de l'app sur l'écran d'accueil |
| `sw.js` | Fait marcher l'app sans réseau et installe les mises à jour |
| `icons/` | Icônes de l'app |

## 1. Mettre l'app en ligne (une seule fois)

Safari ne peut installer l'app que si elle est servie depuis une adresse web en `https`. Deux options gratuites :

### Option A : GitHub Pages (recommandée)

1. Sur github.com, crée un dépôt, par exemple `training-app`.
2. Envoie les fichiers de ce dossier. Le dossier est déjà un dépôt git : depuis un terminal ouvert dans ce dossier, lance
   `git remote add origin https://github.com/keanaulegoff08-dot/training-app.git` puis `git push -u origin main`.
   Tu peux aussi faire glisser les fichiers dans la page du dépôt (« Add file » puis « Upload files »).
3. Dans le dépôt, va dans **Settings → Pages**. Choisis **Deploy from a branch**, la branche `main` et le dossier `/ (root)`, puis enregistre.
4. Après environ une minute, l'app est en ligne à l'adresse `https://keanaulegoff08-dot.github.io/training-app/`.

Le code de l'app devient public, mais tes données restent sur ton iPhone et ne sont jamais envoyées en ligne.

### Option B : Netlify Drop

1. Va sur app.netlify.com/drop et crée un compte gratuit.
2. Fais glisser ce dossier dans la page.
3. Netlify te donne une adresse en `https://…netlify.app`.

## 2. Installer sur l'iPhone

1. Ouvre l'adresse dans **Safari**. Chrome ou l'app Claude ne permettent pas l'installation.
2. Touche **Partager** (le carré avec la flèche vers le haut).
3. Choisis **Sur l'écran d'accueil**, puis **Ajouter**.

L'app s'ouvre alors en plein écran, sans barre Safari, et fonctionne sans réseau.

## 3. Récupérer tes séances de la version Claude

1. Dans la version Claude, ouvre l'onglet **Objectifs**, puis **Sauvegarde & iPhone**, et touche **Exporter**. Enregistre le fichier dans Fichiers ou iCloud Drive.
2. Dans l'app iPhone, ouvre l'onglet **Objectifs**, puis **Sauvegarde**, touche **Importer** et choisis ce fichier.

Les vidéos ne passent pas d'une version à l'autre : chaque vidéo reste là où elle a été ajoutée.

## Passer de l'ancienne app (carnet-de-fonte) à la v2

Sur iPhone, chaque app installée sur l'écran d'accueil garde ses propres données.
1. Dans l'ancienne app **Fonte**, ouvre **Objectifs**, puis **Sauvegarde**, touche **Exporter** et enregistre le fichier dans Fichiers.
2. Dans la nouvelle app, ouvre **Objectifs**, puis **Sauvegarde**, touche **Importer** et choisis ce fichier.
3. Vérifie que tes séances sont là, puis supprime l'ancienne icône si tu veux.

Les vidéos ne passent pas d'une app à l'autre.

## Tes données

- Les séances et les notes sont stockées dans l'app, sur l'iPhone. Les vidéos sont stockées sur l'iPhone, au format d'origine jusqu'à 150 Mo. Au-delà, elles sont compressées automatiquement.
- **Exporte une sauvegarde de temps en temps**, et toujours avant de supprimer l'app de l'écran d'accueil : la supprimer efface ses données.
- Le fichier de sauvegarde contient les séances, les notes, les programmes et les objectifs, mais pas les vidéos.

## Mettre à jour l'app

Remplace `index.html` et `sw.js` par les nouvelles versions, puis envoie-les (`git add . && git commit -m "maj" && git push`). L'iPhone récupère la mise à jour à la prochaine ouverture avec du réseau. Si elle n'apparaît pas, ferme l'app puis rouvre-la.
