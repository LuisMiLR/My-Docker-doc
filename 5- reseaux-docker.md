### 5. Réseaux Docker

Docker permet de créer des réseaux pour les conteneurs, facilitant ainsi la communication entre eux. Il existe plusieurs types de réseaux Docker :

bridge : Réseau par défaut pour les conteneurs sur un hôte unique.
host : Les conteneurs partagent le réseau de l'hôte.
overlay : Utilisé pour les services Swarm, permettant aux conteneurs de différents hôtes de communiquer.

## Commandes de réseau Docker

# Lister les réseaux Docker
docker network ls

# Créer un réseau bridge
docker network create my-bridge-network

# Connecter un conteneur à un réseau
docker network connect my-bridge-network <container_id>

# Déconnecter un conteneur d'un réseau
docker network disconnect my-bridge-network <container_id>

# Supprimer un réseau Docker
docker network rm my-bridge-network
