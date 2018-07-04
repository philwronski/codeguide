---
title: "SASS"
---

## SASS

### Structurer le code
Aujourd'hui avec les nombreux frameworks front orientés composants, il est parfois compliquer de structurer sont code correctement et d'appliquer le DRY (Dont repeat yourself). Pour les projets de ce type, il est recommander d'avoir une structure similaire à celle ci-dessous.

```
+-- sass
|   +-- _config
|   |   +-- _variables.scss
|   |   +-- _breakpoints.scss
|   |   +-- _mixin.scss
|   |   +-- _function.scss
|   |
|   +-- _fonts
|   +-- _library
|   |   +-- _reset.scss
|   |   +-- _base.scss
|   |   +-- _layout.scss
|   |   +-- _grid.scss
|   |   +-- _utilities.css
|   |
|   +-- _core.scss
|   +-- app.scss
```

Ici, le fichier `app.scss` contient l'ensemble du code hors composants. le fichier `_core.scss` servira de base à chaque composant.

Il est recommandé d'avoir un fichier `.scss` par composant. Celui-ci commence de la façon suivante:
```scss
/* --------------- */
/* Composant XXXX  */
/* --------------- */

/*
 * Description du composant...
 */

@import 'sass/core';

...

```

