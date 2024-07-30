### 3. Concepts de base de Docker


## Images Docker
Une image Docker est un package léger, autonome et exécutable qui inclut tout le nécessaire pour faire fonctionner une pièce de logiciel, y compris le code, un runtime, des bibliothèques et des paramètres de configuration.

## Conteneurs Docker
Un conteneur est une instance en cours d'exécution d'une image. Les conteneurs sont légers et se lancent rapidement. Vous pouvez créer, démarrer, arrêter, déplacer ou supprimer un conteneur avec des commandes Docker simples.

## Dockerfile
Un Dockerfile est un fichier texte qui contient une série d'instructions pour construire une image Docker. Voici un exemple de Dockerfile simple :

# Utiliser une image de base officielle de Node.js
FROM node:14

# Définir le répertoire de travail dans le conteneur
WORKDIR /app

# Copier les fichiers de l'application dans le répertoire de travail
COPY . .

# Installer les dépendances de l'application
RUN npm install

# Exposer le port sur lequel l'application va tourner
EXPOSE 3000

# Commande pour lancer l'application
CMD ["node", "app.js"]
