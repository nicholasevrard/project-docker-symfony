# project-docker-symfony
Crud : Create Read Update Delete user 

### Requirements
---

- PHP 8.2
- Symfony 6.4
- Apache 2.4
- MySQL 5.7
- Composer 2

### Usage
---

### Installation
---

# Etape 1 - cloner le projet
```
git clone https://github.com/Jonathanlight/project-docker-symfony.git 
$ cd project-docker-symfony
```

### Installation SSl
---

# Etape 1.2 aller dans le dossier docker/etc/apache/ssl/ pour generer le certificat ssl
```
cd docker/etc/apache/ssl/
```

# generer le certificat ssl en lancant la commande suivante:
```
openssl req -x509 -out server.crt -keyout server.key \
-newkey rsa:2048 -nodes -sha256 \
-subj '/CN=localhost' -extensions EXT -config <( \
printf "[dn]\nCN=localhost\n[req]\ndistinguished_name = dn\n[EXT]\nsubjectAltName=DNS:localhost\nkeyUsage=digitalSignature\nextendedKeyUsage=serverAuth")

```

# Etape 2 - demarrer les containers
```
$ make docker-run
```

# Etape 3 - acceder au container apache
```
$ make docker-exec apache bash
```

# Etape 4 - Install dependencies with composer
```
$ composer install
```

# Etape 5 - Lance les migrations de la base de données
```
$ php bin/console doctrine:migrations:migrate
```

### Configuration
---

### Deployment
---

### Authors
---

- g2r developpeur


