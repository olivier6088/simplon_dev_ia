# Correction exos javascript

Voici un **corrigé complet des 20 exercices**.

Testez sous https://jsfiddle.net/

---

## Exercice 1 — Bonjour console

**Énoncé**
Affiche `Bonjour JS` dans la console.

```js
console.log("Bonjour JS");
```

---

## Exercice 2 — Variables

**Énoncé**
Crée 3 variables `nom`, `age`, `estEtudiant` et affiche leurs valeurs et types.

```js
let nom = "Alice";
let age = 25;
let estEtudiant = true;

console.log(nom, typeof nom);
console.log(age, typeof age);
console.log(estEtudiant, typeof estEtudiant);
```

---

## Exercice 3 — Saisie utilisateur

**Énoncé**
Demande le prénom avec `prompt()` puis affiche `Bonjour <prénom> !` dans la page.

```js
const prenom = prompt("Ton prénom ?");
document.body.innerHTML = `<h1>Bonjour ${prenom} !</h1>`;
```

---

## Exercice 4 — Conditions

**Énoncé**
Demande un nombre et affiche s’il est positif, négatif ou nul.

```js
const n = Number(prompt("Entre un nombre :"));

if (n > 0) {
  console.log("Positif");
} else if (n < 0) {
  console.log("Négatif");
} else {
  console.log("Nul");
}
```

---

## Exercice 5 — Boucles

**Énoncé**
Affiche les nombres de 1 à 10 puis la somme de 1 à N.

```js
// 1 à 10
for (let i = 1; i <= 10; i++) {
  console.log(i);
}

// somme 1 à N
const N = Number(prompt("N ?"));
let somme = 0;
for (let i = 1; i <= N; i++) {
  somme += i;
}
console.log("Somme de 1 à", N, "=", somme);
```

---

## Exercice 6 — Tableaux

**Énoncé**
Tableau de 5 prénoms. Affiche premier, dernier, ajoute un prénom, parcours.

```js
const prenoms = ["Alice", "Bob", "Chloé", "David", "Emma"];

console.log("Premier :", prenoms[0]);
console.log("Dernier :", prenoms[prenoms.length - 1]);

prenoms.push("Fred");

for (const p of prenoms) {
  console.log(p);
}
```

---

## Exercice 7 — Fonctions

**Énoncé**
Écris `estPair(n)` qui renvoie `true` si `n` est pair.

```js
function estPair(n) {
  return n % 2 === 0;
}

console.log(estPair(2)); // true
console.log(estPair(3)); // false
console.log(estPair(10)); // true
```

---

## Exercice 8 — Objets

**Énoncé**
Crée un objet `contact`, affiche le mail, ajoute une méthode `resume()`.

```js
const contact = {
  nom: "Doe",
  email: "john.doe@example.com",
  telephone: "0102030405",
  resume() {
    return `${this.nom} — ${this.email} — ${this.telephone}`;
  }
};

console.log(contact.email);
console.log(contact.resume());
```

---

## Exercice 9 — DOM : sélection & modification

**Énoncé**
Bouton + paragraphe. Au clic, changer texte et couleur.

**HTML exemple :**

```html
<button id="btn">Clique-moi</button>
<p id="txt">Texte initial</p>
```

**JS :**

```js
const btn = document.getElementById("btn");
const txt = document.getElementById("txt");

btn.addEventListener("click", () => {
  txt.textContent = "Bouton cliqué !";
  txt.style.color = "red";
});
```

---

## Exercice 10 — DOM : liste dynamique

**Énoncé**
Champ texte + bouton “Ajouter” → ajoute un `<li>` dans une `<ul>`.

**HTML exemple :**

```html
<input id="item" type="text" placeholder="Nouvel élément">
<button id="add">Ajouter</button>
<ul id="liste"></ul>
```

**JS :**

```js
const input = document.getElementById("item");
const addBtn = document.getElementById("add");
const liste = document.getElementById("liste");

addBtn.addEventListener("click", () => {
  const valeur = input.value.trim();
  if (valeur === "") return;

  const li = document.createElement("li");
  li.textContent = valeur;
  liste.appendChild(li);
  input.value = "";
});
```

---

## Exercice 11 — Événements & classes

**Énoncé**
Permettre de cocher/décocher un element de liste (`.done`).

**CSS exemple :**

```css
.done {
  text-decoration: line-through;
  color: gray;
}
```

**HTML exemple :**

```html
<ul id="tasks">
  <li>Apprendre JS</li>
  <li>Boire un café</li>
  <li>Faire une pause</li>
</ul>
```

**JS :**

```js
const tasks = document.querySelectorAll("#tasks li");

tasks.forEach(li => {
  li.addEventListener("click", () => {
    li.classList.toggle("done");
  });
});
```

---

## Exercice 12 — JSON (bonus)

**Énoncé**
Convertis un objet JS en JSON puis reconvertis-le.

```js
const user = {
  nom: "Vegeta",
  niveau: 9000
};

const json = JSON.stringify(user);
console.log("JSON :", json);

const obj = JSON.parse(json);
console.log("Nom :", obj.nom);
```

---

## Exercice 13 — fetch (bonus)

**Énoncé**
Récupère des données d’une API publique (ex. GitHub) et affiche le premier élément.

