# Programmation Orientée Objet (POO) en Python

## 🎯 Objectifs de la session

- Comprendre les notions de classe, objet, attribut, méthode, encapsulation, héritage et polymorphisme appliquées à Python  
- S'exercer sur un mini-projet à thème  

---

## 🧠 Partie théorique - Niveau Débutant

### 1️. Classe et objet

Une **classe** est comme un **plan de construction** ou une **recette** : elle décrit les **caractéristiques** et les **comportements** que partageront tous ses objets.

Exemple : la classe `Personne` définit les propriétés communes à toutes les personnes (nom, âge, etc.) et leurs actions (se présenter, etc.).

```python
class Personne:
    def __init__(self, prenom, age):
        self.prenom = prenom    # caractéristique 1
        self.age = age          # caractéristique 2
        self.humeur = "neutre"  # caractéristique 3

    # Méthode 1
    def se_presenter(self):
        print(f"Bonjour, je m'appelle {self.prenom} et j'ai {self.age} ans.")
```

*Nota: `self` désigne l'objet lui-même (l'instance courante)*

---

Une **instance** est un objet **construit à partir de cette classe** — c’est la concrétisation du plan.

```python
michel = Personne("Michel", 25)
flavie = Personne("Flavie", 22)
michel.se_presenter()  # Bonjour, je m'appelle Michel et j'ai 25 ans.
```

Chaque personne est **indépendante**, mais toutes suivent le **même modèle**.

---

Reprenons l'exemple ci-dessus en ajoutant la méthode 2:
```Python
class Personne:
    def __init__(self, prenom, age):
        self.prenom = prenom
        self.age = age
        self.humeur = "neutre"

    # Méthode 1
    def se_presenter(self):
        print(f"Bonjour, je m'appelle {self.prenom} et j'ai {self.age} ans.")
	
	# Méthode 2
	def parler(self, message):
		print(f"{self.prenom} dit : {message}")
```

- `message` est un paramètre de la méthode  
- il n'a pas vocation à être stocké dans l'objet,  
- il sert uniquement à cette action ponctuelle.  

Autrement dit:
>> Michel peut dire plein de phrases sans qu’on ait besoin de les garder toutes en mémoire.

Exemple:
```Python
michel = Personne("Michel", 25)
michel.parler("Bonjour !")
michel.parler("J’aime Python !")
```

Chaque message est utilisé, puis oublié après l’appel à parler().

---

🔹 Si on avait écrit self.message

```python
def parler(self, message):
    self.message = message
    print(f"{self.prenom} dit : {self.message}")
```

Alors le message deviendrait un attribut permanent de l’objet.
👉 Cela veut dire que chaque fois que Michel parle, on écrase le message précédent :

```python
michel.parler("Salut")
michel.parler("À bientôt")
print(michel.message)  # "À bientôt"
```

Ce n’est pas une erreur, mais ce n’est pas utile si le message n’a pas besoin d’être enregistré dans l’état de la personne.

🔹 En résumé

- On écrit `self.prenom` car le prénom fait partie de la personne (état permanent).  
- On écrit simplement `message` car le message est juste un paramètre temporaire (action ponctuelle).  

👉 Règle d’or :

Si la donnée fait partie de l’identité ou de l’état durable de l’objet → `self.attribut`
Si c’est juste une information passagère pour une action → paramètre simple (`message`)

---

Les avantages des classes :

1. 🧩 **Organisation** : toutes les données et méthodes d’une personne sont regroupées.
2. 🔁 **Réutilisation** : une seule recette permet de créer autant d’objets que nécessaire.
3. ⚙️ **Évolution** : tu peux améliorer la classe sans tout réécrire (ex : ajouter un attribut “ville”).

---

### 2️. Encapsulation

L’**encapsulation** consiste à **protéger les données internes** d’un objet.
Certaines informations ne doivent pas être modifiées directement depuis l’extérieur.

Exemple : on crée un compte “Apprenant” avec un attribut privé pour son nombre de points.

```python
class Apprenant:
    def __init__(self, prenom, niveau):
        self.prenom = prenom
        self.niveau = niveau
        self.__points = 0  # attribut privé

    def ajouter_points(self, valeur):
        if valeur > 0:
            self.__points += valeur

    def afficher_points(self):
        print(f"{self.prenom} a {self.__points} points.")
```

👉 Ici, `__points` est **privé** : il ne peut pas être modifié directement de l’extérieur.
On doit passer par les **méthodes sécurisées**.

```python
gael = Apprenant("Gaël", "Intermédaire")
gael.ajouter_points(15)
gael.afficher_points()   # Gaël a 15 points.
```

Si on essaye de faire `gael.__points = 999`, cela **ne changera pas** la vraie valeur protégée.
➡️ C’est la base de la **sécurité des données** en programmation orientée objet.

---

🚗 Analogie avec une classe “voiture”

- **Sans encapsulation**:  
Tu accèdes directement au moteur et tu bidouilles les pistons à la main.
Résultat : tu peux faire exploser le moteur.  

- **Avec encapsulation**:  
Tu passes par des commandes prévues : le volant, la pédale d’accélérateur, les freins.
L’objet t’offre une interface contrôlée et sécurisée.  

