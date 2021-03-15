# **String ou chaine de caractères**

## **Définir une chaine de caractère**

En PHP une chaine de caractère se définit en l'encadrant de "" ou de ''.

Si la string comporte deja une ' mettre un / avant pour echapper le caractère ou utiliser ""

```php
echo 'J\'aime porter un chapeau'; // affiche : J'aime porter un chapeau
echo "J'aime porter un chapeau"; // affiche la même chose, pas besoin d'échapper une simple quote dans des doubles quotes et vice versa
```

On peut enregister une string dans une variable car ce sont des données.
ATTENTION: une string s'ecrit avec des guillemet mais si on appelle la variable on ne met pas de guillemet autour

```php
$firstname = 'Indiana';
$presentation = 'Indiana Jones est un célèbre archéologue';

echo $firstname; // affiche : Indiana

echo '$firstname'; // affiche : $firstname
```

mettre en priorité les pour les chaines simple(une string) ''
mettre en priorité les pour les chaines complexe ""

### **concaténer**

on utilise un . en php

Ensuite 2 possibilité décriture

```php
$fullname = $firstname . ' ' . $lastname; // le résultat d'une concaténation peut aussi être enregistré dans une variable.
echo $fullname; // affiche : Indiana Jones


$presentation = "$firstname $lastname est un célèbre archéologue"; // les variables sont interprétées
echo $presentation; // affiche : Indiana Jones est un célèbre archéologue
```

Uniquement utiliser la premiere car la seconde entraine des bugs a la lectures de longues phrases

**operateur de concaténation**

il est utiliser pour ajouter du texte avant et/ ou apres une string

```php
$film = $fullname . ' et le temple maudit';
echo $film; // affiche : Indiana Jones et le temple maudit;

$avis = 'Jaime bien regarder ' . $film;
echo $avis;  // affiche : J'aime bien regarder Indiana Jones et le temple maudit;
```

si on ajouter du texte a la fin d'une string tout en gardant la meme variable on utilise .=

```php
$name = 'Indiana';
$name .= ' Jones'; // équivalent à $name = $name . ' Jones';
echo $name; // affiche : Indiana Jones
```

## **Modulations simples**

On peut récupérer un élement en considérant la string comme un array soit

```php
$actor = 'Harrison Ford';
echo $actor[0]; // affiche 'H' car c'est le premier caractère de la chaîne $actor;
echo $actor[1]; // affiche 'a', le second caractère.
echo $actor[9]; // affiche 'F'
echo $actor[25]; // affiche une erreur car ce caractère n'existe pas dans la chaîne !
```

on peut aussi l'inversere

```php
$actor = 'Sean Connery';
echo $actor[-1]; // affiche 'y' car c'est le dernier caractère de la chaîne
echo $actor[-7]; // affiche 'C' car c'est le septième caractère de la chaîne en partant de la fin
echo $actor[-25]; // affiche une erreur car ce caractère n'existe pas dans la chaîne !
```

## **liste des fonctions native pour les String**

PHP possède beaucoups de fonction native :

- cest une liste de la plupart de ces fonctions

https://www.php.net/manual/fr/ref.strings.php

## **Quelques une des fonctions les plus utilisé**

- strlen() permet de connaitre la taille d'une chaine de caractère.

```php
$weapon = 'fouet';
$length = strlen($weapon); // vaut 5, car fouet contient 5 caractères;
```

- trim() ça vire les espaces et tabulation en début et fin de chaine.

on peut préciser juste debut ltrim() ou juste fin rtrim().

```php
$temple = ' maudit  ';
echo $temple; // affiche " maudit  "
echo trim($temple); //  affiche "maudit"
echo ltrim($temple); // affiche "maudit  ";
echo rtrim($temple); // affiche " maudit";
```

- strtoupper()

majuscule

- strtolower()

minuscule

- ucfirst()

premier caractère d'une chaine en majuscule

- ucwords()
  premier caractère de chaque mot est en majuscule

- str_replace()
  remplace tout ou une partie d'une chaine avec une autre chaine

```php
$text = 'Indiana Jones est un professeur';
echo str_replace('professeur', 'aventurier', $text); // affiche : "Indiana Jones est un aventurier"
echo str_replace('archéologue', 'aventurier', $text); // affiche : "Indiana Jones est un professeur" car le terme "archéologue" n'est pas présent dans $text
```

- explode et implode
  permet de convertir une string en array en fonction d'un délimiteur et implode l'inverse

```php
$team = 'Harrison Steven George';
$persons = explode(' ', $team);
// la chaîne $team a été explosée en fonction du délimiteur 'espace', en un tableau contenant ['Harrison', 'Steven', 'George'].
// le caractère délimiteur 'espace' n'est plus présent dans le tableau obtenu.
// Pour utiliser explode(), le délimiteur est un paramètre obligatoire.

echo implode (',', $persons);
// implode prend en paramètres un délimiteur et un tableau.
// affiche "Harrison,Steven,George". Une chaîne est créée à partir des chaînes contenues dans le tableau, et le délimiteur (ici la virgule) est placé entre chaque élément du tableau.
// pour utiliser implode(), le délimiteur est un paramètre optionnel
echo implode($persons); // affiche "HarrisonStevenGeorge".
```
