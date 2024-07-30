### 4. Commandes Docker détaillées

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


## Gestion des images

# Tagger une image Docker
docker tag <image_id> <repository:tag>

# Pousser une image vers un registre Docker
docker push <repository:tag>

# Tirer une image depuis un registre Docker
docker pull <repository:tag>

# Inspecter une image Docker
docker inspect <image_id>


