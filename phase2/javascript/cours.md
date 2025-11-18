# Mini‑cours JavaScript débutant ⚡

> **Objectif :** Apprendre les bases de JavaScript en ~2h (théorie + pratique).  
> **Niveau :** Débutant  
> **Pré‑requis :** HTML de base (et un peu de CSS pour la démo DOM)

---

## 1) Qu’est-ce que JavaScript ?

JavaScript (JS) est le langage de programmation du **web**.
Il permet de rendre une page **interactive**, de modifier le **DOM**, de communiquer avec des **APIs**, et plus généralement de donner vie à l’interface.

Quelques points essentiels :

* Il s’exécute directement dans le **navigateur** (Chrome, Firefox, Edge…), mais aussi **côté serveur** grâce à **Node.js**.
* Pour observer et tester votre code, utilisez les outils du navigateur (F12) : la **Console** et l’**Inspecteur**.

---

## 2) Où écrire du JavaScript ?

Il existe trois façons d’ajouter du JavaScript dans une page web :

1. **Inline** — directement dans un attribut HTML
   → **À éviter**, car cela mélange HTML et JS et complique la maintenance.

2. **Interne** — dans une balise `<script>` placée en bas du `<body>`
   → Correct pour de petits tests, mais vite limité.

3. **Externe** — dans un fichier `.js` séparé
   → **Méthode recommandée** : plus propre, plus réutilisable, plus facile à organiser.

Exemple :

```html
<script src="js/script.js" defer></script>
```

`defer` permet de **charger le script sans bloquer le rendu** de la page et de **l’exécuter lorsque le DOM est entièrement chargé**.
C’est la manière moderne et conseillée de charger un script côté client.

---

### 💡 Mon conseil sous VS Code

* Créez un dossier `starter` avec :

  * un fichier `index.html`
  * un dossier `js/` qui contiendra vos fichiers `.js`
* Utilisez l’extension **Live Server** pour lancer rapidement votre page et tester vos scripts.

---

### 📝 Nota

Placez vos scripts dans `<head>` avec `defer`.
C’est la solution la plus propre ET la plus performante : le navigateur affiche immédiatement la page et exécute le JavaScript dès que le DOM est prêt.

---

## 3) Variables & types

```js
let nom = "Goku";     // string
const age = 30;       // number
let saiyan = true;    // boolean
let rien = null;      // null
let inconnu;          // undefined
```

- **`let`** : déclare une variable **modifiable**  
- **`const`** : déclare une valeur **non modifiable** (on ne peut pas la réassigner)  
- Principaux types en JavaScript :  
  **string**, **number**, **boolean**, **null**, **undefined**, **object**, **symbol**, **bigint**

Pour connaître le type d’une valeur :

```js
typeof nom
```

---

## 4) Affichage & saisie

```js
console.log("Hello JS");                 // afficher un message dans la console
alert("Coucou !");                       // afficher une fenêtre d’alerte
const prenom = prompt("Ton prénom ?");   // demander une saisie à l’utilisateur
```

---

## 5) Opérateurs

- **Arithmétiques** : `+` `-` `*` `/` `%` `**`  
- **Comparaison** : `===` `!==` `<` `<=` `>` `>=`  
- **Logiques** : `&&` `||` `!`  
- **Affectation combinée** : `+=` `-=` `*=` `/=`  

**Important** :
`==` effectue une **coercition de type** et peut donner des résultats inattendus.
→ Utilisez `===` (égalité stricte) dans la plupart des cas.

---

## 6) Conditions

```js
const age = Number(prompt("Âge ?"));
if (age >= 18) {
  console.log("Adulte");
} else if (age >= 12) {
  console.log("Adolescent");
} else {
  console.log("Enfant");
}
```

---

## 7) Boucles

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}

