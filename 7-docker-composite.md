### 7. Docker Compose

Docker Compose est un outil qui permet de définir et de gérer des applications multi-conteneurs. Avec Compose, vous utilisez un fichier YAML pour configurer les services de votre application.

# Exemple de fichier docker-compose.yml

version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: example


## Commandes Docker Compose 

# Lancer les services définis dans le fichier docker-compose.yml
docker-compose up

# Arrêter les services
docker-compose down

# Afficher les logs des services
docker-compose logs

# Redémarrer un service
docker-compose restart <service_name>

# Lister les services
docker-compose ps

# Mettre à jour les images et redémarrer les conteneurs
docker-compose pull
docker-compose up --detach


## Utilisation avancée de Docker Compose

- Variables d'environnement
Vous pouvez utiliser des variables d'environnement dans votre fichier docker-compose.yml pour rendre votre configuration plus flexible.

version: '3'
services:
  web:
    image: nginx
    ports:
      - "${WEB_PORT}:80"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: ${DB_PASSWORD}

- version:
Cette ligne spécifie la version du format du fichier Docker Compose. La version 3 est l'une des versions les plus utilisées et prend en charge de nombreuses fonctionnalités de Docker Compose. Différentes versions peuvent introduire ou supprimer des fonctionnalités, donc il est important de choisir la version appropriée pour votre cas d'utilisation.

- Services: 
Les services sont les composants principaux définis dans un fichier docker-compose.yml. Chaque service représente un conteneur ou un groupe de conteneurs qui travaillent ensemble.

  web:
    image: nginx
    ports:
      - "80:80"

1. Nom du service (web) : Le nom du service est web. Vous pouvez choisir n'importe quel nom pour vos services, mais il est recommandé d'utiliser des noms significatifs.

2. Image Docker (image: nginx) : Cette ligne indique que le service web utilise l'image Docker officielle de Nginx. L'image Nginx est un serveur web léger et performant.

3. Ports (ports) : La section ports permet de mapper les ports de l'hôte aux ports du conteneur. Ici, "80:80" signifie que le port 80 de l'hôte est mappé au port 80 du conteneur. Cela permet aux utilisateurs d'accéder à l'application web exécutée à l'intérieur du conteneur Nginx via le port 80 de l'hôte.

- Service db

  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: example

1. Nom du service (db) : Le nom du service est db, ce qui signifie que ce service représente une base de données.

2. Image Docker (image: postgres) : Cette ligne indique que le service db utilise l'image Docker officielle de PostgreSQL. 

3. Variables d'environnement (environment) : La section environement permet de définir des variables d'environnement qui seront disponibles à l'intérieur du conteneur. Ici, POSTGRES_PASSWORD est défini avec la valeur example. Cette variable est utilisée par PostgreSQL pour définir le mot de passe de l'utilisateur postgres par défaut.

1. version: '3' : Spécifie la version du fichier de configuration Docker Compose. 
2. services : Une section qui liste tous les services que Docker Compose doit gérer.
    web : Un service nommé web.
        image: nginx : Utilise l'image nginx depuis Docker Hub.
        ports :
            "80:80" : Mappe le port 80 de l'hôte (votre machine) au port 80 du conteneur, ce qui permet d'accéder à Nginx via http://localhost:80.
    db : Un service nommé db.
        image: postgres : Utilise l'image postgres depuis Docker Hub.
    environment :
        POSTGRES_PASSWORD : Définit la variable d'environnement POSTGRES_PASSWORD à example, ce qui configure le mot de passe de l'utilisateur PostgreSQL par défaut.




- Et vous pouvez définir ces variables dans un fichier .env :

WEB_PORT=8080
DB_PASSWORD=example

- Volumes et réseaux
Docker Compose permet également de définir des volumes et des réseaux partagés entre les services.

version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
    volumes:
      - web-data:/var/www/html
    networks:
      - my-network
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: example
    volumes:
      - db-data:/var/lib/postgresql/data
    networks:
      - my-network

volumes:
  web-data:
  db-data:

networks:
  my-network:


