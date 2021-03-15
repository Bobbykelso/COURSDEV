## **Les opérateurs conditionnels**

### **si...sinon**

"if...else".

if permet de vérifier une condition (précisée entre les parenthèses); si la **condition est évaluée comme vraie**, le code est alors exécuté.

```javascript
if (condition) {
  // Do something if the condition is true
} else {
  // Do something if the condition is false
}
```

- exemple:

```javascript
const name = "Paul";

if (name === "Paul") {
  console.log("Welcome, Paul");
} else {
  console.log("Go away!");
}
```

Dans cet exemple, on créé d'abord une variable name et on lui attribue la valeur "Paul ".

Ensuite, on compare la valeur assignée à cette variable avec la chaîne "Paul".
Si le résultat est vrai, alors on affiche "Welcome, Paul " sinon on affiche "Go away!".

_Attention, Javascript est sensible à la casse. Ce qui signifie que "Paul" n'est pas équivalent à "paul" !_

#### **Prompt**

prompt est une fonction qui va afficher une boite de dialogue permettant à l'utilisateur d'entrer du texte.

```javascript
const userName = prompt("What's your name?");
console.log(userName);
```

Tu verras ensuite le texte entré dans la boîte de dialogue s'afficher dans la console.

#### **Utiliser prompt avec des nombres**

Lors de l'utilisation de prompt, ce que l'utilisateur va taper dans la fenêtre de l'invite sera considéré comme une chaîne de caractères.
Si tu veux travailler avec des nombres, tu dois convertir la chaîne de caractères en un nombre. Pour cela, tu peux utiliser la fonction **parseInt**.

```javascript
const age = prompt("How old are you?");
console.log(typeof age);
// String

const ageNumber = parseInt(age);
console.log(typeof ageNumber);
// Number
```

### **Else if**

ajouter des "embranchements" pour traiter plus de cas avec else if

else if devrait être écrit après un if et avant un else, et doit contenir une condition entre parenthèses.

```javascript
else if (condition) {
  // ...
}

```

### \*\*Conditions imbriquées

On peut tout à fait avoir des conditions à l'intérieur de conditions, par exemple si on souhaite demander à l'utilisateur son nom, puis son mot de passe dans un deuxième temps; après avoir vérifié son nom.

Exemple:

```javascript
const userName = prompt("What's your name?");

if (userName === "Bob") {
  const userAge = prompt("What's your age?");
  if (parseInt(userAge) === 30) {
    console.log("Welcome");
  } else {
    console.log("Go Away!");
  }
} else {
  console.log("Go Away!");
}
```

### **Les valeurs "truthy" et "falsy"**

Lorsque tu écris un bloc if...else, l'expression que tu écris entre parenthèses est évaluée et transformée en booléen.

Par exemple, l'expression 4 === 4 est évaluée comme ("transformée" en) true. Si on place cette dernière dans les parenthèses d'un if, le code sous condition sera exécuté.

- Certaines valeurs sont dites "thruthy" : elle seront évaluées comme étant vraies (true).
- D'autres sont "falsy" et seront évaluées comme étant fausses (false).
  Les valeurs dites "falsy" :

- false
- ""
- 0
- -0
- null
- undefined
- NaN

Toutes les autres valeurs sont "truthy" !

Exemple

```javascript
let myName = "";
if (myName) {
  console.log("Hello you!");
  // This will never be run because "empty string" is evaluated as false
} else {
  console.log("you don't have a name");
}
```

Ici, puisque la variable myName est une chaîne vide , la condition est évaluée comme false.

### **Inversion logique**

L'opérateur **!** permet d'inverser un booléen. Ainsi, !false est égal à true et !true est égal à false. Cet opérateur permet d'obtenir l'opposé d'une valeur.
Si on veut évaluer l'opposé logique d'une valeur, on peut utiliser le !.
Par exemple, !true vaut false et !false vaut true.

### **et / ou**

Dans une condition, on peut aussi déterminer la véracité d'une combinaison logique de plusieurs expressions en utilisant les mots-clés **&&**("and") et **||** ("or").

### **Switch**

On peut également utiliser la structure switch...case pour évaluer une condition. Voici un exemple :

```javascript
let userCountry = prompt("Where are you from");

switch (userCountry) {
  case "France":
    console.log("Bonjour");
    break;
  case "England":
    console.log("Hello");
    break;
  case "Germany":
    console.log("Hallo");
    break;
  case "Italy":
    console.log("Ciao");
    break;
  case "Spain":
    console.log("Hola");
    break;
  default:
    console.log("Hey there");
    break;
}
```

On vérifie le pays d'origine de l'utilisateur et, en fonction de ce dernier, on affiche un message spécifique. Dans les parenthèses du switch, on met la valeur à comparer (avec l'opérateur d'égalité stricte) avec différents cas (case) possibles.

_N'oublie surtout pas de rajouter des break; pour marquer la fin du traitement de tes différents cas_

Le mot clé default sert à spécifier quoi faire si aucun des cas n'est égal à la valeur testée.

_"switch" peut être utilisé uniquement si on souhaite tester l'égalité d'une seule valeur avec plusieurs autres valeurs pré-définies. Cette structure peut permettre de gagner un peu en lisibilité, mais elle est moins puissante que "if...else if...else"._

```javascript
const today = new Date().getDay();
console.log(today);

// Use the switch statement here
switch (today) {
  case 0:
    console.log("Dimanche");
    break;
  case 1:
    console.log("Lundi");
    break;
  case 2:
    console.log("Mardi");
    break;
  case 3:
    console.log("Mercredi");
    break;
  case 4:
    console.log("jeudi");
    break;
  case 5:
    console.log("vendredi");
    break;
  case 6:
    console.log("Samedi");
    break;
}
```

### **Les ternaires**

On peut simplifier l'écriture d'une condition en utilisant l'opérateur ternaire.
Cet opérateur utilise ? et :, respectivement équivalents à if et else :

```javascript
name === "Bob" ? console.log("Hello, Bob") : console.log("Go Away!");
```

_Une utilisation abusive ou non approprié de l'opérateur ternaire peut également rendre ton code moins lisible et compréhensible._

### **Portée (scope) / Contexte**

le contexte est très important : on ne peut pas utiliser une variable déclarée à l'intérieur d'une condition en dehors de cette dernière.

Les accolades { } définissent un contexte local.
