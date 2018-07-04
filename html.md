---
title: "HTML"
---

### Ordre des attributs
Pour facilité la lecture du code, il est recommander d'écrire les attributs dans l'ordre suivant:
- class
- id, name
- data-*
- src, for, type, href, value
- title, alt
- role, aria-*
- attributs liés au framework web

### Attributs de type boolean
HTML5 ne force pas la déclaration d'une valeur pour les attribut de type boolean. Le code est ainsi allégé et plus lisible.

```html
<!-- KO -->
<input type="text" disabled="true">

<!-- OK -->
<input type="text" disabled>

### Alléger la structure
Il arrive parfois que le code html soit dense et qu'il y ai des balises superflues. Il est recommander d'écrire du html de la façon la plus légère possible pour facilité sa compression par les navigateurs.

```html
<!-- KO -->
<span class="avatar">
  <img src="...">
</span>
<h1>
    <span>Titre</span><span>Sous-titre</span>
</h1>

<!-- OK -->
<img class="avatar" src="...">
<h1>
    Titre<small>Sous-titre</small>
</h1>

```