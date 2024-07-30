### 6. Volumes Docker

Les volumes sont utilisés pour persister les données générées par et utilisées par les conteneurs Docker. Ils permettent de partager des données entre l'hôte et le conteneur, ainsi qu'entre plusieurs conteneurs.


## Commandes de volume Docker

# Lister les volumes Docker
docker volume ls

# Créer un volume
docker volume create my-volume

# Utiliser un volume dans un conteneur
docker run -d -v my-volume:/data <image_name>

# Supprimer un volume Docker
docker volume rm my-volume
