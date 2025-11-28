# Corrections

## ✅ Fiche 1 — Créer sa première classe

**Rappel :** classe simple avec attributs d’instance.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom, niveau_energie):
        self.nom = nom
        self.niveau_energie = niveau_energie

# Démo
goku = GuerrierZ("Goku", 9000)
vegeta = GuerrierZ("Végéta", 8500)
print(goku.niveau_energie)   # 9000
print(vegeta.niveau_energie) # 8500
```

---

## ✅ Fiche 2 — Ajouter une méthode

**Rappel :** méthode d’instance `se_presenter`.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom, niveau_energie):
        self.nom = nom
        self.niveau_energie = niveau_energie

    def se_presenter(self):
        print(f"Je suis {self.nom}, mon énergie est de {self.niveau_energie}.")

# Démo
goku = GuerrierZ("Goku", 9000)
vegeta = GuerrierZ("Végéta", 8500)
goku.se_presenter()   # Je suis Goku, mon énergie est de 9000.
vegeta.se_presenter() # Je suis Végéta, mon énergie est de 8500.
```

---

## ✅ Fiche 3 — L’apprenant Super Saiyan

**Rappel :** classe `ApprenantZ` + méthode `etudier`.

```python
# Solution
class ApprenantZ:
    def __init__(self, prenom, specialite):
        self.prenom = prenom
        self.specialite = specialite

    def etudier(self):
        print(f"{self.prenom} étudie intensément la spécialité {self.specialite}.")

# Démo
Michel  = ApprenantZ("Michel", "React")
Flavie  = ApprenantZ("Flavie", "IA")
Fidel  = ApprenantZ("Fidel", "Git")
Michel.etudier()  # Michel étudie intensément la spécialité React.
Flavie.etudier()  # Flavie étudie intensément la spécialité IA.
Fidel.etudier()  # Fidel étudie intensément la spécialité Git.
```

---

## ✅ Fiche 4 — Interaction entre classes

**Rappel :** `GuerrierZ.former(apprenant)` reçoit un ApprenantZ.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom):
        self.nom = nom

    def former(self, apprenant):
        print(f"{self.nom} forme {apprenant.prenom} à devenir un codeur Super Saiyan !")

class ApprenantZ:
    def __init__(self, prenom, specialite):
        self.prenom = prenom
        self.specialite = specialite

# Démo
goku = GuerrierZ("Goku")
Michel = ApprenantZ("Michel", "Python")
goku.former(Michel)  # Goku forme Michel à devenir un codeur Super Saiyan !
```

---

## ✅ Fiche 5 — Encapsulation (attribut privé)

**Rappel :** attribut privé `__niveau_secret` + contrôle par le nom.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom, niveau_energie, niveau_secret="Salle du temps"):
        self.nom = nom
        self.niveau_energie = niveau_energie
        self.__niveau_secret = niveau_secret  # privé

    def devoiler_secret(self):
        if self.nom == "Goku":
            print(f"Niveau secret de {self.nom} : {self.__niveau_secret}")
        else:
            print(f"Accès refusé pour {self.nom}.")

# Démo
goku = GuerrierZ("Goku", 9000)
vegeta = GuerrierZ("Végéta", 8500)
vegeta.devoiler_secret()  # Accès refusé pour Végéta.
goku.devoiler_secret()    # Niveau secret de Goku : Salle du temps
```

---

## ✅ Fiche 6 — Héritage

**Rappel :** `GuerrierSaiyan` hérite de `GuerrierZ` et override `se_presenter`.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom, niveau_energie):
        self.nom = nom
        self.niveau_energie = niveau_energie

    def se_presenter(self):
        print(f"Je suis {self.nom}, énergie {self.niveau_energie}")

class GuerrierSaiyan(GuerrierZ):
    def __init__(self, nom, niveau_energie, transformation):
        super().__init__(nom, niveau_energie)
        self.transformation = transformation

    def se_presenter(self):
        print(f"Je suis {self.nom}, énergie {self.niveau_energie}, transformation : {self.transformation}")

