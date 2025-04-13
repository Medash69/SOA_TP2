API REST avec Express.js, SQLite et Keycloak – Résumé
Description
Ce projet est une API REST développée avec Node.js, Express.js et SQLite3 permettant la gestion d’un registre de personnes (ajout, consultation, modification, suppression).
L’authentification et l’autorisation sont assurées via Keycloak (OAuth 2.0).

Fonctionnalités principales

Opérations CRUD complètes sur les personnes

Authentification et autorisation sécurisées avec Keycloak

Stockage des données en base locale SQLite

Testabilité via Postman ou tout autre client HTTP

Structure du projet

arduino
Copy
Edit
TP2_API/
│── index.js              // Serveur principal Express
│── database.js           // Configuration et accès SQLite
│── keycloak-config.json  // Paramètres de Keycloak
│── package.json          // Dépendances et scripts du projet
│── README.md             // Documentation
└── node_modules/         // Modules Node.js installés
Installation et exécution

Prérequis

Node.js installé : https://nodejs.org

SQLite3 (intégré)

Keycloak disponible sur http://localhost:8080

Installation des dépendances

bash
Copy
Edit
npm install
Initialisation de la base SQLite
Si une ancienne base existe sans colonne "adresse", il faut la supprimer :

bash
Copy
Edit
rm maBaseDeDonnees.sqlite
S’assurer ensuite que database.js contient la bonne structure pour recréer la base.

Lancer le serveur

bash
Copy
Edit
node index.js
Le serveur est disponible sur : http://localhost:3000

Configuration de Keycloak

Démarrer Keycloak

Avec Docker :

bash
Copy
Edit
docker run -p 8080:8080 --name keycloak -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:latest start-dev
Sans Docker :

Télécharger Keycloak depuis keycloak.org

Extraire et naviguer dans le dossier bin

Lancer :

Windows : kc.bat start-dev

Linux/Mac : ./kc.sh start-dev

Accéder à l’interface d’administration
Aller sur http://localhost:8080/admin
Se connecter avec l’identifiant admin et le mot de passe admin.
