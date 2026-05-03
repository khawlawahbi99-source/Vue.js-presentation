# Todo App – Vue.js

Une application Todo simple développée avec Vue.js.

---

## Fichiers importants

### Présentation
Le fichier `presentation.pptx` contient les slides de présentation du projet,
incluant l'architecture, les composants Vue utilisés et les fonctionnalités de l'application.

### Explication du code
Le fichier `explication du code.pdf` détaille le fonctionnement du code source,
avec des explications sur chaque composant et la logique de l'application.

---

## Structure du projet

Le dossier `src` contient l'ensemble du code source de l'application :

- `components/` : les composants Vue réutilisables de l'application
  - `TodoForm.vue` : le formulaire permettant d'ajouter une nouvelle tâche
  - `TodoItem.vue` : le composant représentant une tâche individuelle
  - `TodoList.vue` : le composant affichant la liste complète des tâches
- `App.vue` : le composant racine qui regroupe tous les composants de l'application
- `main.js` : le point d'entrée de l'application, initialise Vue et monte l'application

---

## Technologies utilisées

- Vue.js
- Vite
- JavaScript / HTML / CSS

---
## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
