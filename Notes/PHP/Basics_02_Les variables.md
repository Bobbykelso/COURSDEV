# **Variable en PHP**

## **Les règles associées au nom des variables**

**Une Variable:**

- commence toujours par $
- contien uniquement des chiffres, des lettres, et des "\_".
- ne peut pas commencer par des chiffres

* s'écrit en camelCase
* est en anglais
* doit décrire au maximum ce qu'elle est

* une variable est sensible a la casse

✅ Exemples de noms de variables valides :

```php
$str
$my_value
$_old
$theBestValue
```

❌ Exemples de noms de variables invalides :

```php
$4days            // commence par un chiffre
day4              // pas de symbole $
$my-bad           // contient un caractère interdit (-)
$                 // pas de nom
$name@domain      // caractère interdit (@)
$first name       // caractère interdit ( )
```

## **Les types de variables**

Le PHP est un language de typage faible CAD que cest le contenu de la variable qui définit le type de variable.
PHP est assez souple sur le typage des variables.

Il y a deux familles de types de données :

- **scalaire** :

  - integer (entier)
  - float (réel)
  - Boolean ( true false)
  - String (chaine de caractére)

- **composé** :
  - Array (tableau)
  - Object (objet)

* **Types spéciaux**:

  - ressources (fichier, connexion a bose de données)
  - NULL (variable sans valeur)

  Lorsque l'on souhaite créer une variable, on parle de déclaration.
  Lorsque l'on souhaite lui attribuer (ou modifier) une valeur, il faut utiliser l'opérateur d'affectation =. On parle donc d'affectation.
  À la première déclaration de la variable, on parle d'initialisation et on affecte une valeur à cette variable.

## **Variable scope**

Une variable existe sur tout le code en dessous d'elle mais pas dans les fonctions

```php
<?php

$total = 0;
// $total est accessible ici

function add() {
    $note1 = 15;     // $total n'est pas accessible ici
    $note2 = 20;
}

// $total est accessible ici aussi
// $notes1 et $notes2 ne sont pas accessibles ici
```
