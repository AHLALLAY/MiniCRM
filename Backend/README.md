# Configuration d'une API Laravel avec JWT Auth et PostgreSQL

Ce guide vous accompagne dans la configuration d'une API Laravel utilisant JWT pour l'authentification et PostgreSQL comme base de données.

## Prérequis

Avant de commencer, assurez-vous d'avoir installé :
- PHP 8.1 ou supérieur
- Composer
- PostgreSQL
- Git

## Installation et Configuration

### 1. Installation des dépendances PHP

```bash
composer install
    # Cette commande installe toutes 
    # les dépendances définies 
    # dans le fichier `composer.json`.
```

### 2. Installation et configuration de JWT Auth

#### Supprimer Sanctum
```bash
composer remove laravel/sanctum
```

#### Installation du package JWT Auth
```bash
composer require tymon/jwt-auth
```

#### Publication de la configuration JWT
```bash
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
```

### 3. Configuration de l'environnement

```bash
cp .env.example .env
# Créez votre fichier
# de configuration local
# à partir du template fourni.
```


### 4. Génération des clés de sécurité

```bash
# Clé d'application Laravel
php artisan key:generate

# Clé JWT pour l'authentification
php artisan jwt:secret
```

### 5. Configuration de la base de données PostgreSQL

Éditez le fichier `.env` et configurez les paramètres de connexion PostgreSQL :

```env
# Configuration de la base de données
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=nom_de_votre_db
DB_USERNAME=votre_username
DB_PASSWORD=votre_password

# Configuration JWT (optionnel - personnalisation)
JWT_SECRET=votre_secret_jwt
JWT_TTL=60
JWT_REFRESH_TTL=20160

# Configuration de l'application
APP_NAME="Mon API Laravel"
APP_ENV=local
APP_DEBUG=true
APP_URL=http://localhost:8000
```

### 6. Création de la base de données

#### Option 1 : Via la ligne de commande PostgreSQL
```bash
createdb nom_de_votre_db
```

#### Option 2 : Via psql
```bash
psql -U postgres
CREATE DATABASE nom_de_votre_db;
\q
```

#### Option 3 : Manuellement
dans l'interface de `PgAdmin4`

### 7. Exécution des migrations

```bash
php artisan migrate
```

Cette commande crée toutes les tables nécessaires dans votre base de données.

### 8. Insertion des données de test (optionnel)

```bash
php artisan db:seed
```

Exécute les seeders pour peupler la base de données avec des données de test.

### 9. Optimisation des performances (optionnel)

```bash
# Cache de configuration
php artisan config:cache

# Cache des routes
php artisan route:cache

# Cache des vues
php artisan view:cache
```

### 10. Lancement du serveur de développement

```bash
php artisan serve
```

Votre API sera accessible sur : **http://localhost:8000**

## Ressources utiles

- [Documentation Laravel](https://laravel.com/docs)
- [Documentation JWT Auth](https://jwt-auth.readthedocs.io/)
- [Documentation PostgreSQL](https://www.postgresql.org/docs/)

## Contribution au projet

### Important pour les contributeurs

⚠️ **OBLIGATOIRE :** Avant de commencer à travailler sur le projet, vous **devez** créer une branche spécifique pour vos modifications.

### Workflow de contribution

1. **Créer une branche** pour votre travail
2. **Effectuer vos modifications** et commits
3. **Pousser votre branche** : `git push origin nom-de-votre-branche`
4. **Créer une Pull Request** vers la branche principale
5. **Attendre la review** avant le merge
