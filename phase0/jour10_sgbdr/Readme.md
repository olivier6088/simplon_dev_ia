# Jour 10 - Les SGBDR

Objectif se familiariser avec d'autres SGBDR que sqlite (ex: MySQL, PostgreSQL, duckDB, etc...)

---

## MySQL

1. Installer MySQL sur votre poste de travail  
2. Refaire l'exercice SQL (fichier .ipynb) avec MySQL  

### Astuces
- Utilisez **MySQL Workbench** pour une interface graphique conviviale.
- Pour lancer le client MySQL en terminal :
```bash
mysql -u root -p
```
- Le fichier de configuration principal est souvent situé dans `/etc/mysql/my.cnf` (Linux) ou dans le répertoire d’installation sous Windows.
- Pensez à vérifier que le service MySQL est démarré (ex. : `sudo service mysql status`).

---

## PostgreSQL

1. Installer PostgreSQL sur votre poste de travail  
2. Refaire l'exercice SQL (fichier .ipynb) avec PostgreSQL  

### Astuces

1. En cas d'erreur d'installation sous Windows11 changez le chemin du dossier `data` vers par exemple `C:\PostgresData`
au lieu de `C:\Program Files\PostgreSQL\17`  
2. Lancer le service PostgreSQL depuis un terminal:
```bash
postgres -D C:\\PostgresData
```  
3. Utiliser **Postbird** (outil GUI léger) pour se connecter à un serveur PostgreSQL  
   (par défaut un utilisateur `postgres` avec le mot de passe `postgres` a été créé lors de l'installation).  
4. Créez vos tables et interrogez-les directement depuis Postbird.  
5. Alternative : utilisez **pgAdmin 4** si vous souhaitez un outil plus complet.  

---

## DuckDB

1. Installer DuckDB (binaire léger ou via `pip install duckdb`).
2. Refaire l’exercice SQL (fichier `.ipynb`) avec DuckDB.
3. Points forts :
   - Aucun serveur à configurer (mode embarqué).
   - Compatible avec des fichiers CSV et Parquet directement.
   - Peut être utilisé en Python ou R comme une simple librairie.

### Exemple rapide en Python
```python
import duckdb

con = duckdb.connect('mydb.duckdb')
con.execute("CREATE TABLE users(id INTEGER, name VARCHAR);")
con.execute("INSERT INTO users VALUES (1, 'Alice'), (2, 'Bob');")
print(con.execute("SELECT * FROM users").fetchall())
```

---

## Bonus - SGBDR avec Docker

Si vous préférez éviter une installation locale, vous pouvez utiliser Docker pour lancer un SGBDR rapidement.

### Exemple : lancer PostgreSQL
```bash
docker run --name my_postgres -e POSTGRES_PASSWORD=postgres -d -p 5432:5432 postgres
```

### Exemple : lancer MySQL
```bash
docker run --name my_mysql -e MYSQL_ROOT_PASSWORD=root -d -p 3306:3306 mysql
```

> Avantage : vous pouvez facilement démarrer/arrêter/supprimer la base sans impacter votre système.

---

## Liens utiles

- [MySQL](https://www.mysql.com/fr/)  
- [PostgreSQL](https://www.postgresql.org/)  
- [Postbird](https://github.com/Paxa/postbird)  
- [DuckDB](https://duckdb.org/)  
- [MySQL vs PostgreSQL](https://www.data-bird.co/blog/postgresql-vs-mysql)  
- [pgAdmin 4](https://www.pgadmin.org/)  
- [Docker](https://www.docker.com/)  
