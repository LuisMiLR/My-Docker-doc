### 8. Bonnes pratiques et optimisation

- Minimiser la taille des images : Utilisez des images de base légères et nettoyez les caches de construction.
- Multi-stage builds : Permet de créer des images plus petites et plus efficaces.
- Utiliser .dockerignore : Exclure les fichiers et dossiers non nécessaires lors de la construction de l'image.
- Sécurité : Gardez vos images à jour et ne pas exécuter les conteneurs avec des privilèges élevés.

# Exemple de .dockerignore
node_modules
.git
Dockerfile
docker-compose.yml


# Multi-stage builds

# Etape 1 : Construction
FROM node:14 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Etape 2 : Production
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html


## 9. Conclusion
Docker est un outil puissant qui facilite le déploiement et la gestion des applications conteneurisées. En suivant ce cours, vous avez appris les bases de Docker, y compris la création d'images, la gestion des conteneurs, l'utilisation des réseaux et des volumes, et l'utilisation de Docker Compose pour orchestrer des applications multi-conteneurs.

Pour aller plus loin, explorez la documentation officielle de Docker et continuez à expérimenter avec vos propres projets.

