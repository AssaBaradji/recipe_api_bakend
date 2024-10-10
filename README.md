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

1. Connectez-vous à MySQL :

```bash
   mysql -u root -p
```

2.Exécutez les commandes dans le fichier `/assets/script.sql` pour créer la base de données et les tables.

3.Modifiez les informations d'identification dans `/config/db.js` :

```javascript
{
  user: "votre_nom_utilisateur",
  password: "votre_mot_de_passe",
  database: "votre_nom_de_base_de_données",
}
```

## Utilisation

Pour démarrer le serveur backend, exécutez :

```bash
npm start
```

## Tests avec Postman

Importez la collection Postman incluse pour tester facilement les endpoints.

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
  "title": "Titre de la Recette",
  "type": "Type de Recette",
  "ingredient": "Liste des Ingrédients",
  "category_id": "ID de la catégorie"
}
```

- **Réponse :** Retourne l'ID de la recette nouvellement créée.

  4.**Mettre à Jour une Recette par ID**

- **Point de terminaison :** `PUT /recipes/:id`
- **Description :** Mettre à jour une recette existante par son ID.
- **Corps de la requête :**

```json
{
  "title": "Titre Mis à Jour",
  "type": "Type de Recette Mis à Jour",
  "ingredient": "Liste des Ingrédients Mise à Jour",
  "category_id": "ID de la catégorie Mis à jour"
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

Pour exécuter les tests unitaires :

```bash
npm test
```

## Analyse de Code et Formatage

### Linting et Formatage

- Pour exécuter ESLint :

```bash
   npm run lint
```

- Pour formater le code avec Prettier :

```bash
   npm run format
```

## Auteur

[Assa Baradji](https://github.com/AssaBaradji)
