# **Les Formulaires**

## **Coté Client**
```php
<form action="page.php"
      method="GET"
      enctype="application/x-www-form-urlencoded">

   ...Divers champs de formulaire (input, checkbox, radios…)...

</form>

- action : définit OU (URL) sont envoyées les données(par défaut la page sur laquelle on se trouve),
- method : définit la méthode HTTP utilisée pour envoyer des données (GET par défaut ou POST)
- enctype : définit la méthode d'encodage des données (dans le cas d'UPLOAD il DOIT obligatoirement être "multipart/form-data")
```

Liste des champs du formulaire correspondant à un élément HTML spécifique : 
```php
https://www.w3schools.com/html/html_form_elements.asp

Un label doit obligatoirement être relié à son champ, via son attribut for et l’attribut id du champ. 

<label for="firstname">Firstname</label>
<input type="text"
       id="firstname"
       name="firstname"
       required
       placeholder="John"
       pattern="^[a-zA-Z][a-zA-Z0-9-_\.]{1,20}$"
       minlength="1"
       maxlength="20"
       size="10"
>
```
Une fois le  formulaire complété avec toutes les données requises, il faut que l’utilisateur puisse soumettre le formulaire et transmettre les données saisies.

```php
<form action="form.php" method="POST">
   <!-- différents champs (input, select, textarea...) -->

   <button>Submit</button>
   <!-- ou -->
   <input type="submit" value="Submit" name="submit"/>
</form>
//Lorsque l’utilisateur appuie sur le bouton, le formulaire est soumis.
//Une requête HTTP (GET ou POST en fonction de la method définie) est envoyée par le client (ici le navigateur) vers la ressource sur le serveur, inscrite dans l’attribut action (ici form.php ou '' par défaut). 
```
### **Restrictions :** 

- Il n’est pas possible d’imbriquer une balise <form> dans une autre balise <form>
- Tout champ en dehors d’une balise <form> ne peut pas être associé à celui-ci. 
Ex. : Si le <submit> est en dehors du form, il sera alors impossible de soumettre le <form> en cliquant dessus.
Cependant: Depuis HTML5 il est possible de renseigner l'attribut form avec l'ID du 
<form id="myForm">...</form> sur un <button form="myForm"> 
en dehors du formulaire afin de le soumettre.
Ex. : Si un formulaire est soumis, les données saisies dans des champs en dehors de la balise <form> ne seront pas envoyées.
- Si la page contient plusieurs formulaires, on ne peut en soumettre qu'un seul à la fois.

### **Validations :** 

```php
<input type="email" required>
<input type="number" min="0" max="100">
```
Le but est uniquement de faciliter l'usage du formulaire par le client (UX). C'est important et ça doit être fait.
MAIS cela n'apporte aucune sécurisation des données seule la validation côté serveur apporte une véritable sécurisation > Priorité

## **Coté Serveur**

Pour un formulaire, on utilise les méthodes HTTP GET ou POST.
Il en existe d’autres (DELETE, PUT, PATCH) mais non utilisables dans un formulaire HTML

- GET : Envoie les données saisies dans l’URL dans un format spécifique appelé Query String : 	

		index.php?firstname=jack&status=passenger 
        (Limitation à 3000 caractères. 
        Ne pas utiliser avec des données sensibles car elle sont conservées dans l'historique navigateur.)

- POST : Envoie les données saisies dans le corps de la requête HTTP
Pour tout autre cas de figure, notamment upload de fichiers.
Pas de limitation théorique de taille. Invisible dans l’URL.

### **Lecture des données**
Variables SUPERGLOBALES à traiter en php :

- $_GET[] : contient toutes les valeurs saisies envoyées avec la méthode GET via l’url.
- $_POST[ ] : contient toutes les valeurs saisies envoyées avec la méthode POST.
- $_REQUEST[ ] : contient les infos des deux précédents
- $_FILES[ ] : Les données concernant un fichier

Exemple : 
```php
<?php
$firstname = $_GET['firstname'];
$firstname = $_POST['firstname'];
```
La superglobale $_GET/POST contiendra alors une clé ‘firstname’ qui est définie par la clé firstname de la querystring, elle même générée car il y a un attribut name="firstname" dans le champ du formulaire

### **Restrictions**

- Le temps : de base PHP coupe son exécution après 30 secondes de traitement 
(directive max_execution_time du php.ini)
- Le poids : de base le poids maximum du POST ne doit pas dépasser 8M et 2M pour un fichier uploadé 
(post_max_size, upload_max_filesize)
- Le nombre d’éléments de formulaire : de base, “seulement” 1000 éléments sont autorisés.

## **Sécurisation**

### **Nettoyage**
Effectuer un trim() sur toutes les données provenant de l'utilisateur (avant toute autre validation).
```php
foreach($_POST as $key=>$value) {
   $data[$key] = trim($value);
}
// or
$data = array_map('trim', $_POST);
```
### **Validations**

Les données (surtout lorsqu'elle vont être stockées dans une base) sont ce qu'il y a de plus important dans une application. 

Types de validations possible : 
- requis ou non :  emtpy()
- longueur max d'une chaîne : strlen()
- correspond à une valeur parmi un choix restreint : in_array()
- format (email, url…) :  filter_var()
- valeur supérieure/inférieure à…      
- date supérieure/inférieure à…  
...

Ces validations doivent être réalisées de manière systématique, minutieuse, pour tous types de données (formulaire, query string) provenant d'un utilisateur.

Exemple : 
```php 
// cleaning : Données nettoyées via trim()
$data = array_map('trim', $_POST);
$errors = [];

// validation : Validation exhaustive de toutes les données.
if (empty($data['firstname'])) {
   $errors[] = 'The firstname is mandatory';
}

if (strlen($data['firstname']) > 100) {
   $errors[] = 'The firstname length should be less than 100 characters';
}

if (!empty($errors)) {
  //S'il y a des erreurs, elles sont affichées et les données ne sont pas traitées
} else {
    //Sinon traitement (par ex INSERT en base de données) puis redirection (en GET, vide $_POST) et évite une seconde soumission accidentelle du formulaire.
   header('Location: /index.php');
}
```
La fonction filter_var($value, FILTER, FLAG)retournera false si la valeur passée en premier argument n’est pas acceptée par le filtre indiqué en deuxième paramètre. Certains filtres peuvent être complétés d’un drapeau (optionnel en 3e position).
 
Il est par exemple possible de :
• contrôler le format d’une adresse mail xxx@xxx.tld (FILTER_VALIDATE_EMAIL)
• contrôler le format d’une url http://xxxxx (FILTER_VALIDATE_URL) ⚠️
• convertir une chaîne de caractère en son équivalent booléen. (FILTER_VALIDATE_BOOLEAN)
```php
$email = "yoda@wildcodeschool-com";
if(!filter_var($email, FILTER_VALIDATE_EMAIL)){
  $errors[] = "L'adresse mail n’est pas au bon format.";
}
$website = "http:www.wildcodeschool.com";
if(!filter_var($website, FILTER_VALIDATE_URL){
  $errors[] = "Le format d'url n’est correct"; ⚠️
}
$send_me_newsletter = "yes";
var_dump(filter_var($send_me_newsletter, FILTER_VALIDATE_BOOLEAN));
// true
$remember_me = "forever";
var_dump(filter_var($remember_me, FILTER_VALIDATE_BOOLEAN, FILTER_NULL_ON_FAILURE));
// null
```

# **RESSOURCES SUPP**
- https://www.w3schools.com/htmL/html_form_elements.asp (Element HTML d'un form)
- https://developer.mozilla.org/fr/docs/Learn/Forms/Your_first_form (MDN Form)
- https://www.php.net/manual/fr/language.variables.superglobals (Variable Superglobales)
- https://assiste.com/Caracteres_interdits_dans_les_URLs.html (Caractères interdit dans une URL)
- https://fr.wikipedia.org/wiki/Post-redirect-get  (Wiki PRG)
- https://www.youtube.com/watch?v=576WwU7xlWU (Youtube HTML Get/Post)

- https://www.youtube.com/playlist?list=PLZU0qJlzY07VNsFwaORXKV_ka8urJjdQg (Youtube Validations)
- https://www.w3schools.com/php/php_form_url_email.asp (Validation W3s)
- https://www.w3schools.com/php/php_form_required.asp (Champs requis W3s)
- https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data#Common_security_concerns (MDN Get/Post/Security)
- https://evontech.com/component/easyblog/10-useful-javascript-form-validation-libraries.html (Validations utiles JS)
- https://www.html5pattern.com/ (Patern HTML pour Sécurisation)
- https://css-tricks.com/form-validation-part-1-constraint-validation-html/ (Contraintes validation coté Front end)