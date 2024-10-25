# Demo Application with Symfony 7 + PHP 8.3 + PostgreSQL 16 + Docker

## Prérequis
- Linux (Ubuntu 22.04 LTS ou autre)
- Docker
- Docker Compose

## Installation
- Cloner le dépôt
```bash
git clone
```

- Builder les images Docker
```bash
docker compose build
```

- Lancer les conteneurs Docker
```bash
docker compose up -d
```
## Utilisation

### Entrer dans le container php
```bash
docker compose exec php-symfo bash
```

### Exécuter les migrations
```bash
symfony console doctrine:migrations:migrate
```

### Créer un utilisateur
```bash
adduser username
chown -R username:username /var/www/html
```

### Lancer symfony server
```bash
symfony serve
```

### Voir le projet
- [http://localhost:8001](http://localhost:9000)

## Commandes utiles Docker
- Lister les conteneurs Docker
```bash
docker ps -a
```

- Supprimer des conteneurs Docker
```bash
docker rm -f $(docker ps -aq)
```

- Supprimer les images Docker
```bash
docker rmi -f $(docker images -aq)
```

- Supprimer les volumes Docker

```bash
docker volume rm $(docker volume ls -q)
```

- Suppression de tous les objets Docker
> ⚠️ **Avertissement** ⚠️
>
> Avec cette commande, vous supprimez définitivement tous les conteneurs, les images, les volumes et les réseaux Docker.
```bash
docker system prune -a
```
