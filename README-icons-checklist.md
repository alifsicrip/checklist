# Icône & PWA — site Suivi de Compétences (checklist)

## 1. Fichiers à déposer

Dans `assets/icons/` :
- `checklist-favicon.ico`
- `checklist-icon.svg`
- `checklist-apple-touch-icon.png`
- `checklist-icon-192.png`
- `checklist-icon-512.png`

À la racine du repo :
- `manifest.json` (renommer `manifest-checklist.json` téléchargé précédemment)

## 2. Bloc à coller dans le `<head>`

Chemins **absolus** — fonctionne quel que soit le niveau de dossier de la page.

```html
<link rel="icon" href="/checklist/assets/icons/checklist-favicon.ico" sizes="any">
<link rel="icon" type="image/svg+xml" href="/checklist/assets/icons/checklist-icon.svg">
<link rel="apple-touch-icon" href="/checklist/assets/icons/checklist-apple-touch-icon.png">
<link rel="manifest" href="/checklist/manifest.json">
```

## 3. Pages à mettre à jour

- [ ] `index.html`

Le site checklist ne compte qu'une seule page HTML (application à sections dynamiques via Firebase), donc une seule mise à jour suffit.

## 4. Vérification

Une fois en ligne (après un push GitHub Pages, ça prend 1–2 min) :
1. Ouvre la page → l'icône doit apparaître dans l'onglet du navigateur.
2. Sur mobile (Chrome Android) : menu ⋮ → **Ajouter à l'écran d'accueil**. L'icône bleu-turquoise avec la coche doit apparaître, et le site s'ouvre en plein écran sans barre d'adresse.
3. Optionnel : teste sur [manifest-validator.appspot.com](https://manifest-validator.appspot.com) que le `manifest.json` est bien lu (colle l'URL `https://alifsicrip.github.io/checklist/manifest.json`).

## 5. Point d'attention Firebase

L'installation PWA rend l'affichage disponible hors-ligne, mais **pas la synchronisation des données** (ajout/modification de compétences) tant qu'il n'y a pas de connexion. C'est normal — pas besoin de service worker supplémentaire pour ce cas d'usage, sauf si tu veux un vrai mode hors-ligne avec file d'attente de synchronisation plus tard.

## 6. Couleurs utilisées

| Usage | Couleur |
|---|---|
| Fond icône / `theme_color` | `#1D4F5C` |
| Accent (anneau de progression) | `#1A9AA4` |

Palette reprise directement du logo personnel (`AL_Logo_color-17.png`).
