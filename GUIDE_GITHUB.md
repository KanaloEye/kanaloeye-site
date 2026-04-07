# 🚀 Guide — Push KanaloEye sur GitHub

---

## 📁 ÉTAPE 1 — Structure de ton dossier local

Assure-toi que ton dossier contient bien ces fichiers :

```
kanaloeye/
├── index.html              ← le site principal (fichier fourni)
├── logo.png
├── hero.JPG
├── hauteure.jpg
├── service1.JPG
├── service2.JPG
├── service3.JPG
├── real1.jpg
├── real2.jpg
├── real3.jpg
├── DJI_202506180905 52_0020_D.JPG
├── DJI_202506181158 49_0031_D.JPG
├── DJI_202601241418 52_0041_D.JPG
├── DJI_202602071045 28_0134_D.DNG
├── DJI_202602261516 47_0032_D.JPG
├── DJI_202602261519 54_0035_D.JPG
├── video moulin.mp4
└── (kanaloeye.txt, kanaloeye(2).html à ne pas inclure si inutiles)
```

---

## 🔧 ÉTAPE 2 — Initialiser Git (si pas encore fait)

Ouvre un terminal dans ton dossier du projet :

```bash
cd /chemin/vers/ton/dossier/kanaloeye

git init
git add .
git commit -m "Initial commit — site KanaloEye"
```

---

## 🌐 ÉTAPE 3 — Créer le dépôt sur GitHub

1. Va sur **https://github.com**
2. Clique sur le bouton **"New"** (ou "+", "New repository")
3. Nom du dépôt : `kanaloeye` (ou ton choix)
4. Visibilité : **Public** (obligatoire pour GitHub Pages gratuit)
5. **Ne coche PAS** "Add a README" (tu as déjà des fichiers)
6. Clique **"Create repository"**

---

## 🔗 ÉTAPE 4 — Connecter ton dossier local à GitHub

GitHub t'affichera les commandes. Copie-les, ou utilise celles-ci :

```bash
git remote add origin https://github.com/TON_PSEUDO/kanaloeye.git
git branch -M main
git push -u origin main
```

> ⚠️ Remplace `TON_PSEUDO` par ton vrai nom d'utilisateur GitHub.

---

## 📸 ÉTAPE 5 — Astuce pour les gros fichiers (vidéo)

Si `video moulin.mp4` est trop lourd pour GitHub (limite 100 MB) :

```bash
# Vérifier la taille
ls -lh "video moulin.mp4"

# Si > 50 MB, compresser avec ffmpeg
ffmpeg -i "video moulin.mp4" -vcodec libx264 -crf 28 "video moulin.mp4"

# OU héberger la vidéo sur un service externe (YouTube unlisted, Vimeo)
# et changer la balise <source> dans index.html
```

---

## 🌍 ÉTAPE 6 — Activer GitHub Pages (hébergement gratuit)

1. Sur GitHub, va dans ton dépôt → **Settings**
2. Dans la barre latérale, clique **Pages**
3. Sous "Source" → **Deploy from a branch**
4. Branche : **main** / Dossier : **/ (root)**
5. Clique **Save**

Après 1-2 minutes, ton site sera en ligne à l'adresse :
```
https://TON_PSEUDO.github.io/kanaloeye/
```

---

## 🔄 ÉTAPE 7 — Mettre à jour le site plus tard

À chaque modification :

```bash
git add .
git commit -m "Description de ta modif"
git push
```

GitHub Pages se met à jour automatiquement dans les 2 minutes.

---

## ⚠️ Problèmes fréquents

| Problème | Solution |
|---|---|
| `git push` refusé | `git pull origin main --rebase` puis push |
| Images ne s'affichent pas | Vérifier les noms de fichiers (majuscules/minuscules) |
| Vidéo trop lourde | Compresser ou héberger sur YouTube |
| Fichiers avec espaces | GitHub gère bien, mais tu peux renommer sans espaces |

---

## 📝 Noms de fichiers avec espaces

Les fichiers DJI ont des espaces dans leur nom (`DJI_202506180905 52_0020_D.JPG`).
GitHub les accepte, mais il vaut mieux les renommer :

```bash
# Renommer en masse (macOS/Linux)
for f in *.JPG; do mv "$f" "${f// /_}"; done
for f in *.DNG; do mv "$f" "${f// /_}"; done
mv "video moulin.mp4" "video_moulin.mp4"
```

Puis mettre à jour `index.html` avec les nouveaux noms.

---

✅ **Ton site KanaloEye sera en ligne et accessible gratuitement via GitHub Pages !**
