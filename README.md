# Sondage 2.0 — déploiement

## Contenu
- `index.html` — le sondage public
- `admin.html` — l'espace admin (protégé par Supabase Auth)
- `netlify.toml` / `vercel.json` — configs de déploiement, un seul des deux est nécessaire selon l'hébergeur choisi

## Avant de déployer
Ajoute dans ce dossier la photo du plat utilisée dans le sondage (Q2 et Q10) :
- nom de fichier exact : `plat-attieke.jpg`
- si le fichier est absent, le sondage fonctionne quand même mais affiche un message de remplacement à la place de l'image.

## Déployer sur Netlify
1. Va sur https://app.netlify.com
2. "Add new site" → "Deploy manually"
3. Glisse-dépose ce dossier entier (avec le zip dézippé) dans la zone de dépôt
4. Le site est en ligne immédiatement, avec une URL du type `nom-aleatoire.netlify.app`
5. Accès au sondage : `https://ton-site.netlify.app/`
6. Accès admin : `https://ton-site.netlify.app/admin.html`

## Déployer sur Vercel
1. Va sur https://vercel.com/new
2. "Deploy" → glisse-dépose le dossier, ou connecte un repo GitHub contenant ces fichiers
3. Aucune configuration de build nécessaire (site statique)
4. Accès admin : `https://ton-site.vercel.app/admin.html`

## Sécurité — rappel
- `admin.html` n'est pas caché, juste protégé par mot de passe (Supabase Auth). N'importe qui connaissant l'URL peut voir l'écran de connexion, mais ne peut rien lire sans identifiants valides.
- Ne partage jamais l'URL `/admin.html` publiquement au même endroit que le lien du sondage.