---

⚡ En une phrase :
> L’encapsulation et les méthodes sécurisées permettent de garantir la cohérence, la sécurité et la stabilité de tes objets dans le temps.

---

### 3️. Héritage et polymorphisme

L’**héritage** permet à une classe de **réutiliser** le code d’une autre classe, tout en pouvant **ajouter** ou **modifier** des comportements.
Le **polymorphisme** permet d’utiliser les mêmes méthodes avec des comportements différents selon la classe.

Exemple : `Apprenant` hérite de `Personne`.

```python
class Personne:
    def __init__(self, prenom):
        self.prenom = prenom

    def se_presenter(self):
        print(f"Bonjour, je suis {self.prenom}.")

class Apprenant(Personne):
    def __init__(self, prenom, niveau):
        super().__init__(prenom)     # hérite de Personne
        self.niveau = niveau

    # Redéfinition de la méthode
    def se_presenter(self):
        print(f"Bonjour, je suis {self.prenom}, apprenant niveau {self.niveau}.")
```

Exemples d’utilisation :

```python
fidel = Personne("Fidel")
anna = Apprenant("Anna", "Débutant")

fidel.se_presenter()  # Bonjour, je suis Fidel.
anna.se_presenter()   # Bonjour, je suis Anna, apprenante niveau Débutant.
```

🔹 Ici, **la même méthode `se_presenter()`** se comporte différemment selon l’objet :

* pour une **Personne**, elle affiche une phrase simple ;
* pour un **Apprenant**, elle précise le niveau d’étude.

C’est ça le **polymorphisme** : une **même action** adaptée à chaque type d’objet.

---

### 4️. Exemple complet 🎓

```python
class Personne:
    def __init__(self, prenom, age):
        self.prenom = prenom
        self.age = age

    def se_presenter(self):
        print(f"Je m'appelle {self.prenom}, j'ai {self.age} ans.")

class Apprenant(Personne):
    def __init__(self, prenom, age, niveau):
        super().__init__(prenom, age)
        self.niveau = niveau
        self.__points = 0

    def progresser(self, points):
        self.__points += points
        print(f"{self.prenom} progresse de {points} points !")

    def afficher_statut(self):
        print(f"{self.prenom} ({self.niveau}) a actuellement {self.__points} points.")

# Création d'objets
nicolas = Apprenant("Nicolas", 70, "Débutant")
dorian = Apprenant("Dorian", 21, "Débutant")
olivier = Apprenant("Olivier", 24, "Débutant")

# Utilisation
nicolas.se_presenter()
dorian.progresser(10)
olivier.afficher_statut()
```

---

### 5️. Attributs de classe et d’instance

Les **attributs d’instance** appartiennent à **chaque objet** (chaque apprenant a ses propres valeurs),
tandis que les **attributs de classe** sont **communs à toutes les instances** d’une même classe.

#### 🧩 Exemple concret

```python
class Apprenant:
    # Attribut de classe — partagé par tous
    nombre_total = 0
    ecole = "Simplon"  # même école pour tous les apprenants

    def __init__(self, prenom, niveau):
        # Attributs d’instance — propres à chaque objet
        self.prenom = prenom
        self.niveau = niveau
        self.nb_cours_suivis = 0
        # On incrémente le compteur global à chaque création d’apprenant
        Apprenant.nombre_total += 1

    def suivre_cours(self):
        self.nb_cours_suivis += 1
        print(f"{self.prenom} suit maintenant {self.nb_cours_suivis} cours.")

    def afficher_infos(self):
        print(f"{self.prenom} ({self.niveau}) - École : {Apprenant.ecole}")

# Création de plusieurs apprenants
nicolas = Apprenant("Nicolas", "Débutant")
michel = Apprenant("Michel", "Intermédiaire")
flavie = Apprenant("Flavie", "Avancé")

michel.suivre_cours()
flavie.suivre_cours()
flavie.suivre_cours()

# Attribut de classe commun à tous
print(f"École commune : {Apprenant.ecole}")
print(f"Nombre total d'apprenants : {Apprenant.nombre_total}")
```

#### 📘 Explications :

* `prenom`, `niveau` et `nb_cours_suivis` ➜ **attributs d’instance** (chaque apprenant a les siens).
* `ecole` et `nombre_total` ➜ **attributs de classe** (partagés entre toutes les instances).

✅ Si on modifie `Apprenant.ecole`, le changement s’appliquera à **tous les apprenants**.
Mais si on modifie `michel.nb_cours_suivis`, cela **ne concerne que Michel**.

---

### 🧩 Résumé

| Concept           | Définition                                            | Exemple                           |
| ----------------- | ----------------------------------------------------- | --------------------------------- |
| **Classe**        | Modèle ou plan de création d’objet                    | `class Personne:`                 |
| **Objet**         | Instance concrète de la classe                        | `michel = Personne("Michel", 25)` |
| **Encapsulation** | Protection des données internes                       | `self.__points`                   |
| **Héritage**      | Transmission des attributs/méthodes d’une classe mère | `class Apprenant(Personne)`       |
| **Polymorphisme** | Méthodes communes avec comportements différents       | `se_presenter()` selon la classe  |

---