```js
fetch("https://api.github.com/repos/javascript-tutorial/en.javascript.info/commits")
  .then(res => res.json())
  .then(data => {
    console.log("Premier commit :", data[0]);
  })
  .catch(err => {
    console.error("Erreur :", err);
  });
```

---

## Exercice 14 — try/catch (bonus)

**Énoncé**
Fonction qui parse du JSON fourni par l’utilisateur et gère les erreurs.

```js
function parseJSONUtilisateur() {
  const texte = prompt("Entre du JSON :");
  try {
    const obj = JSON.parse(texte);
    console.log("Objet parsé :", obj);
  } catch (err) {
    console.error("JSON invalide :", err.message);
  }
}

parseJSONUtilisateur();
```

---

## Exercice 15 — Manipulation des classes

**Énoncé**
3 boutons : Rouge, Vert, Bleu → changer la couleur de fond via des classes sur `<body>`.

**CSS exemple :**

```css
.rouge { background-color: red; }
.vert  { background-color: green; }
.bleu  { background-color: blue; }
```

**HTML exemple :**

```html
<button id="rouge">Rouge</button>
<button id="vert">Vert</button>
<button id="bleu">Bleu</button>
```

**JS :**

```js
const body = document.body;
const btnRouge = document.getElementById("rouge");
const btnVert = document.getElementById("vert");
const btnBleu = document.getElementById("bleu");

function setCouleur(classe) {
  body.classList.remove("rouge", "vert", "bleu");
  body.classList.add(classe);
}

btnRouge.addEventListener("click", () => setCouleur("rouge"));
btnVert.addEventListener("click", () => setCouleur("vert"));
btnBleu.addEventListener("click", () => setCouleur("bleu"));
```

---

## Exercice 16 — Minuteur simple

**Énoncé**
Bouton “Démarrer” → affiche `Temps : 1s`, `2s`, etc. (avec `setInterval`).

**HTML exemple :**

```html
<button id="start">Démarrer</button>
<button id="stop">Arrêter</button>
<p id="time">Temps : 0s</p>
```

**JS :**

```js
const startBtn = document.getElementById("start");
const stopBtn = document.getElementById("stop");
const timeP = document.getElementById("time");

let compteur = 0;
let intervalId = null;

startBtn.addEventListener("click", () => {
  if (intervalId !== null) return; // déjà en cours

  intervalId = setInterval(() => {
    compteur++;
    timeP.textContent = `Temps : ${compteur}s`;
  }, 1000);
});

stopBtn.addEventListener("click", () => {
  clearInterval(intervalId);
  intervalId = null;
});
```

---

## Exercice 17 — Fonction fléchée & filter

**Énoncé**
À partir de `nombres`, garder ceux > 10.

```js
const nombres = [3, 8, 12, 5, 20, 7];

const sup10 = nombres.filter(n => n > 10);

console.log(sup10); // [12, 20]
```

---

## Exercice 18 — Objet + boucle

**Énoncé**
Objet `produit`, parcours des clés/valeurs avec `for...in`.

```js
const produit = {
  nom: "PC Gamer",
  prix: 1200,
  stock: 5
};

for (const cle in produit) {
  console.log(cle, ":", produit[cle]);
}
```

---

## Exercice 19 — Création d’éléments DOM

**Énoncé**
Bouton “Créer un carré” → crée un carré 50×50 de couleur aléatoire.

**HTML exemple :**

```html
<button id="add-square">Créer un carré</button>
<div id="zone"></div>
```

**JS :**

```js
const btnSquare = document.getElementById("add-square");
const zone = document.getElementById("zone");

function couleurAleatoire() {
  const r = Math.floor(Math.random() * 256);
  const g = Math.floor(Math.random() * 256);
  const b = Math.floor(Math.random() * 256);
  return `rgb(${r}, ${g}, ${b})`;
}

btnSquare.addEventListener("click", () => {
  const div = document.createElement("div");
  div.style.width = "50px";
  div.style.height = "50px";
  div.style.display = "inline-block";
  div.style.margin = "5px";
  div.style.backgroundColor = couleurAleatoire();
  zone.appendChild(div);
});
```

---

## Exercice 20 — API + affichage dans la page

**Énoncé**
Utiliser `https://randomuser.me/api/?results=3` et afficher prénom, nom, photo.

**HTML exemple :**

```html
<button id="load-users">Charger utilisateurs</button>
<div id="users"></div>
```

**JS :**

```js
const btnUsers = document.getElementById("load-users");
const usersDiv = document.getElementById("users");

btnUsers.addEventListener("click", async () => {
  usersDiv.textContent = "Chargement...";

  try {
    const res = await fetch("https://randomuser.me/api/?results=3");
    const data = await res.json();
    usersDiv.textContent = "";

    data.results.forEach(user => {
      const card = document.createElement("div");
      const img = document.createElement("img");
      const p = document.createElement("p");

      img.src = user.picture.medium;
      img.alt = "Photo de profil";
      p.textContent = `${user.name.first} ${user.name.last}`;

      card.appendChild(img);
      card.appendChild(p);
      usersDiv.appendChild(card);
    });
  } catch (err) {
    usersDiv.textContent = "Erreur lors du chargement.";
    console.error(err);
  }
});
```

---