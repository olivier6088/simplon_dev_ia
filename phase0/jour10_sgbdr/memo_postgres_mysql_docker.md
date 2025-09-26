# 📘 Mémo : Démarrer et Arrêter PostgreSQL & MySQL

## 🔹 PostgreSQL

### 1. Sous **Linux**
Deux méthodes principales :

#### Avec `systemctl` (service système)
- Démarrer :
```bash
sudo systemctl start postgresql
```
- Arrêter :
```bash
sudo systemctl stop postgresql
```
- Redémarrer :
```bash
sudo systemctl restart postgresql
```

➡️ **Intérêt** : Intégré au système, gestion automatique des services (redémarrage, logs).

#### Avec `pg_ctl` (contrôle direct)
- Démarrer :
```bash
pg_ctl -D /var/lib/postgresql/15/main start
```
- Arrêter :
```bash
pg_ctl -D /var/lib/postgresql/15/main stop
```
- Vérifier l’état :
```bash
pg_ctl -D /var/lib/postgresql/15/main status
```

➡️ **Intérêt** : Contrôle fin, utile pour le debug ou si PostgreSQL n’est pas configuré comme service.

---

### 2. Sous **Windows**

#### Avec `services.msc` ou PowerShell
- Démarrer :
```powershell
net start postgresql-x64-15
```
- Arrêter :
```powershell
net stop postgresql-x64-15
```
*(adapter `15` selon votre version)*

➡️ **Intérêt** : simple si PostgreSQL est installé comme service Windows.

#### Avec `pg_ctl` (recommandé en Git Bash)
- Démarrer :
```bash
pg_ctl -D "C:/PostgresData" start
```
- Arrêter :
```bash
pg_ctl -D "C:/PostgresData" stop
```
- Redémarrer :
```bash
pg_ctl -D "C:/PostgresData" restart
```
- Vérifier l’état :
```bash
pg_ctl -D "C:/PostgresData" status
```

➡️ **Intérêt** :
- Ne dépend pas du service Windows.
- Pratique si plusieurs instances.
- Flexible pour le développement local.

---

## 🔹 MySQL

### Linux
- Démarrer :
```bash
sudo systemctl start mysql
```
ou
```bash
sudo systemctl start mysqld
```
- Arrêter :
```bash
sudo systemctl stop mysql
```
ou
```bash
sudo systemctl stop mysqld
```

### Windows (PowerShell)
- Démarrer :
```powershell
net start mysql
```
- Arrêter :
```powershell
net stop mysql
```

### Git Bash
- Arrêter :
```bash
mysqladmin -u root -p shutdown
```
➡️ (il faudra entrer le mot de passe root).

---

## 🔹 Avec Docker

### PostgreSQL
- Lancer un conteneur :
```bash
docker run --name my_postgres -e POSTGRES_PASSWORD=postgres -d -p 5432:5432 postgres
```
- Arrêter le conteneur :
```bash
docker stop my_postgres
```

### MySQL
- Lancer un conteneur :
```bash
docker run --name my_mysql -e MYSQL_ROOT_PASSWORD=root -d -p 3306:3306 mysql
```
- Arrêter le conteneur :
```bash
docker stop my_mysql
```

### Commandes utiles
- Voir les conteneurs actifs :
```bash
docker ps
```
- Arrêter un conteneur avec son ID :
```bash
docker stop <container_id>
```

➡️ **Intérêt** : permet de tester sans impacter le système local. Facile à démarrer/arrêter/supprimer.
