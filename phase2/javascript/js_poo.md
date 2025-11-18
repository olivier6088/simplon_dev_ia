---

# 🐍➡️🟨 JavaScript pour les développeurs venant de Python

## Objets, classes et différences essentielles

JavaScript et Python utilisent tous les deux des objets, mais leur **philosophie** est différente.
Si tu viens de Python, cette section t’aidera à comprendre comment penser “à la manière JavaScript”.

---

# 1) Objet littéral : l’équivalent du `dict` Python

En JavaScript, on peut créer un objet directement, sans classe :

```js
const perso = {
  nom: "Goku",
  race: "Saiyan"
};
```

Équivalent en Python :

```python
perso = {
    "nom": "Goku",
    "race": "Saiyan"
}
```

✔ Très pratique
✔ Rapide
✔ Pas besoin de structure prédéfinie
❗ Le type de l’objet n’est pas strict (on peut modifier à volonté)

---

# 2) Ajouter, modifier, supprimer des propriétés

```js
perso.age = 30;       // ajout
perso.nom = "Son Goku"; // modification
delete perso.race;    // suppression
```

Python :

```python
perso["age"] = 30
perso["nom"] = "Son Goku"
del perso["race"]
```

---

# 3) Les méthodes : fonctions dans un objet

```js
const perso = {
  nom: "Goku",
  parler() {
    console.log("Bonjour, je suis " + this.nom);
  }
};

perso.parler();
```

Équivalent Python :

```python
class Perso:
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        print("Bonjour, je suis", self.nom)
```

📝 En JS, pas besoin de classe pour ajouter une méthode : un objet peut avoir des fonctions comme propriétés.

---

# 4) Les “classes” en JS : un sucre syntaxique (aka une écriture plus simple)

Si tu préfères une approche orientée objets plus proche de Python :

```js
class Perso {
  constructor(nom) {
    this.nom = nom;
  }

  parler() {
    console.log("Je suis " + this.nom);
  }
}

const goku = new Perso("Goku");
goku.parler();
```

Python :

```python
class Perso:
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        print("Je suis", self.nom)

goku = Perso("Goku")
goku.parler()
```

🧠 **Important :**
En JS, `class` utilise en interne le système prototype du langage.
C’est une syntaxe moderne, mais pas exactement la même mécanique que Python.

---

# 5) Prototype : ce que Python n’a pas

En JavaScript, les objets héritent via un **prototype**, pas via une classe :

```js
const base = { type: "Saiyan" };

const perso = Object.create(base);
perso.nom = "Goku";

console.log(perso.type); // hérité du prototype
```

En Python, ce concept n’existe pas sous la même forme.

→ C’est ce système qui permet à JS de créer des objets **sans classe**.

Tu peux ignorer les prototypes au début, mais comprendre leur existence t’aide à saisir la philosophie du langage.

---

# 6) Quand utiliser quoi ?

| Situation                         | Python | JavaScript                                        |
| --------------------------------- | ------ | ------------------------------------------------- |
| Stocker quelques infos            | dict   | objet littéral `{…}`                              |
| Créer plusieurs objets similaires | classe | classe (`class`)                                  |
| Objets dynamiques, flexibles      | dict   | objet littéral ou prototype                       |
| Héritage                          | classe | classe (syntaxe ✨), prototype (mécanique interne) |

---

# 7) Résumé essentiel

* JS permet de créer des objets **sans classe**, contrairement à Python.
* Les classes JS existent, mais ne sont qu’une **façade sur les prototypes**.
* La syntaxe objet `{…}` en JS est aussi naturelle que les dictionnaires en Python.
* Pour une structure réutilisable, utilise `class`, comme en Python.

