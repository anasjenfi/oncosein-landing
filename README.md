# OncoSein — page de téléchargement

## Ce qu'il y a dans ce dossier
- `index.html` — la page complète
- `assets/` — les captures d'écran et l'image de partage
- Il manque **OncoSein.apk** — c'est le fichier que les gens téléchargeront. Voir ci-dessous.

## Étape 1 — Générer le fichier APK

Le `.aab` déjà construit pour le Play Store n'est pas installable directement — il faut un `.apk`. Dans Git Bash, sur ton PC :

```
cd ~/Desktop/oncosein-standalone
eas build -p android --profile preview
```

Si le profil `preview` n'existe pas dans `eas.json`, ajoute-le (ou demande-moi de le faire) :

```json
"preview": {
  "distribution": "internal",
  "android": { "buildType": "apk" }
}
```

Une fois le build terminé, télécharge le fichier `.apk` depuis le lien qu'EAS affiche, renomme-le exactement `OncoSein.apk`, et place-le à la racine de ce dossier — au même niveau que `index.html`, pas dans `assets/`.

## Étape 2 — Mettre en ligne sur GitHub Pages

Même méthode que pour `oncosein-privacy` :

1. Crée un nouveau repo GitHub public, par exemple `oncosein-landing`
2. Mets-y ces trois éléments : `index.html`, `assets/`, `OncoSein.apk`
3. Repo → **Settings → Pages** → Source : `main`, dossier `/ (root)` → **Save**
4. La page sera en ligne à `https://anasjenfi.github.io/oncosein-landing/`

## Vérifications avant de partager le lien
- Ouvre la page et clique sur « Télécharger l'APK » — vérifie que le téléchargement démarre
- Teste l'installation sur ton propre téléphone en suivant les 5 étapes affichées sur la page
- Le numéro de version affiché (« v1.0.0 ») est en dur dans `index.html` — pense à le mettre à jour à chaque nouvelle version que tu publies ici