let n = 0;
while (n < 3) {
  console.log("n =", n);
  n++;
}
```

---

## 8) Tableaux (Arrays)

```js
const fruits = ["pomme", "banane", "orange"];
console.log(fruits[0]);        // accéder à un élément
for (const f of fruits) {
  console.log(f);              // parcourir le tableau
}
console.log(fruits.length);    // nombre d’éléments
fruits.push("kiwi");           // ajouter un élément
```

---

## 9) Fonctions

```js
function carre(x) { // Syntaxe classique
  return x * x;
}
console.log(carre(2));
```

```js
const carre2 = (x) => x * x;   // Syntaxe fléchée
console.log(5);
```

### Paramètres par défaut

```js
function saluer(nom = "ami") {
  console.log("Salut", nom);
}
saluer();
```

## 10) Objets

Un **objet** est une structure qui permet de regrouper des informations sous forme de **paires clé–valeur**. C’est l’un des piliers du langage JavaScript.  

### Déclaration d’un objet

```js
const perso = {
  nom: "Goku",
  race: "Saiyan"
};
```

### Accéder aux propriétés

Deux syntaxes possibles :

```js
console.log(perso.nom);       // notation point
console.log(perso["race"]);   // notation crochets
```

### Ajouter ou modifier une propriété

```js
perso.transformations = ["SSJ1", "SSJ2"];  // ajout
perso.nom = "Son Goku";                   // modification
```

### Parcourir les propriétés d’un objet

```js
for (const key in perso) {
  console.log(key, perso[key]);
}
```

### Objet avec méthodes

Une propriété peut aussi contenir une **fonction**, appelée *méthode* :

```js
const perso2 = {
  nom: "Vegeta",
  saluer() {
    console.log("Je suis " + this.nom);
  }
};

perso2.saluer();  // "Je suis Vegeta"
```

### Résumé

* Un objet stocke des données structurées.
* Accès via `.` ou `[]`.
* On peut ajouter, modifier ou supprimer des propriétés.
* Les méthodes permettent de donner un **comportement** à l’objet.

---

## 11) DOM : sélectionner & modifier

Javascript peut interagir avec le DOM, c'est-à-dire modifier le contenu affiché dans la page.  

```html
<button id="btn">Clique-moi</button>
<p id="msg"></p>

<script>
  const btn = document.getElementById("btn");
  const msg = document.getElementById("msg");

  btn.addEventListener("click", () => {
    msg.textContent = "Bouton cliqué !";
  });
</script>
```

---

## 12) Classes CSS dynamiques

```js
element.classList.add("actif");    // ajouter une classe 
element.classList.remove("actif"); // retirer une classe
element.classList.toggle("actif"); // ajouter ou retirer selon l'état actuel
```

---

## 13) Bonnes pratiques et débogage

### ✔️ Bonnes pratiques de code

* Donnez des **noms de variables et de fonctions compréhensibles**.
* Gardez des **fonctions courtes**, centrées sur une seule tâche.
* Utilisez **`const`** par défaut, et passez à **`let`** uniquement si la valeur doit changer.
* Si possible, utilisez un **linter** (comme ESLint) pour détecter les erreurs et améliorer la qualité du code automatiquement.

---

### 🔍 Déboguer son code

Outils pour comprendre ce qui se passe :

* `console.log(...)` : permet d’afficher des valeurs dans la console du navigateur.
* **Breakpoints** (points d’arrêt) :
  Dans l’onglet *Sources* des DevTools (F12), vous pouvez cliquer sur le numéro d’une ligne pour arrêter l’exécution du script et examiner toutes les valeurs à ce moment précis.

---

### ⚠️ Gestion des erreurs

Pour éviter que votre programme plante en cas de problème :

```js
try {
  // Code à tester
} catch (err) {
  console.error("Une erreur a eu lieu :", err);
} finally {
  // Ce bloc s'exécute toujours, qu'il y ait eu une erreur ou non
}
```

* `try` : on exécute du code “à risque”.
* `catch` : on intercepte et traite l’erreur.
* `finally` : s’exécute dans tous les cas (utile pour nettoyer, fermer une connexion, etc.).

---

## 14) JSON & APIs (aperçu)

Le **JSON** (*JavaScript Object Notation*) est un format texte utilisé partout sur le web pour échanger des données entre le navigateur et un serveur.
Il ressemble aux objets JavaScript, mais reste **du texte**, et doit être transformé pour être utilisé.

### 🔄 Convertir JSON ↔ objet JS

```js
const texte = '{"nom":"Vegeta","niveau":9000}'; // JSON = texte

