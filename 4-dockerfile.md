

## Dockerfile

Un Dockerfile est un fichier texte qui contient une série d'instructions pour construire une image Docker. 

La construction d’une image est décrite dans un Dockerfile  

Organisation en couches mises en cache et ré-utilisées 

Héritage d’images pour ne pas réinventer la roue

Zoom sur le build

 Voici un exemple de Dockerfile simple :

# Utiliser une image de base officielle de Node.js
FROM node:14

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

# Copier les fichiers de l'application dans le répertoire de travail
COPY . .

# Installer les dépendances de l'application
RUN npm i

# Exposer le port sur lequel l'application va tourner
EXPOSE 3000

# Commande pour lancer l'application
CMD ["node", "app.js"] [npm start]
