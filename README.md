# KAIROS | Site de production

Ce dossier est prêt pour GitHub Pages ou Cloudflare Pages.

## Contenu

- `index.html` : landing page finale
- `assets/images/` : logo, portrait optimisé et image de partage LinkedIn/WhatsApp
- `assets/icons/` : favicon et icônes
- `assets/js/analytics-config.js` : identifiants Google Analytics et Microsoft Clarity
- `robots.txt` : directives pour les moteurs de recherche
- `sitemap.xml` : plan du site à transmettre à Google Search Console
- `site.webmanifest` : identité du site sur mobile
- `CNAME` : domaine personnalisé `kairos-consultance.com`
- `404.html` : page d’erreur
- `.github/workflows/deploy-pages.yml` : déploiement automatique GitHub Pages

## 1. Mettre le site sur GitHub

1. Créer un dépôt nommé par exemple `kairos-site`.
2. Importer **le contenu du dossier**, pas le dossier parent.
3. Vérifier que `index.html` se trouve à la racine.
4. Dans GitHub : `Settings` → `Pages`.
5. Dans `Build and deployment`, choisir **GitHub Actions**.
6. Le workflow fourni publiera le site après chaque modification de la branche `main`.

## 2. Relier le domaine

Le fichier `CNAME` contient déjà :

```text
kairos-consultance.com
```

Dans Cloudflare DNS, ajouter les enregistrements demandés par GitHub Pages, puis activer HTTPS dans GitHub Pages.

## 3. Google Analytics 4

Créer une propriété GA4, récupérer l’identifiant de mesure au format `G-XXXXXXXXXX`, puis ouvrir :

```text
assets/js/analytics-config.js
```

Remplacer :

```javascript
googleAnalyticsId: "G-XXXXXXXXXX"
```

Le suivi s’activera automatiquement.

## 4. Microsoft Clarity

Créer un projet Clarity, récupérer son identifiant, puis remplacer :

```javascript
microsoftClarityId: "XXXXXXXXXX"
```

dans le même fichier.

## 5. Google Search Console

1. Ajouter la propriété de domaine `kairos-consultance.com`.
2. La vérification DNS via Cloudflare est la méthode recommandée.
3. Après validation, transmettre ce sitemap :

```text
https://kairos-consultance.com/sitemap.xml
```

## 6. Référencement et partage

Le site comprend déjà :

- une URL canonique ;
- les métadonnées Open Graph pour LinkedIn, Facebook et WhatsApp ;
- une image sociale 1200 × 630 px ;
- des données structurées Schema.org pour KAIROS et Valiha ;
- un sitemap ;
- un fichier robots.txt ;
- des images WebP optimisées ;
- les dimensions d’images pour limiter les déplacements visuels ;
- un chargement prioritaire du portrait principal.

## Important

Le formulaire utilise actuellement FormSubmit. Lors de la première soumission en production,
un message d’activation pourra être envoyé à `valihamananjara@gmail.com`.

Les identifiants Analytics et Clarity ne peuvent pas être inventés : ils restent volontairement
désactivés jusqu’à ce que les véritables identifiants soient renseignés.
