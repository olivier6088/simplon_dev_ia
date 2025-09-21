# Jour2

## 1. Planning

1. Matin: arbre des compétences par les apprenants  
2. Après-midi: IDE + Git  

## 2. IDE (Visual Studio Code)

### Définition

Un **IDE** (Integrated Development Environment, ou Environnement de Développement Intégré) est un logiciel qui
regroupe tous les outils nécessaires pour écrire, tester et déboguer du code.
VS Code est aujourd’hui l’un des IDE les plus populaires grâce à sa légèreté et son écosystème d’extensions.

### Pourquoi utiliser un IDE ?

* **Autocomplétion** : propose automatiquement du code (fonctions, variables).
* **Débogage** : permet d’exécuter pas à pas pour comprendre d’où vient une erreur.
* **Extensions** : ajoutent des fonctionnalités (support de langages, intégration Git, formatage automatique).
* **Personnalisation** : thèmes, raccourcis, réglages selon les besoins.

### Démonstration pratique

1. Ouvrir VS Code → **File > Open Folder** → choisir un dossier projet.
2. Créer un fichier `hello.py`.
3. Écrire un programme simple.
4. Exécuter avec :

   ```bash
   python hello.py
   ```

---

## 3. Git

### Définition

**Git** est un système de gestion de versions.
Il permet de suivre l’évolution d’un projet, de collaborer à plusieurs et de revenir en arrière si besoin.

### Concepts clés

* **Dépôt (repository)** : espace contenant l’historique du projet.
* **Commit** : enregistrement d’un changement dans l’historique.
* **Branche** : ligne parallèle de développement.
* **Merge** : fusion de branches.
* **Remote** : copie distante du projet (ex. GitHub).

### Installation

https://git-scm.com/downloads

```bash
git --version
git config --global user.name "<name>"
git config --global user.email "<email>"
git init
git add Readme.md
git log
```

### Cycle de base

```bash
git init                 # Créer un dépôt local
git status               # 
git add .                # Préparer les fichiers à enregistrer
git commit -m "message"  # Créer un commit
git branch dev           # Créer une nouvelle branche
git checkout dev         # Basculer sur cette branche
git merge dev            # Fusionner la branche
git push origin main     # Envoyer sur GitHub
```

### Exemple concret

```bash
echo "Hello Git" > readme.txt
git init
git add readme.txt
git commit -m "Ajout premier fichier"
```

💡 **Bonne pratique** : faire des commits fréquents, avec des messages clairs.

## 4. GitHub

Créer un compte sur github.  

## 5. Workflow collaboratif (avec GitHub)

### Principes

* Chaque développeur travaille sur une **branche dédiée**.
* Les modifications passent par une **pull request** avant d’être intégrées.
* La branche `main` reste **stable** et toujours fonctionnelle.

### Exemple de workflow simplifié

```bash
# 1. Créer un dépôt sur GitHub

# 2. Cloner le projet
git clone <url>

# 3. Créer et travailler sur une branche dev
git checkout -b dev

# 4. Pousser la branche sur GitHub
git push origin dev

# 5. Ouvrir une pull request et merger sur main
```

💡 **Bonne pratique** : relire le code avant de merger pour éviter les bugs.

---