données primitifs (immuables) :

- Boolean
- String
- Number
- Null
- Undefined

Les autres (mutables) :

- Object
- Function

## **Typeof**

permet de voir le type de données d'une valeur.
Ecrire typeof() et mettre la valeur que nous voulons vérifier entre les parenthèses.

```javascript
typeof 1;
```

Résultat "number" car la valeur 1 est un nombre.

## **Deux types de données**

En JS il existe neuf types de données différents. Ils sont classés en deux catégories :
**Primitifs** et **non-primitifs**.

### **Les types primitifs**

Types de données primitifs correspondent à des valeurs qui ne peuvent pas changer (nous disons généralement qu'elles sont immuables).

#### **Boolean**

Les booléens sont utilisés pour représenter le vrai (true) ou le faux (false).

```javascript
typeof true;
// "boolean"
```

#### **String**

Une "String" est une chaîne (suite) de caractères. Les chaînes sont toujours entourées de guillemets doubles ("") ou simples ('') .

```javascript
typeof "Hello, World !";
// "string"
```

#### _Number_

Les nombres sont une représentation d'un nombre entier ou décimal.

```javascript
typeof 1234;
// "number"
typeof 12.54;
// "number"
```

#### _Null_

La valeur null est utilisée pour représenter une absence intentionnelle de valeur.

Si tu utilises typeof avec null, tu verras que le type de null est "object" ;

C'est une erreur qui a été implémentée dans l'ECMAScript depuis le début et ne peut plus être corrigée de nos jours.

```javascript
let empty = null;
typeof empty;
// "object"
```

#### _Undefined_

undefined est la valeur par défaut d'une variable qui existe (car elle est déclarée) mais qui n'a pas encore de valeur (car elle n'a pas été initialisée/assignée).

```javascript
let notDefined;
typeof notDefined;
// "undefined"
```

Attention si la variable n'est pas définie cest different

```javascript
typeof nothing;
// ReferenceError: nothing is not defined
```

Et la cest **FATAL ERROR**

### **Types complexes (non-primitifs)**

Les valeurs non primitives sont des valeurs qui peuvent changer (on dit qu'elles sont mutables).

#### **Function**

Une fonction est un bloc de code utilisé pour exécuter un ensemble d'instructions.

On peut exécuter (invoquer) une fonction en écrivant son nom suivi de parenthèses.

```javascript
typeof console.log;
// "function"
```

#### **Object**

"boîtes" qui peuvent contenir des clés associées à des valeurs

Ces paires "clé/valeur" sont entourés d'accolades pour délimiter l'objet décrit.

Les valeurs contenues dans un objet peuvent être de n'importe quel type, cela peut même être des fonctions ! Une fonction contenue dans un objet sera appelée "méthode".

```javascript
const person = {
  name: "Bob",
  age: 25,
  sayHello: function () {
    console.log("Hello");
  },
};

person.sayHello();
// "Hello"

typeof person;
// "object"
```

#### **Objets particuliers**

- **Array**

Les Arrays sont utilisés pour stocker plusieurs valeurs au sein d'une **même variable**.

```javascript
const colors = ["Red", "Blue", "Yellow"];
typeof colors;
// "object"
```
