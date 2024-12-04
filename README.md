# README pour le Backend - Recette API

## Description

Ce projet backend est développé avec **Express.js** pour gérer les recettes via une API RESTful. Il permet la gestion des recettes avec des fonctionnalités CRUD (Create, Read, Update, Delete) et est connecté à une base de données **MySQL**.

## Diagramme de Classes

![Diagramme de Classes](./src/assets/Diagramme%20de_Classe_des_Recettes.png)

## Prérequis

Avant de commencer, assurez-vous d'avoir installé les éléments suivants :

- [Node.js](https://nodejs.org) (version 14 ou supérieure)
- [npm](https://www.npmjs.com/) (Node Package Manager)
- [MySQL](https://www.mysql.com/)

## Installation

Suivez ces étapes pour configurer le projet sur votre machine locale :

1. Clonez le dépôt :

```bash
   git clone https://github.com/AssaBaradji/recipe_api_bakend.git
```

2.Accédez au répertoire du projet :

```bash
   cd recipe_api_bakend
```

3.Installez les dépendances :

```bash
   npm install
```

## Configuration de la Base de Données

1. Créez un fichier `.env` à la racine du projet en vous basant sur le fichier `.env.example` fourni. Ce fichier contient les variables d'environnement nécessaires pour configurer la connexion à la base de données MySQL.

2. Dans le fichier `/assets/script.sql`, vous trouverez toutes les commandes SQL nécessaires pour créer la base de données et les tables associées.

3. L'application se connecte automatiquement à la base de données en utilisant les variables d'environnement définies dans le fichier `.env`.

## Utilisation

1. Démarrez l'application avec la commande suivante :

```bash
   npm start
```

2.L'application sera disponible à l'adresse suivante : `http://localhost:3002`.

## Tests avec Postman

Une collection Postman est disponible dans le fichier `/assets/Recipe API.postman_collection.json` contenant des requêtes pour tester les différents endpoints de l'API.

## Endpoints de l'API

### Recette

1. **Récupérer une Recette par ID**

   - **Point de terminaison :** `GET /recipes/:id`
   - **Description :** Récupérer une seule recette par son ID.
   - **Réponse :** Objet recette ou une erreur 404 si non trouvé.

2.**Récupérer Toutes les Recettes**

- **Point de terminaison :** `GET /recipes`
- **Description :** Récupérer toutes les recettes de la base de données.
- **Réponse :** Tableau d'objets recette.

  3.**Créer une Nouvelle Recette**

- **Point de terminaison :** `POST /recipes`
- **Description :** Créer une nouvelle recette.
- **Corps de la requête :**

```json
{
  "id": 123,
  "title": "Titre de la Recette",
  "type": "Type de Recette",
  "ingredient": "Liste des Ingrédients",
  "category_id": "Nom de la catégorie"
}
```

- **Réponse :** Retourne l'ID de la recette nouvellement créée.

  4.**Mettre à Jour une Recette par ID**

- **Point de terminaison :** `PUT /recipes/:id`
- **Description :** Mettre à jour une recette existante par son ID.
- **Corps de la requête :**

```json
{
  "id": 123,
  "title": "Titre de la Recette",
  "type": "Type de Recette",
  "ingredient": "Liste des Ingrédients",
  "category_id": "Nom de la catégorie"
}
```

- **Réponse :** Confirmation de la mise à jour réussie ou une erreur 404 si non trouvé.

  5.**Supprimer une Recette par ID**

- **Point de terminaison :** `DELETE /recipes/:id`
- **Description :** Supprimer une recette par son ID.
- **Réponse :** Confirmation de la suppression réussie ou une erreur 404 si non trouvé.

### Categorie

1. **Récupérer une Categorie par ID**

   - **Point de terminaison :** `GET /categories/:id`
   - **Description :** Récupérer une seule Categorie par son ID.
   - **Réponse :** Objet Categorie ou une erreur 404 si non trouvé.

2.**Récupérer Toutes les Categories**

- **Point de terminaison :** `GET /categories`
- **Description :** Récupérer toutes les categories de la base de données.
- **Réponse :** Tableau d'objets categorie.

  3.**Créer une Nouvelle Categorie**

- **Point de terminaison :** `POST /categories`
- **Description :** Créer une nouvelle categorie.
- **Corps de la requête :**

```json
{
  "name": "nom de la Categorie"
}
```

- **Réponse :** Retourne l'ID de la categorie nouvellement créée.

  4.**Mettre à Jour une Categorie par ID**

- **Réponse :** Confirmation de la mise à jour réussie ou une erreur 404 si non trouvé.

  5.**Supprimer une Categorie par ID**

- **Point de terminaison :** `DELETE /categories/:id`
- **Description :** Supprimer une categorie par son ID.
- **Réponse :** Confirmation de la suppression réussie ou une erreur 404 si non trouvé.

## Tests Unitaires

Des tests unitaires sont disponibles pour vérifier que les actions CRUD fonctionnent correctement.

Exécutez les tests avec la commande suivante :

```bash
npm test
```

## Analyse de Code et Formatage

- **ESLint et Prettier sont intégrés :**

  - Exécutez ESLint pour analyser statiquement le code :

```bash
   npm run lint
```

- Exécutez Prettier pour formater automatiquement le code :

```bash
   npm run format
```

## Auteur

[Assa Baradji](https://github.com/AssaBaradji)
