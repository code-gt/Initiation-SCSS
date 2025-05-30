# Atelier SCSS : Création d'une Page Web avec SCSS

## Introduction à SCSS

SCSS (Sassy CSS) est une extension de CSS qui permet d'utiliser des fonctionnalités avancées comme les variables, les mixins, et surtout l'imbrication. L'imbrication permet de structurer vos styles CSS de manière plus intuitive et lisible, en reflétant directement la hiérarchie du HTML. Cela rend le processus de stylisation plus efficace et maintenable.

CSS classique :

```css

article {
   width: 800px;
   background: #F6F6F6;
}

article h2 {
   color: #222;
   font-size: 18px;
}

article p {
   color : #444;
   font-size: 13px;
}
```

Le même code en SCSS avec le principe d'imbrication :

```scss
article {
  width: 800px;
  background: #F6F6F6;

  h2 {
    color: #222;
    font-size: 18px;
  }

  p {
    color: #444;
    font-size: 13px;
  }
}
```

## Installation de Live Sass Compiler

Pour compiler SCSS en CSS en temps réel dans Visual Studio Code, suivez ces étapes :

1. **Installer l'extension Live Sass Compiler** :
   - Ouvrez Visual Studio Code.
   - Allez dans l'onglet des extensions (ou utilisez le raccourci `Ctrl+Shift+X`).
   - Recherchez "Live Sass Compiler" et installez-le.

2. **Configurer Live Sass Compiler** :
   - Ouvrez un fichier SCSS dans VS Code.
   - Cliquez sur "Watch Sass" dans la barre d'état en bas de la fenêtre pour démarrer la compilation automatique de vos fichiers SCSS en CSS.

## Consignes pour le HTML

Utilisez les balises sémantiques suivantes pour structurer votre page :

- `<header>` pour l'en-tête de la page.
- `<article>` pour chaque section de contenu autonome.
- `<footer>` pour le pied de page.

Voici le texte à inclure dans votre HTML :

### Texte pour le HTML

- **Titre principal dans le header** : "Le Chat de Mistral"
- **Article 1** :
  - **Titre** : "Qui est Le Chat de Mistral ?"
  - **Paragraphe** : "Le Chat de Mistral est une application avancée d'intelligence artificielle développée pour interagir avec les utilisateurs de manière naturelle et intuitive."
  - **Image** : Utilisez une image aléatoire de picsum.photos : `https://picsum.photos/800/400?random=1`

- **Article 2** :
  - **Titre** : "Origines et Développement"
  - **Paragraphe** : "Le Chat de Mistral a été développé par Mistral AI, une startup française basée à Paris."
  - **Image** : Utilisez une image aléatoire de picsum.photos : `https://picsum.photos/800/400?random=2`

- **Article 3** :
  - **Titre** : "Avantages du Chat de Mistral"
  - **Paragraphe** : "Le Chat de Mistral offre plusieurs avantages, notamment sa capacité à comprendre le contexte des conversations."
  - **Image** : Utilisez une image aléatoire de picsum.photos : `https://picsum.photos/800/400?random=3`

- **Article 4** :
  - **Titre** : "Utilisation du Chat de Mistral"
  - **Paragraphe** : "Le Chat de Mistral peut être utilisé dans divers contextes, tels que l'assistance client, l'éducation, la recherche d'informations."
  - **Image** : Utilisez une image aléatoire de picsum.photos : `https://picsum.photos/800/400?random=4`

- **Footer** :
  - **Paragraphe** : "&copy; 2025 Code GT3D - Tous droits réservés"

## Consignes pour le SCSS

### Variables SCSS

Créez un fichier SCSS et définissez trois variables pour les couleurs et la taille de police :

- Une variable `$primary-color` pour la couleur primaire.
- Une variable `$secondary-color` pour la couleur secondaire.
- Une variable `$base-font-size` pour la taille de base de la police.

Exemple : 

```scss
$primary-color: #DD8734;

h2 {
    color: $primary-color;
}
```

Utilisez les propriétés SCSS suivantes pour styliser votre page en utilisant au maximum les variables créées :

- Un `header` avec un arrière-plan de couleur primaire, du padding, et le texte centré.
- Des `article` de largeur fixe, avec margin et padding, et un `border-bottom` pour séparer les différents articles
- Des titres `h2` de couleur primaire.
- Un `footer` fixe avec une largeur de 100%, le texte centré, et un arrière-plan avec la couleur primaire foncée de 20%.
- Des images centrées avec une largeur maximale de 100%.

Ajouter un maximum de SCSS à votre projet pour tester le fonctionnement de l'imbrication et les variables. 

### Mixin SCSS

Une mixin est un morceau de code paramétrable et réutilisable n’importe où dans votre fichier SCSS. Comme pour une fonction, une mixin peut prendre des paramètres. Utiliser un mixin pour générer des boutons sur votre page html. 

- Définition du **Mixin** : Le mixin `button-styles` est défini pour prendre une couleur d'arrière-plan en paramètre. Il applique des styles communs pour les boutons, comme le padding, la couleur de texte, et un effet de survol qui assombrit la couleur de fond.

- Utilisation du **Mixin** : Vous pouvez inclure ce mixin dans vos styles pour différents boutons. Par exemple, `.button` utilise le mixin avec la couleur primaire, et `.secondary-button` utilise le mixin avec la couleur secondaire.  


```scss

@mixin button-styles($bg-color) {
    // code

  &:hover {
    // code
  }
}

// Utilisation du mixin dans vos styles
.button {
  @include button-styles($primary-color);
}

.secondary-button {
  @include button-styles($secondary-color);
}
```


