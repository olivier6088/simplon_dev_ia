# Exercices

## Partie A — Analyse et nettoyage de `customers_dirty.csv`

1. Charger `customers_dirty.csv`
2. Afficher le nombre de lignes et de colonnes.  
3. Diagnostiquer les données : valeurs manquantes par colonne.  
4. Diagnostiquer les données : Afficher les doublons.
5. Supprimer les doublons (par `id` si dispo, sinon par combinaison `name` + `age` + `city`).  
6. Supprimer les doublons en considérant la combinaison de colonnes `name` + `age` + `city`.  
7. Uniformiser la colonne `city` (supprimer les espaces en trop, mettre en majuscule la première lettre).  
8. Supprimer les lignes avec des valeurs manquantes pour la colonne `city`.  
9. Vérifier s'il n'y a pas de valeurs aberrantes dans `age` (ex. âge négatif, > 120 ans, etc.).  
10. Supprimer les lignes avec des âges aberrants (ex. < 0 ou >= 120 ans).
11. Traiter les valeurs manquantes d’âge (les remplacer par la moyenne et arrondir à l’entier le plus proche).  
12. Exporter le CSV nettoyé dans `data/customers_clean.csv`.  
---

## Partie B — Analyse et nettoyage de `orders.csv`

1. Charger `orders.csv`.
2. Afficher le nombre de lignes et de colonnes.
3. Afficher les 5 premières lignes.
4. Normaliser le nom des colonnes (minuscules, underscores, pas d’espaces).
5. Afficher les types de données par colonne.  
6. Afficher les valeurs manquantes par colonne.  
7. Vérifier la présence de doublons.  
8. Vérifier les commandes sans client.  
9. Vérifier les clients sans commande.  
10. Supprimer les commandes sans client (customer_id absent de df).  
11. Pour les clients sans commande supprimer les de `orders`.  
12. Afficher le total des ventes (somme de `total_amount`).  
13. Afficher le total des ventes par `customer_id`, trié par ordre décroissant.  
14. Afficher le total des ventes par mois (extraire le mois de `order_date`).
15. Exporter le CSV nettoyé dans `data/orders_clean.csv`.    

---

## Partie C — Créer la bdd `marketing.db` et y insérer les données nettoyées

1. Créer une base SQLite `marketing.db`  
2. Créer une table `customers` à partir du fichier `customers_clean.csv`  
3. Créer une table `orders` à partir du fichier `orders_clean.csv`  
4. Vérifiez que cette base est exploitable  