# Démo
gohan = GuerrierSaiyan("Gohan", 7000, "Super Saiyan 2")
gohan.se_presenter()  # Je suis Gohan, énergie 7000, transformation : Super Saiyan 2
```

---

## ✅ Fiche 7 — Polymorphisme

**Rappel :** mêmes méthodes `agir()` sur classes différentes.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom):
        self.nom = nom
    def agir(self):
        print("Je me bats pour protéger la Terre.")

class ApprenantZ:
    def __init__(self, prenom):
        self.prenom = prenom
    def agir(self):
        print("Je code pour protéger le réseau !")

# Démo
goku = GuerrierZ("Goku")
Flavie = ApprenantZ("Flavie")
Michel = ApprenantZ("Michel")

equipe = [goku, Flavie, Michel]
for perso in equipe:
    perso.agir()
# Je me bats pour protéger la Terre.
# Je code pour protéger le réseau !
# Je code pour protéger le réseau !
```

---

## ✅ Fiche 8 — Attribut de classe

**Rappel :** `nombre_total` compte les instances ; `ecole` partagé.

```python
# Solution
class ApprenantZ:
    nombre_total = 0
    ecole = "Simplon"

    def __init__(self, prenom, specialite):
        self.prenom = prenom
        self.specialite = specialite
        ApprenantZ.nombre_total += 1

# Démo
flavie = ApprenantZ("Flavie", "IA")
nicolas = ApprenantZ("Nicolas", "Python")
fidel = ApprenantZ("Fidel", "Git")
print(ApprenantZ.ecole)         # Simplon
print(ApprenantZ.nombre_total)  # 3
```

---

## ✅ Fiche 9 — Composition : un cours contient des apprenants

**Rappel :** relation “a un” (liste d’objets).

```python
# Solution
class ApprenantZ:
    def __init__(self, prenom):
        self.prenom = prenom

class CoursZ:
    def __init__(self, nom_cours):
        self.nom_cours = nom_cours
        self.apprenants = []

    def ajouter_apprenant(self, apprenant):
        self.apprenants.append(apprenant)

    def afficher_apprenants(self):
        noms = ", ".join(a.prenom for a in self.apprenants) or "Aucun"
        print(f'Apprenants du cours "{self.nom_cours}" : {noms}')

# Démo
Michel = ApprenantZ("Michel")
Flavie = ApprenantZ("Flavie")
cours = CoursZ("Combat orienté objet")
cours.ajouter_apprenant(Michel)
cours.ajouter_apprenant(Flavie)
cours.afficher_apprenants()
# Apprenants du cours "Combat orienté objet" : Michel, Flavie
```

=> 🧠 crée une nouvelle liste en mémoire à chaque création d’un cours.
Chaque instance a son propre espace d’apprenants.
Donc dans ce cas précis, l’initialisation est parfaite. 👌

---

## ✅ Fiche 10 — Fusion ultime

**Rappel :** combiner héritage + composition + méthodes.

```python
# Solution
class GuerrierZ:
    def __init__(self, nom, niveau_energie):
        self.nom = nom
        self.niveau_energie = niveau_energie

class FormateurZ(GuerrierZ):
    def donner_cours(self, cours):
        print(f"{self.nom} enseigne le cours {cours.nom_cours} à {len(cours.apprenants)} apprenants.")

class ApprenantZ:
    def __init__(self, prenom, specialite):
        self.prenom = prenom
        self.specialite = specialite

class CoursZ:
    def __init__(self, nom_cours):
        self.nom_cours = nom_cours
        self.apprenants = []

    def ajouter_apprenant(self, apprenant):
        self.apprenants.append(apprenant)

# Démo
cours = CoursZ("Python Super Saiyan")
Michel = ApprenantZ("Michel", "Python")
Fidel = ApprenantZ("Fidel", "Git")
Flavie = ApprenantZ("Flavie", "IA")
cours.ajouter_apprenant(Michel)
cours.ajouter_apprenant(Fidel)
cours.ajouter_apprenant(Flavie)

goku = FormateurZ("Goku", 9000)
goku.donner_cours(cours)
# Goku enseigne le cours Python Super Saiyan à 3 apprenants.
```

---
