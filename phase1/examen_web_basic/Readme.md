# Mini documentation – Rappel HTML / CSS / JS

## HTML (HyperText Markup Language)

* Structure de base d’une page :

  ```html
  <!DOCTYPE html>
  <html>
    <head>
      <title>Titre</title>
    </head>
    <body>
      <h1>Titre principal</h1>
      <p>Paragraphe</p>
    </body>
  </html>
  ```
* Balises fréquentes : `<h1>` à `<h6>`, `<p>`, `<a>`, `<img>`, `<ul>`, `<ol>`, `<li>`, `<div>`, `<span>`.
* Attributs : `id`, `class`, `src`, `alt`, `href`.

### Détail de quelques balises

* **Image (`<img>`)** : insère une image.

  ```html
  <img src="photo.jpg" alt="Description de l’image" width="200" height="150">
  ```

  * `src` : chemin vers l’image.
  * `alt` : texte alternatif (accessibilité).
  * `width` / `height` : taille en pixels.

* **Lien (`<a>`)** : crée un hyperlien.

  ```html
  <a href="https://exemple.com" target="_blank">Visiter le site</a>
  ```

  * `href` : adresse du lien.
  * `target="_blank"` : ouvre dans un nouvel onglet.

* **Tableaux (`<table>`)** : structure tabulaire.

  ```html
  <table border="1">
    <tr>
      <th>Nom</th>
      <th>Âge</th>
    </tr>
    <tr>
      <td>Jean</td>
      <td>20</td>
    </tr>
    <tr>
      <td>Anna</td>
      <td>22</td>
    </tr>
  </table>
  ```

  * `<table>` : table.
  * `<tr>` : ligne.
  * `<th>` : cellule d’en-tête.
  * `<td>` : cellule de données.

## CSS (Cascading Style Sheets)

* Inclusion :

  ```html
  <link rel="stylesheet" href="style.css">
  <style>p { color: red; }</style>
  ```
* Sélecteurs :

  * Par balise : `p { ... }`
  * Par classe : `.maClasse { ... }`
  * Par id : `#monId { ... }`
* Propriétés utiles : `color`, `background-color`, `font-size`, `margin`, `padding`, `border`, `display`, `flex`.

## JS (JavaScript)

* Insertion :

  ```html
  <script src="script.js"></script>
  <script>console.log("Hello");</script>
  ```
* Variables : `let`, `const`, `var`.
* Types : `number`, `string`, `boolean`, `array`, `object`.
* Conditions :

  ```js
  if (x > 10) { ... } else { ... }
  ```
* Boucles :

  ```js
  for (let i=0; i<5; i++) { ... }
  while (condition) { ... }
  ```
* Fonctions :

  ```js
  function addition(a, b) {
    return a + b;
  }
  ```
* DOM :

  ```js
  document.getElementById("id");
  document.querySelector(".classe");
  element.innerText = "Nouveau texte";
  ```
