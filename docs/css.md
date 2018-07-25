---
title: "CSS"
---

# CSS

Les styles doivent toujours être dans un fichier spécifique. Ne jamais ajouter de balise ou d'attribut `style` dans le code HTML.

## Synthaxe
- Utiliser une tabulation à 2 espaces.
- Une ligne par sélecteurs lors d'un groupement de sélecteurs.
- Ajouter un espace avant chaque ouverture de bloc.
- Les accolades fermantes sont sur une nouvelle ligne.
- Ajouter un espace apres les `:` de chaque propriété.
- Une ligne par propriété.
- Ajouter un espace apres chaque valeur de propriété séparée d'une virgule. (ex: box-shadow)
- Ne pas ajouter d'espace apres chaque valeur de fonction tel que `rgba()`.
- Ne pas préfixer par 0 les valeur décimal inférieure à 1 (ex: .5 à la place de 0.5).
- Les code couleur sont en héxadécimal et en minuscule.
- Ne pas préciser l'unité quand une propriété à pour valeur 0.
- Ajouter une nouvelle ligne aprés chaque bloc.

```css
/* KO */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* OK */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

## Ordre des déclarations
Pour garder une cohérence d'ensemble et avoir une lecture simplifié du code, ranger les propriétés dans l'ordre suivante:
1. Positionnement
2. Modèle de boite
3. Typographie
4. Effets visuels (couleur, fond, bordure)
5. le reste...

```css
.declaration-order {
  /* Positionnement */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Modèle de boite */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typographie */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Effets visuels */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Le reste... */
  opacity: 1;
}
```

## Utilisation des Media query
Placer les media query dans chaque bloc/règle au lieu de regrouper le tout.

```css
/* KO */
.element { ... }
.element-avatar { ... }
.element-selected { ... }

@media (min-width: 480px) {
  .element { ...}
  .element-avatar { ... }
  .element-selected { ... }
}

/* OK */
.element { 
  @media (min-width: 480px) { }
}
.element-avatar {
  @media (min-width: 480px) { }
}
.element-selected {
  @media (min-width: 480px) { }
}
```

## Préfixer les proriétés
Il est recommandé de préfixer les propriétés pour disposer d'une compatibilité maximal pour chaque navigateur. Il est préférable de laisser des outils telque postcss ou les IDE le faire à votre place.

Pour une question de lisibilité, aligner verticalement les propriétés.

```css
.selector {
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,.15);
          box-shadow: 0 1px 2px rgba(0,0,0,.15);
}
```

## Les déclarations simple
Il arrive par fois qu'un sélecteur ne dispose que d'une propriété. Dans ce cas et uniquement dans ce cas, il est recommander de supprimer les retour à la ligne.

```css
/* Simple déclarations */
.span1 { width: 60px; }
.span2 { width: 140px; }
.span3 { width: 220px; }

/* Multiple déclarations */
.sprite {
  display: inline-block;
  width: 16px;
  height: 15px;
  background-image: url(../img/sprite.png);
}
```

## Propriété abrégée
Lors de l'utilisation des propriétés suivantes, il est recommandé d'utiliser leur version abrégée pour fixer leurs différentes valeurs.
- padding
- margin
- font
- background
- border
- border-radius

```css
/* KO */
.element {
  margin: 0 0 10px;
  background: red;
  background: url("image.jpg");
  border-radius: 3px 3px 0 0;
}

/* OK */
.element {
  margin-bottom: 10px;
  background-color: red;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
```

## Commentaires

Il ne faut pas hésiter à ajouter des commentaires dans le CSS pour expliquer le pourquoi du comment. Comme tout autre code, s'il n'est pas commenté, le css peut s'avérer difficile à comprendre.

```css
/* KO */
/* Modal header */
.modal-header {
  ...
}

/* OK */
/* Wrapping element for .modal-title and .modal-close */
.modal-header {
  ...
}
```

## Nommage des classes et sélecteurs
- Toujours nommer les classes en minuscules et utiliser des tirets (celui ci `-` :D) pour la séparation des mots/termes.
- Utiliser le double tiret pour les classes de changement d'état. (ex: `.btn--danger`)
- Le BEM permet de nommer correctement les classes peut parfois être lourd à gérer. Dans ce cas privilégier SMACSS (https://smacss.com/)
- Utiliser les class plus tot que les tag d'éléments ou les sélecteurs d'attribut.

## Reset
Le `reset.css` est un fichier de style qui a pour but d'aligner le comportement des navigateurs au niveau de l'affichage des éléments standard HTML. Avec un comportement identique sur chaque navigateur, il est plus facile de créer un théme compatible multi-navigateur sans ajouter de hack.

Il est fortement conseillé d'avoir un `reset.css` au début d'un théme css. Les 2 `reset.css` les plus connu sont:
- Normalize.css https://necolas.github.io/normalize.css/
- Reboot https://getbootstrap.com/docs/4.1/content/reboot/