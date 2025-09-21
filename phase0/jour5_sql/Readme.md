# 📚 Formation SQL Niveau 1 - CRUD

## Planning

- Matin: Veille sur SQL niveau1
- Après-midi: Exercices sur une bdd sqlite  

## 🚀 Guide d’installation

### 1. Installer Python et Jupyter
- Installe Python (≥3.9) depuis [python.org](https://www.python.org/downloads/)  
- Ne pas installer Anaconda (trop lourd pour ce cours)  
- **Ne pas installer Python via le Microsoft Store (problèmes de compatibilité)**  

### 2. Installer un environnement virtuel

`venv` (inclus avec Python)  
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
pip install --upgrade pip
pip install jupyter # plus lourd que pip install notebook mais plus complet avec convertisseurs html/pdf
```

### 3. Installer les extensions SQL
Dans ton environnement virtuel, installe :
```bash
pip install ipython-sql sqlalchemy pandas tabulate # pour afficher joliment les tableaux
```
> `sqlite3` est inclus par défaut avec Python.

### 4. Vérifier l’installation
Lance Jupyter :
```bash
jupyter notebook # ou ctrl+shift+p puis "Jupyter: Launch Notebook" (VSCode)
```
Puis dans une cellule :
```python
%load_ext sql
%sql sqlite://
```
➡️ Si aucun message d’erreur, tout est OK ✅

### 4. Lancer les notebooks
1. Ouvre les fichiers `.ipynb` (exos/projet/corrigés) dans Jupyter.  
2. Exécute la cellule :
   ```python
   %load_ext sql
   %sql sqlite:///dbz.db
   ```
   ➡️ Cela crée/utilise le fichier `dbz.db` comme base SQLite locale.

---

## 📂 Contenu
- `cours.qmd` → slides du cours (Quarto/Reveal.js)  
- `exos.ipynb` → exercices (15)  
- `exos_corriges.ipynb` → corrigés des exercices  
- `projet.ipynb` → projet CRUD DBZ  
- `projet_corrige.ipynb` → corrigé du projet  
- `README.md` → ce guide

---

## 💡 Conseils pédagogiques
- Toujours exécuter les cellules d’initialisation avant de faire les exos.  
- Relancer le kernel si la base est corrompue.  
- Sauvegarder régulièrement `dbz.db` si tu veux garder l’état actuel de la base.  

## Liens utiles

[SQLite : présentation de la célèbre bibliothèque de programmes](https://www.ionos.fr/digitalguide/sites-internet/developpement-web/sqlite/)
[SQLite3 Cheat Sheet](https://opensource.com/sites/default/files/gated-content/cheat_sheet_sqlite_0.pdf)
[Running SQL queries on Jupyter notebook](https://ploomber.io/blog/sql-on-jupyter/)
[SQLite3 avec Python](https://www.ionos.fr/digitalguide/sites-internet/developpement-web/sqlite3-avec-python/)

Bon apprentissage ! 🐉
