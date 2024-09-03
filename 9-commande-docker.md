### 9. Commandes Docker détaillées


## Commandes de base


# Vérifier la version de Docker
docker --version

# Lister les conteneurs en cours d'exécution
docker ps

# Lister tous les conteneurs (en cours d'exécution ou arrêtés)
docker ps -a

# Lancer un conteneur
docker run <image_name>

# Arrêter un conteneur
docker stop <container_id>

# Supprimer un conteneur
docker rm <container_id>

# Construire une image à partir d'un Dockerfile
docker build -t <image_name> .

# Lister les images Docker
docker images

# Supprimer une image Docker
docker rmi <image_id>

# Rechercher une image sur le registre Docker
docker search <marecherche>

# Récupérer une image depuis un registre Docker
docker pull <monimage>

# Construire une image à partir du Dockerfile dans le dossier en cours
docker build .

# Construire une image en la taguant
docker build -t <utilisateur/monapp> .

# Se connecter à Docker Hub
docker login

# Pousser une image vers Docker Hub
docker push <utilisateur/monapp>

# Supprimer une image Docker par son identifiant
docker image rm <idDeLImage>

# Lancer un conteneur en arrière-plan à partir d'une image
docker run -d <monrepository:monimage>

# Afficher le dernier conteneur créé
docker ps -l

# Créer un nouveau conteneur
docker create <leNomDeMonContainer>

# Relancer un conteneur précédemment créé
docker start <leNomDeMonContainer>

# Démarrer le dernier conteneur avec retour dans le terminal
docker start -a -i `docker ps -q -l`


## Commandes avancées

# Exécuter une commande dans un conteneur en cours d'exécution
docker exec -it <container_id> <command>

# Afficher les logs d'un conteneur
docker logs <container_id>

# Afficher l'utilisation des ressources d'un conteneur
docker stats <container_id>

# Exporter un conteneur vers un fichier tar
docker export <container_id> -o <filename.tar>

# Importer un conteneur à partir d'un fichier tar
docker import <filename.tar>

# Sauvegarder une image Docker vers un fichier tar
docker save -o <filename.tar> <image_name>

# Charger une image Docker à partir d'un fichier tar
docker load -i <filename.tar>

# Lancer Docker Compose
docker compose up -d

# Lister les conteneurs lancés via Docker Compose
docker compose ps

# Forcer le rebuild au lancement de Docker Compose
docker compose up --build

# Afficher les logs d'une application dans un terminal séparé
docker logs -f <containerId>

# Exécuter une commande dans le shell d'un conteneur
docker exec -it <idcontainer> <macommande>

# Récupérer la liste des conteneurs et leur ID
docker container ps

# Inspecter un conteneur pour obtenir des informations détaillées
docker inspect <containerid>

# Vider le cache de Docker
docker system prune --all

# Supprimer toutes les images Docker
docker rmi $(docker images -q)

# Supprimer tous les conteneurs Docker
docker rm $(docker ps -aq)

# Stopper tous les conteneurs Docker
docker stop $(docker ps -a -q)

# Lister les volumes Docker
docker volume ls

# Afficher la liste des fichiers dans un volume Docker
docker run -it --rm -v <nom/du/volume>:/vol busybox ls -l /vol

# Ouvrir une instance bash sur un volume Docker
docker run -it --rm -v <nom/du/volume>:/vol busybox sh

# Résoudre les problèmes de chemins d'accès sous Windows
$Env:COMPOSE_CONVERT_WINDOWS_PATHS=1

