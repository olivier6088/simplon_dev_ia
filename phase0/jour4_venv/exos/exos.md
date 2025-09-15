# Exercices — Environnements virtuels Python (venv)

Cette feuille contient **uniquement des indications** pour vous entraîner dans un *terminal*.  
Travaillez étape par étape, puis comparez vos réponses avec `corriges.md` une fois terminé.

## Prérequis
- Python installé et accessible dans le terminal (`python` ou `python3` selon la machine).
- Savoir ouvrir un terminal (macOS/Linux) ou **PowerShell**/**CMD** (Windows).
- Vous créerez un dossier de travail : `mon_projet_venv/`.

## Conseils multi‑plateformes (à lire une fois)
- Activation d’un venv : macOS/Linux (via `source`), Windows PowerShell (script `Activate.ps1`), Windows CMD (script `activate.bat`).
- Le binaire `python` et `pip` doivent venir **du venv** quand il est activé.
- Pour lister les fichiers : `ls` (macOS/Linux) ou `dir` (Windows).

---

## Exercice 1 — Initialiser le projet et créer un venv
**But :** disposer d’un dossier `mon_projet_venv` contenant un venv nommé `.venv`.
- Créez le dossier du projet et placez‑vous dedans.
- Créez un environnement virtuel nommé `.venv` avec le module standard de Python.
- Vérifiez que le venv a des sous‑dossiers (`bin/` côté macOS/Linux ou `Scripts/` côté Windows).
**À consigner :** le **chemin absolu** du Python du venv.

---

## Exercice 2 — Activer et vérifier l’isolement
**But :** s’assurer que `python` et `pip` pointent vers le venv.
- **Activez** le venv selon votre OS.
- Affichez le chemin de l’exécutable Python courant et la version de `pip`.
- Listez les paquets installés : l’environnement doit être minimal.
**Questions :** le chemin pointe‑t‑il **dans** `.venv` ? Combien de paquets voyez‑vous ?

---

## Exercice 3 — Installer une version précise
**But :** pratiquer le **pinnage de version**.
- Installez `requests` dans une **version exacte** (ex. `2.31.0`).
- En Python, importez le paquet et affichez sa version pour vérifier.
**Question :** que se passe‑t‑il si vous demandez une version inexistante ?

---

## Exercice 4 — Figer l’environnement
**But :** capturer l’état exact des dépendances dans `requirements.txt`.
- Générez un fichier `requirements.txt` depuis l’environnement courant.
- Ouvrez‑le et lisez les premières lignes.
**Questions :** quelles **dépendances indirectes** apparaissent ? Pourquoi figer des versions **exactes** ?

---

## Exercice 5 — Recréer l’environnement à l’identique
**But :** tester la **reproductibilité**.
- Désactivez le venv si besoin, supprimez `.venv`, recréez un nouveau `.venv` vide.
- Réinstallez toutes les dépendances **à partir** de `requirements.txt`.
**Vérification :** comparez la liste des paquets **avant/après** : doivent‑elles correspondre ?

---

## Exercice 6 — Contraintes de versions & mise à jour
**But :** comprendre les **intervalles** de versions.
- Installez `urllib3` avec la contrainte `>=2,<2.2`.
- Relevez sa version installée puis effectuez une mise à jour qui respecte la contrainte.
**Questions :** quelle est la dernière version **autorisée** ? Quand préférez‑vous une plage plutôt qu’une version exacte ?

---

## Exercice 7 — Désinstaller et vérifier
**But :** savoir revenir en arrière proprement.
- Désinstallez `urllib3`.
- Tentez de l’importer en Python et observez l’erreur attendue.
**Question :** quel type d’erreur confirme la désinstallation ?

---

## Exercice 8 (bonus) — Variable d’environnement en session
**But :** constater la portée **temporaire** des variables d’environnement.
- Définissez la variable `APP_ENV=dev` **dans la session** courante.
- Affichez‑la depuis Python.
- Ouvrez une **nouvelle** session : est‑elle encore définie ?
**Question :** comment la rendre **persistante** à l’ouverture du shell ?

---

## Exercice 9 (bonus) — Utiliser le venv comme noyau Jupyter
**But :** enregistrer le venv comme **kernel**.
- Installez le module nécessaire.
- Créez un noyau nommé `venv-cours` avec un libellé lisible.
- Vérifiez qu’il apparaît dans la liste des kernels.

---

## Exercice 10 (bonus) — `.gitignore` minimal
**But :** éviter de versionner le venv et les artefacts de build.
- Créez un `.gitignore` à la racine du projet.
- Ajoutez au minimum : `.venv/`, `__pycache__/`, et les artefacts de build Python.
- Vérifiez que Git ignore ces chemins.

---

## Dépannage rapide
- Si une commande n’est pas reconnue : vérifiez **shell** (PowerShell vs CMD) et **activation** du venv.
- Comparez `python --version` et le chemin de l’exécutable pour confirmer l’isolement.
- En cas de conflits de dépendances : resserrez les contraintes ou recréez le venv.
