## 🥋 Thème : *Les Apprenants Z – L’école de la Programmation Suprême*

Voici **10 exercices progressifs** en **Python orienté objet**, avec une montée en difficulté progressive :
du simple constructeur jusqu’à l’héritage, le polymorphisme et les attributs de classe.

### 🧩 Exercice 1 — Créer sa première classe

**Objectif :** Créer une classe simple avec des attributs d’instance.

Crée une classe `GuerrierZ` avec :

* un attribut `nom`
* un attribut `niveau_energie`

Puis crée deux objets :

* `Goku` (niveau_energie = 9000)
* `Végéta` (niveau_energie = 8500)

Affiche leur énergie respectivement.

---

### 🧩 Exercice 2 — Ajouter une méthode

**Objectif :** Apprendre à définir des méthodes dans une classe.

Ajoute à la classe `GuerrierZ` une méthode `se_presenter()`
qui affiche :

> "Je suis {nom}, mon énergie est de {niveau_energie}."

Appelle cette méthode pour Goku et Végéta.

---

### 🧩 Exercice 3 — L’apprenant Super Saiyan

**Objectif :** Introduire la création d’un objet issu d’un autre univers (les apprenants).

Crée une classe `ApprenantZ` avec :

* `prenom`
* `specialite` (ex : “Python”, “Git”, “IA”)
* une méthode `etudier()` qui affiche :

  > "{prenom} étudie intensément la spécialité {specialite}."

Crée les objets suivants :

* `Michel` (React)
* `Flavie` (IA)
* `Fidel` (Git)

Fais-les étudier.

---

### 🧩 Exercice 4 — Interaction entre classes

**Objectif :** Faire interagir deux classes différentes.

Ajoute à la classe `GuerrierZ` une méthode `former(apprenant)`
qui prend un objet `ApprenantZ` et affiche :

> "{nom} forme {apprenant.prenom} à devenir un codeur Super Saiyan !"

Exemple :

```python
goku.former(Michel)
# Goku forme Michel à devenir un codeur Super Saiyan !
```

---

### 🧩 Exercice 5 — Attributs privés et sécurité

**Objectif :** Découvrir l’encapsulation.

Ajoute un attribut **privé** `__niveau_secret` à `GuerrierZ` (ex : Salle du temps).
Ajoute une méthode `devoiler_secret()` qui affiche ce niveau,
mais seulement si le `nom` de l’objet est `"Goku"`.

Test :

```python
vegeta.devoiler_secret()  # Refusé
goku.devoiler_secret()    # Affiche le niveau secret
```

---

### 🧩 Exercice 6 — Héritage

**Objectif :** Introduire la dérivation d’une classe.

Crée une classe `GuerrierSaiyan` qui **hérite** de `GuerrierZ`.
Elle ajoute un attribut `transformation` (ex : "Super Saiyan 2")
et redéfinit la méthode `se_presenter()` pour inclure cette transformation.

Exemple :

```python
gohan = GuerrierSaiyan("Gohan", 10000, "Super Saiyan 2")
gohan.se_presenter()
# Je suis Gohan, énergie 10000, transformation : Super Saiyan 2
```

---

### 🧩 Exercice 7 — Polymorphisme

**Objectif :** Montrer que différentes classes peuvent partager une méthode avec un comportement différent.

Fais en sorte que :

* `GuerrierZ` ait une méthode `agir()` → affiche “Je me bats pour protéger la Terre.”
* `ApprenantZ` ait aussi une méthode `agir()` → affiche “Je code pour protéger le réseau !”

Ensuite, place plusieurs objets (`Goku`, `Flavie`, `Michel`) dans une même liste et fais-les agir dans une boucle.

---

### 🧩 Exercice 8 — Attribut de classe

**Objectif :** Comprendre les variables partagées.

Ajoute un **attribut de classe** `nombre_total` dans `ApprenantZ`
qui compte combien d’apprenants ont été créés.

Chaque fois qu’un nouvel objet est instancié, on incrémente ce compteur.

Exemple :

```python
print(ApprenantZ.nombre_total)  # 3 (si 3 apprenants créés)
```

---

### 🧩 Exercice 9 — Composition (un cours contient des apprenants)

**Objectif :** Créer une relation "a un" entre objets.

Crée une classe `CoursZ` avec :

* un `nom_cours` (ex : “Combat orienté objet”)
* une liste d’`apprenants`

Ajoute une méthode `ajouter_apprenant(apprenant)`
et une méthode `afficher_apprenants()`.

Exemple :

```python
cours = CoursZ("Combat orienté objet")
cours.ajouter_apprenant(Michel)
cours.ajouter_apprenant(Flavie)
cours.afficher_apprenants()
# Apprenants du cours "Combat orienté objet" : Michel, Flavie
```

---

### 🧩 Exercice 10 — Fusion ultime 💥

**Objectif :** Combiner tout ce qui a été appris.

Crée :

* une classe `FormateurZ` qui hérite de `GuerrierZ`

* une méthode `donner_cours(cours)` qui affiche :

  > "{nom} enseigne le cours {cours.nom_cours} à {len(cours.apprenants)} apprenants."

* un cours nommé `"Python Super Saiyan"`

* des apprenants : Michel, Fidel, Flavie

* un formateur : Goku

Fais Goku enseigner le cours et affiche un résumé.

---

## 🧠 Résumé des compétences couvertes

| Exercice | Notion principale         | Concept Python                         |
| -------- | ------------------------- | -------------------------------------- |
| 1        | Création de classe        | `__init__`, attributs                  |
| 2        | Méthodes d’instance       | `self`                                 |
| 3        | Plusieurs classes         | Objets multiples                       |
| 4        | Interaction entre classes | Passage d’objet en paramètre           |
| 5        | Encapsulation             | `__attribut`                           |
| 6        | Héritage                  | `class Enfant(Parent)`                 |
| 7        | Polymorphisme             | Même méthode, comportements différents |
| 8        | Attribut de classe        | `ClassName.attribut`                   |
| 9        | Composition               | Objets contenus dans d’autres objets   |
| 10       | Combinaison complète      | Héritage + composition + méthodes      |

---
