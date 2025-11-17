# 🎯 Task Tracker Application

> Application full-stack de gestion des tâches avec API REST Spring Boot et PostgreSQL.
## 📖 Table des Matières

* [Description](#3-description-du-projet)
* [Fonctionnalités Clés](#4-fonctionnalités-clés)
* [Architecture Technique](#5-architecture-technique)
* [Prérequis](#6-démarrage-rapide)
* [Installation & Lancement](#6-démarrage-rapide)
* [Documentation API](#7-documentation-des-endpoints-api)
## 3. Description du Projet

Le **Task Tracker** est une solution de gestion de la productivité conçue pour aider les utilisateurs à **organiser, hiérarchiser et suivre la progression** de leurs tâches.

Cette application web full-stack permet de structurer les responsabilités au sein de **listes de tâches thématiques**, offrant une visibilité claire sur l'avancement grâce au calcul dynamique du pourcentage de complétion.
## 4. Fonctionnalités Clés

* **Gestion des Listes de Tâches :** CRUD complet pour les `TaskLists` (Créer, Mettre à jour, Supprimer).
* **Suivi de la Progression :** Affichage du **pourcentage d'achèvement** par liste de tâches.
* **Capture Détaillée des Tâches :** Les tâches incluent un titre, une description, une date d'échéance et un niveau de **Priorité** (`HIGH`, `MEDIUM`, `LOW`).
* **Statut de Tâche :** Marquage des tâches comme `OPEN` ou `CLOSED` pour un suivi précis.
* **Opérations Imbriquées :** Gestion des tâches dans le contexte d'une liste parente spécifique.
## 5. Architecture Technique

Le projet suit une architecture modulaire **full-stack** :

### Backend (API REST)
* **Framework :** **Spring Boot** (Java)
* **Persistance :** **Spring Data JPA** (Hibernate)
* **Base de Données :** **PostgreSQL** (lancée via Docker Compose)
* **Modèles :** Entités JPA pour `Task` et `TaskList`.
* **Logique Métier :** Gérée dans la couche `Services`, avec une gestion globale des exceptions (`GlobalExceptionHandler`).

### Frontend (Structure implicite)
* **Technologies :** Basé sur Node.js/npm (généralement React, Vue ou Angular).
* **Rôle :** Consomme l'API Spring Boot pour afficher l'interface utilisateur et gérer les interactions.
## 6. Démarrage Rapide

### Prérequis
* **Java 17+**
* **Maven** ou **Gradle** (pour le backend)
* **Docker** et **Docker Compose** (pour la base de données)
* **Node.js & npm** (pour le frontend)

### 🚀 Lancement du Backend (API)

1.  **Cloner le dépôt :**
    ```bash
    git clone [https://github.com/MariemMhadhbii/task-tracker-app.git](https://github.com/MariemMhadhbii/task-tracker-app.git)
    cd task-tracker-app/backend
    ```
2.  **Démarrer la base de données (PostgreSQL) :**
    Le fichier `docker-compose.yml` configure la base de données et est prêt à l'emploi.
    ```bash
    docker-compose up -d db
    ```
3.  **Lancer l'application Spring Boot :**
    ```bash
    # Si vous utilisez Maven
    ./mvnw spring-boot:run
    ```
    L'API sera disponible sur `http://localhost:8080`.

### 💻 Lancement du Frontend

1.  **Installer les dépendances :**
    ```bash
    cd ../frontend # Assurez-vous d'être dans le dossier du code frontend
    npm install
    ```
2.  **Démarrer l'application :**
    ```bash
    npm start # La commande peut varier selon le framework (e.g., vue serve)
    ```
## 7. Documentation des Endpoints API

L'API est accessible via `http://localhost:8080/api/`.

| Ressource | Méthode | Route | Description |
| :--- | :--- | :--- | :--- |
| **Listes** | `GET` | `/task-lists` | Liste toutes les listes de tâches. |
| **Listes** | `POST` | `/task-lists` | Crée une nouvelle liste de tâches. |
| **Listes** | `GET` | `/task-lists/{id}` | Récupère une liste spécifique. |
| **Listes** | `PUT` | `/task-lists/{id}` | Met à jour une liste spécifique. |
| **Listes** | `DELETE` | `/task-lists/{id}` | Supprime une liste spécifique. |
| **Tâches** | `GET` | `/task-lists/{listId}/tasks` | Liste toutes les tâches pour une liste donnée. |
| **Tâches** | `POST` | `/task-lists/{listId}/tasks` | Crée une tâche dans la liste spécifiée. |
| **Tâches** | `PUT` | `/task-lists/{listId}/tasks/{taskId}` | Met à jour une tâche spécifique. |
| **Tâches** | `DELETE` | `/task-lists/{listId}/tasks/{taskId}` | Supprime une tâche spécifique. |
---
## 9. Auteur & Licence

* **Auteur :** Mariem Mhadhbii ([MariemMhadhbii](https://github.com/MariemMhadhbii))
