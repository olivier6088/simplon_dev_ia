# Exercices JavaScript débutant (≈2h)

> À faire dans le navigateur (Console + petite page HTML), sauf mention Node.js.

## Exercice 1 — Bonjour console
Affiche `Bonjour JS` dans la console.

## Exercice 2 — Variables
Crée 3 variables `nom`, `age`, `estEtudiant` et affiche leurs valeurs et types dans la console.

## Exercice 3 — Saisie utilisateur
Demande à l’utilisateur son prénom avec `prompt()` puis affiche `Bonjour <prénom> !` dans la page (ex. via `document.body.innerHTML` ou un élément dédié).

## Exercice 4 — Conditions
Demande un nombre et affiche s’il est **positif**, **négatif** ou **nul**.

## Exercice 5 — Boucles
Affiche les nombres de 1 à 10 puis la **somme** des nombres de 1 à N (saisi par l’utilisateur).

## Exercice 6 — Tableaux
Crée un tableau de 5 prénoms. Affiche le **premier** et le **dernier**. Ajoute un prénom avec `push()`. Parcours le tableau pour tout afficher.

## Exercice 7 — Fonctions
Écris une fonction `estPair(n)` qui renvoie `true` si `n` est pair. Teste‑la sur quelques valeurs.

## Exercice 8 — Objets
Crée un objet `contact` avec `nom`, `email`, `telephone`. Affiche le mail. Ajoute une méthode `resume()` qui retourne une chaîne formatée.

## Exercice 9 — DOM : sélection & modification
Crée un bouton et un paragraphe. Au clic du bouton, change le **texte** et la **couleur** du paragraphe.

## Exercice 10 — DOM : liste dynamique
Crée un champ texte et un bouton “Ajouter”. Au clic, ajoute un `<li>` dans une `<ul>` avec le contenu saisi.

## Exercice 11 — Événements & classes
Permets de **cocher/décocher** un élément de liste (ajouter/retirer la classe `.done` au clic).

## Exercice 12 — JSON (bonus)
Convertis un objet JS en JSON (via `JSON.stringify`) puis reconvertis‑le (via `JSON.parse`) et affiche un des champs.

## Exercice 13 — fetch (bonus)
Récupère des données d’une API publique avec `fetch` (ex. GitHub) et affiche le **premier élément** dans la console.

## Exercice 14 — try/catch (bonus)
Écris une fonction qui parse du JSON fourni par l’utilisateur et gère les erreurs avec `try/catch`.

Bien sûr ! Voici **6 exercices supplémentaires** (niveaux débutant → intermédiaire), pour compléter et arriver à **20 exercices**.

## Exercice 15 — Manipulation des classes

Crée trois boutons : **Rouge**, **Vert**, **Bleu**.
Au clic sur chaque bouton, change la couleur d’arrière-plan de la page en ajoutant une classe correspondante au `<body>`.

## Exercice 16 — Minuteur simple

Crée un bouton “Démarrer” qui affiche dans un paragraphe :
`Temps : 1s`, `Temps : 2s`, etc.
(→ utiliser `setInterval()` et `clearInterval()`)

## Exercice 17 — Fonction fléchée & filter

À partir du tableau suivant :

```js
const nombres = [3, 8, 12, 5, 20, 7];
```

Utilise `filter()` pour récupérer uniquement les nombres **supérieurs à 10**, puis affiche-les.

## Exercice 18 — Objet + boucle

Crée un objet représentant un produit :

```js
const produit = {
  nom: "PC Gamer",
  prix: 1200,
  stock: 5
};
```

Parcours toutes ses **clés** et **valeurs** avec une boucle `for...in` et affiche-les proprement.

## Exercice 19 — Création d’éléments DOM

Ajoute un bouton “Créer un carré”.
À chaque clic, crée un `<div>` de 50×50 pixels avec une couleur aléatoire (background) et l’ajoute dans la page.

👉 utiliser `document.createElement()`, `appendChild()`

## Exercice 20 — API + affichage dans la page

Récupère 3 utilisateurs aléatoires via l’API :

```
https://randomuser.me/api/?results=3
```

Affiche dans la page :

* prénom
* nom
* photo

(→ nécessite `fetch`, `.json()`, et manipulation du DOM)

---
