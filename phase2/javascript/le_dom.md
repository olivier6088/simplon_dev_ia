# 🌳 Qu’est-ce que le DOM ?

Le **DOM (Document Object Model)** est la **représentation en arbre** d’une page HTML.
Le navigateur transforme ton fichier HTML en une structure composée de **nœuds** (éléments, textes, attributs…).

Tu peux imaginer le DOM comme un arbre hiérarchique que JavaScript peut lire et modifier.

---

# 🧱 DOM = ensemble de *nœuds*

Chaque élément HTML devient un **nœud** :

* Document
* Éléments (`<html>`, `<body>`, `<p>`, `<div>`…)
* Textes
* Attributs
* Commentaires …

Exemple HTML :

```html
<body>
  <h1>Hello</h1>
  <p>Texte</p>
</body>
```

Représentation DOM :

```
DOCUMENT
└── html
    └── body
        ├── h1
        │   └── "Hello"
        └── p
            └── "Texte"
```

Chaque indentation représente un **parent** et ses **enfants**.

---

# 🪟 `window` : l’objet global

Dans un navigateur :

* `window` = **la fenêtre du navigateur**
* C’est l’objet **racine**, qui contient tout ce qui concerne la page.

Quelques exemples :

```js
window.alert("Salut !");
window.innerWidth;
window.location.href;
```

Même `setTimeout()` et `console.log()` viennent de `window`.

```
window
├── document
├── console
├── location
├── history
├── setTimeout
└── …
```

---

# 📄 `document` : le DOM de la page

`document` est une **propriété de window**.

Il représente **le document HTML chargé**.

```
window
└── document
    └── arbre DOM
```

Exemples :

```js
document.getElementById("titre");
document.querySelector("p");
document.body;
```

Si `window` = la maison,
`document` = le plan détaillé de toutes les pièces (DOM).

---

# 🌲 Vue d’ensemble : DOM complet en ASCII

Voici un schéma d’une page simple :

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Test</title>
  </head>
  <body>
    <h1 id="titre">Bonjour</h1>
    <p>Ceci est un paragraphe.</p>
  </body>
</html>
```

Représentation DOM :

```
DOCUMENT
└── html
    ├── head
    │   └── title
    │       └── "Test"
    └── body
        ├── h1 (id="titre")
        │   └── "Bonjour"
        └── p
            └── "Ceci est un paragraphe."
```

---

# 🎮 Comment JS interagit avec tout ça ?

Quand tu écris :

```js
const titre = document.getElementById("titre");
titre.textContent = "Modifié !";
```

Tu es en train de modifier **un nœud** dans l’arbre DOM.

```
DOM avant :                      DOM après :
"h1" → "Bonjour"                "h1" → "Modifié !"
```

Le navigateur met immédiatement à jour l’affichage.

---

# 🧩 Résumé clair

* Le navigateur transforme le HTML en **arbre DOM**.
* Le DOM est fait de **nœuds** hiérarchisés (document → html → body → éléments…).
* `window` est **l’objet global** du navigateur.
* `document` est **l’entrée du DOM**.
* JavaScript peut **lire**, **modifier**, **ajouter**, **supprimer** n’importe quel nœud.  
