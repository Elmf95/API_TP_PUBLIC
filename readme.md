# TP 2 - Requêter une API publique

## Objectif
Ce TP consiste à utiliser **Postman** pour effectuer des requêtes HTTP sur une API publique.

---

## API utilisée
- **Base URL** : `https://jsonplaceholder.typicode.com`

---

## Requêtes

### 1. Requête GET sur les comments
- **Méthode** : `GET`
- **URL** : `https://jsonplaceholder.typicode.com/comments`
- **Étapes dans Postman** :
  1. Créer une nouvelle requête.
  2. Sélectionner `GET` comme méthode.
  3. Entrer l'URL : `https://jsonplaceholder.typicode.com/comments`.
  4. Cliquer sur "Send".
- **Résultat attendu** :
  ```json
  [
    {
      "postId": 1,
      "id": 1,
      "name": "Commentateur 1",
      "email": "comment1@example.com",
      "body": "Ceci est un commentaire."
    },
    {
      "postId": 1,
      "id": 2,
      "name": "Commentateur 2",
      "email": "comment2@example.com",
      "body": "Ceci est un autre commentaire."
    }
  ]
---

### 2. Requête POST sur les todos
- **Méthode** : `POST`
- **URL** : `https://jsonplaceholder.typicode.com/todos`
- **Paramètres envoyés** (format `x-www-form-urlencoded`) :
  - `title`: `"Apprendre Postman"`
  - `completed`: `false`
  - `userId`: `1`

- **Étapes dans Postman** :
  1. Créer une nouvelle requête.
  2. Sélectionner `POST` comme méthode.
  3. Entrer l'URL : `https://jsonplaceholder.typicode.com/todos`.
  4. Aller dans l'onglet `Body`.
  5. Sélectionner `x-www-form-urlencoded`.
  6. Ajouter les champs :
     - `title`: `"Apprendre Postman"`
     - `completed`: `false`
     - `userId`: `1`
  7. Cliquer sur "Send".

- **Résultat attendu** :
  ```json
  {
    "title": "Apprendre Postman",
    "completed": false,
    "userId": 1,
    "id": 201
  }

---

### 3. Requête PATCH sur les posts
- **Méthode** : `PATCH`
- **URL** : `https://jsonplaceholder.typicode.com/posts/1`
- **Paramètres envoyés** (format `raw` en JSON) :
  ```json
  {
    "title": "Titre mis à jour",
    "body": "Contenu mis à jour"
  }
  
---

### 4. Requête GET pour les commentaires du post ID 1
- **Méthode** : `GET`
- **URL** : `https://jsonplaceholder.typicode.com/posts/1/comments`
- **Étapes dans Postman** :
  1. Créer une nouvelle requête.
  2. Sélectionner `GET` comme méthode.
  3. Entrer l'URL : `https://jsonplaceholder.typicode.com/posts/1/comments`.
  4. Cliquer sur "Send".
- **Résultat attendu** :
  ```json
  [
    {
      "postId": 1,
      "id": 1,
      "name": "Commentateur 1",
      "email": "comment1@example.com",
      "body": "Ceci est un commentaire."
    },
    {
      "postId": 1,
      "id": 2,
      "name": "Commentateur 2",
      "email": "comment2@example.com",
      "body": "Ceci est un autre commentaire."
    }
  ]

---

### 5. Requête GET pour les photos de l’album numéro 2
- **Méthode** : `GET`
- **URL** : `https://jsonplaceholder.typicode.com/albums/2/photos`
- **Étapes dans Postman** :
  1. Créer une nouvelle requête.
  2. Sélectionner `GET` comme méthode.
  3. Entrer l'URL : `https://jsonplaceholder.typicode.com/albums/2/photos`.
  4. Cliquer sur "Send".
- **Résultat attendu** : Une liste de photos affiliées à l’album numéro 2.
  ```json
  [
    {
      "albumId": 2,
      "id": 51,
      "title": "Photo 1 de l'album 2",
      "url": "https://via.placeholder.com/600/92c952",
      "thumbnailUrl": "https://via.placeholder.com/150/92c952"
    },
    {
      "albumId": 2,
      "id": 52,
      "title": "Photo 2 de l'album 2",
      "url": "https://via.placeholder.com/600/771796",
      "thumbnailUrl": "https://via.placeholder.com/150/771796"
    }
  ]