const obj = JSON.parse(texte);   // JSON → objet JS
console.log(obj.niveau);          // 9000

console.log(JSON.stringify(obj)); // objet JS → JSON
```

* `JSON.parse()` : transforme une chaîne JSON en véritable objet JavaScript
* `JSON.stringify()` : transforme un objet JavaScript en chaîne JSON (utile pour envoyer au serveur)

---

## 🌐 Appeler une API depuis le navigateur

Le navigateur propose la fonction **fetch()** pour faire des requêtes HTTP (GET, POST, etc.).

Exemple simple :

```js
fetch("https://api.github.com/repos/javascript-tutorial/en.javascript.info/commits")
  .then(res => res.json())       // convertir la réponse JSON en objet JS
  .then(data => console.log(data[0])) // utiliser les données
  .catch(err => console.error(err));  // gérer les erreurs
```

### Comment ça fonctionne ?

1. **fetch(...)** envoie une requête réseau.
2. `.then(res => res.json())` lit le corps de la réponse et le convertit en JSON.
3. `.then(data => ...)` permet d'utiliser les données.
4. `.catch(...)` intercepte les erreurs (connexion, mauvaise URL, etc.).

---

## 🧠 Ce qu’il faut retenir

* Le JSON est **le format standard** pour transmettre des données entre navigateur et serveur.
* `JSON.parse()` et `JSON.stringify()` permettent de passer du texte JSON à un objet JS, et inversement.
* `fetch()` permet d’effectuer des requêtes réseau (API).
* Les appels réseau sont **asynchrones**, d’où l’usage de `.then()` ou `async/await`.

---

## ⭐ Version async/await (plus moderne)

Tu peux écrire le même code de façon plus lisible :

```js
async function charger() {
  try {
    const res = await fetch("https://api.github.com/repos/javascript-tutorial/en.javascript.info/commits");
    const data = await res.json();
    console.log(data[0]);
  } catch (err) {
    console.error(err);
  }
}

charger();
```
---

👉 Passe aux **exercices** pour pratiquer.

## Annexe

### Faut-il mettre des `;` en JavaScript ?

En JavaScript, le point-virgule est **optionnel** grâce à l’ASI (*Automatic Semicolon Insertion*), un mécanisme qui insère automatiquement les `;` manquants lorsque c’est possible.

Cependant, on continue souvent à les utiliser car ils apportent :

* **Clarté** : chaque instruction est explicitement terminée.
* **Sécurité** : ils évitent certains cas rares où l’ASI produit un comportement inattendu (ex: `return` suivi d’une ligne vide).
* **Cohérence** : beaucoup de projets, frameworks et règles ESLint/Prettier les utilisent.

**Conclusion :**
Les deux styles fonctionnent, mais l’important est de rester **cohérent** dans tout votre projet.  

Voici une version courte et prête à mettre dans ton cours :

---

### HTMLCollection vs NodeList

**HTMLCollection**

- Contient uniquement des **éléments HTML**  
- Collection **vivante** : se met à jour si le DOM change  
- Produite par les méthodes anciennes (`getElementsByTagName`, `getElementsByClassName`)  
- Peu pratique (pas de `forEach` natif)  

**NodeList**

- Peut contenir **tout type de nœud** (éléments, textes, etc.)  
- Généralement **statique** (ne change pas si le DOM change)  
- Produite par les sélecteurs modernes (`querySelector`, `querySelectorAll`)
- Plus flexible, supporte `forEach`

**Aujourd’hui, la solution recommandée :**
👉 Utiliser **NodeList** via `querySelectorAll()` (plus moderne, plus pratique, plus cohérent).

Exemple moderne typique:

```js
document.querySelectorAll(".btn").forEach(btn => {
  btn.addEventListener("click", () => console.log("click"));
});
```

Avec une HTMLCollection , il faudrait:

```js
Array.from(collection).forEach(...)
```

