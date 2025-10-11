# Corrigés – HTML / CSS / JS

## Partie 1 : HTML

1.

```html
<!DOCTYPE html>
<html>
<head><title>Titre</title></head>
<body></body>
</html>
```

2. `<h1>Jean</h1>`
3. `<p>Phrase 1. Phrase 2.</p>`
4. `<img src="photo.jpg" alt="Une photo">`
5.

```html
<ul><li>Pomme</li><li>Banane</li><li>Orange</li></ul>
```

6.

```html
<ol><li>Faire bouillir l’eau</li><li>Mettre le café</li><li>Verser l’eau</li></ol>
```

7. `<a href="https://openai.com">OpenAI</a>`
8.

```html
<table>
<tr><th>Nom</th><th>Âge</th></tr>
<tr><td>Jean</td><td>20</td></tr>
<tr><td>Anna</td><td>22</td></tr>
</table>
```

9. `<p>Ce mot est <span class="highlight">important</span>.</p>`
10.

```html
<header>En-tête</header>
<main>Contenu</main>
<footer>Pied</footer>
```

## Partie 2 : CSS

1. `* { color: red; }`
2. `h1 { color: blue; }`
3. `.important { font-weight: bold; }`
4. `#special { font-style: italic; }`
5. `p { background-color: yellow; }`
6. `div { border: 2px solid black; }`
7. `h1 { text-align: center; }`
8. `p { font-size: 20px; }`
9.

```css
.container {
  display: flex;
  justify-content: center;
}
```

10.

```css
a:hover { color: red; }
```

## Partie 3 : JavaScript

1. `let prenom = "Jean";`
2. `console.log("Bonjour " + prenom);`
3.

```js
function carre(x) {
  return x * x;
}
```

4. `let tab = [1, 2, 3];`
5.

```js
for (let i=0; i<tab.length; i++) {
  console.log(tab[i]);
}
```

6.

```js
if (age >= 18) { console.log("Majeur"); }
else { console.log("Mineur"); }
```

7.

```js
document.getElementById("titre").innerText = "Hello";
```

8.

```html
<button onclick="console.log('Clique!')">Bouton</button>
```

9.

```html
<input id="champ" type="text">
<button onclick="console.log(document.getElementById('champ').value)">OK</button>
```

10.

```js
function changeFond() {
  document.body.style.backgroundColor = "green";
}
```
