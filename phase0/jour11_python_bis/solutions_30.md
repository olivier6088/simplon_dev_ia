# ✅ Solutions des 30 Exercices Python (Débutants à Intermédiaire)

---

## 🔹 Niveau 1 – Bases (1 → 10)

### 1)
```python
print("Bonjour, Python !")
```

### 2)
```python
print("Bonjour, Mickaël !")
```

### 3)
```python
a = 12
b = 5
print("Somme =", a + b)
print("Produit =", a * b)
```

### 4)
```python
minutes = int(input("Minutes : "))
print("Heures =", minutes / 60)
```

### 5)
```python
n = int(input("Nombre : "))
print("Carré =", n * n)
```

### 6)
```python
n = int(input("Nombre : "))
if n % 2 == 0:
    print("Pair")
else:
    print("Impair")
```

### 7)
```python
n = int(input("Nombre : "))
for i in range(1, 11):
    print(n, "x", i, "=", n * i)
```

### 8)
```python
prenom = input("Prénom : ")
age = input("Âge : ")
print("Bonjour", prenom + ", tu as", age, "ans.")
```

### 9)
```python
c = float(input("Température en °C : "))
f = c * 9/5 + 32
print("En Fahrenheit :", f)
```

### 10)
```python
a = int(input("a = "))
b = int(input("b = "))
a, b = b, a
print("Après échange : a =", a, " b =", b)
```

---

## 🔹 Niveau 2 – Conditions & Boucles (11 → 20)

### 11)
```python
age = int(input("Âge : "))
if age >= 18:
    print("Majeur")
else:
    print("Mineur")
```

### 12)
```python
import random
secret = random.randint(1, 10)
essai = int(input("Devine (1-10) : "))
if essai == secret:
    print("Bravo !")
else:
    print("Raté, c'était", secret)
```

### 13)
```python
N = int(input("N : "))
for i in range(1, N+1):
    print(i)
```

### 14)
```python
N = int(input("N : "))
somme = 0
for i in range(1, N+1):
    somme += i
print("Somme =", somme)
```

### 15)
```python
n = int(input("Nombre : "))
while n >= 0:
    print(n)
    n -= 1
```

### 16)
```python
n = int(input("Nombre : "))
fact = 1
for i in range(1, n+1):
    fact *= i
print("Factorielle =", fact)
```

### 17)
```python
n = int(input("Nombre : "))
est_premier = True
if n < 2:
    est_premier = False
for i in range(2, n):
    if n % i == 0:
        est_premier = False
        break
print("Premier ?" , est_premier)
```

### 18)
```python
import random
secret = random.randint(1, 10)
trouve = False
for _ in range(3):
    essai = int(input("Devine (1-10) : "))
    if essai == secret:
        print("Bravo !")
        trouve = True
        break
if not trouve:
    print("Raté, c'était", secret)
```

### 19)
```python
n = int(input("Hauteur : "))
for i in range(1, n+1):
    print("*" * i)
```

### 20)
```python
for n in range(1, 11):
    for i in range(1, 11):
        print(n, "x", i, "=", n * i)
    print("----")
```

---

## 🔹 Niveau 3 – Listes, Dictionnaires & Fonctions (21 → 30)

### 21)
```python
notes = [12, 15, 9, 18]
print("Moyenne =", sum(notes)/len(notes))
```

### 22)
```python
liste = [12, 15, 9, 18]
print("Min =", min(liste))
print("Max =", max(liste))
```

### 23)
```python
phrase = input("Phrase : ")
voyelles = "aeiouyAEIOUY"
compte = 0
for c in phrase:
    if c in voyelles:
        compte += 1
print("Voyelles =", compte)
```

### 24)
```python
mot = input("Mot : ")
print("Inversé =", mot[::-1])
```

### 25)
```python
fruits = ["pomme","banane","mangue"]
f = input("Fruit : ")
if f in fruits:
    print("Présent")
else:
    print("Absent")
```

### 26)
```python
personne = {"nom":"Ali","age":25}
print(personne["nom"], "a", personne["age"], "ans.")
```

### 27)
```python
personne = {"nom":"Ali","age":25}
personne["ville"] = "Paris"
print(personne)
```

### 28)
```python
def saluer(nom):
    print("Bonjour", nom)

prenoms = ["Marie","Lina","Jo"]
for p in prenoms:
    saluer(p)
```

### 29)
```python
def carre(n):
    return n*n

for i in range(1, 11):
    print(i, "->", carre(i))
```

### 30)
```python
import math
for i in range(1, 21):
    print(i, "->", math.sqrt(i))
```
