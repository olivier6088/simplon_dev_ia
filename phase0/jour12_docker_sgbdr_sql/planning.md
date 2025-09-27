# Planning

8h00: Gérer compte apprenant Azure  
8h30: Prez des sites web  
9h00: Revenir sur SGBDR PostGreSQL local vs docker  
=> suivre tuto en autonomie: https://www.datacamp.com/fr/tutorial/postgresql-docker  
=> se rabattre sur le tutorial docker: https://www.datacamp.com/fr/tutorial/docker-tutorial  
=> suivre le cheatsheet postgresql en autonomie (ex: sample data)
=> pour aller plus loin, configurer un serveur PostgreSQL sécurisé avec SSL sous docker: https://lavoiedudev.com/docker-configurer-un-serveur-postgresql-securise-avec-ssl/  
=> lister les databases et les tables sous PostGreSQL avec psql: https://www.atlassian.com/data/admin/how-to-list-databases-and-tables-in-postgresql-using-psql  


13h00: Brief sql tournoi de cell


## Docker PostGreSQL

### Lancement du container

```bash
docker run --name postgres-db \
  -e POSTGRES_PASSWORD=mysecretpassword \
  -e POSTGRES_USER=myuser \
  -e POSTGRES_DB=mydatabase \
  -v postgres-data:/var/lib/postgresql/data \
  -p 5432:5432 \
  -d postgres
```

```bash
docker run --name postgres-db \
  -e POSTGRES_PASSWORD=postgres \
  -e POSTGRES_USER=postgres \
  -e POSTGRES_DB=dbz \
  -v postgres-data:/var/lib/postgresql/data \
  -p 5432:5432 \
  -d postgres
```

### Connexion avec `psql`

```bash
docker exec -it postgres-db psql -U myuser -d mydatabase
```

```bash
docker exec -it postgres-db psql -U postgres -d dbz
```

