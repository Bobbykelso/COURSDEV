## **Les tableaux en JS**

### **quésaco un tableau**

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
```

Pour créer un tableau, utilise les crochets [ ] et écris à l'intérieur les éléments que tu veux.
Chaque élément doit être séparé par une virgule.

Un tableau peut contenir tout type de données : nombre, booléen, chaîne de caractères, objet, fonction ou d'autres tableaux.

```javascript
const myArray = ["Hello", 123, true, ["Hey", "Ho"]];
```

### **Accéder à un élément du tableau**

Pour accéder à un élément du tableau, tape le nom du tableau et la position de l'élément auquel tu veux accéder entre les crochets.

En JavaScript, le premier élément est toujours 0

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];

console.log(fruits[0]); // will print "Kiwi"

console.log(fruits[1]); // will print "Apple"

console.log(fruits[2]); // will print "Pineapple'
```

Tu peux également définir la valeur d'un élément spécifique dans un tableau

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
console.log(fruits[0]); // Will print "Kiwi"
console.log(fruits[1]); // Will print "Apple"
console.log(fruits[2]); // Will print "Pineapple'
fruits[0] = "Banana"; // Will change the first element to Banana
console.log(fruits[0]); // Will print "Banana"
```

### **Obtenir la longueur d'un tableau**

Pour obtenir la longueur d'un tableau, nous pouvons utiliser **array.length**.

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];

console.log(fruits.length); // will print 3
```

---

### **afficher tableaux ds console**

Va dans la console chrome et crée un tableau. Utilise console.log sur ce tableau pour l'afficher dans la console.

```javascript
console.log(["Kiwi", "Apple", "Pineapple"]);

// ⮀ (3) ["Kiwi", "Apple", "Pineapple"]
```

Clique sur la flèche, tu verras le détail des éléments qui se trouvent à l'intérieur de ton tableau.

```javascript
▼ (3) ["Kiwi", "Apple", "Pineapple"]
	0: "Kiwi"
	1: "Apple"
	2: "Pineapple"
	length: 3
    ⮀ __proto__: Array(0)
```

### **Ajouter un élément à un tableau**

- **push**

Il suffit d'exécuter la méthode push et de donner le nouvel élément comme argument :

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
fruits.push("Banana");
console.log(fruits);
// ["Kiwi", "Apple", "Pineapple", "Banana"]
```

Push ajoutera l'élément à la fin du tableau.

### **unshift**

Ajouter un élément au début du tableau.

    unshift

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
fruits.unshift("Strawberry");
console.log(fruits);
// ["Strawberry", "Kiwi", "Apple", "Pineapple"]
```

### **Supprimer un élément du tableau**

#### **Pop**

supprimer le dernier élément d'un tableau

pop

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
fruits.pop();
console.log(fruits);
// [ "Kiwi", "Apple" ]
```

#### **Shift**

supprimer le premier élément
shift

```javascript
fruits.shift();
console.log(fruits);
// [ "Kiwi" ]
```

#### **D'autres méthodes utiles**

- **concat**

concat (merge) fusionnera deux tableaux en un seul :

```javascript
const fruits1 = ["Apple", "Strawberry"];
const fruits2 = ["Banana", "Pineapple"];

const mySmoothie = fruits1.concat(fruits2);
console.log(mySmoothie);
```

On peut fusionner plusieur tableaux

```javascript
zodiacSigns = fireSigns.concat(earthSigns, waterSigns, airSigns);
```

ou tableau et valeur

```javascript
let nouveau_tableau = ancien_tableau.concat(valeur1[, valeur2[, ...[, valeurN]]])
```

- **Join**

join transformera ton tableau en une chaîne de caractères; tu peux également spécifier le caractère que tu souhaites utiliser comme séparateur.

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
const fruitsString = fruits.join();
console.log(fruitsString);
// Kiwi,Apple,Pineapple

const fruitsString2 = fruits.join("-");
console.log(fruitsString2);
// Kiwi-Apple-Pineapple

const fruitsString3 = fruits.join("*");
console.log(fruitsString3);
// Kiwi*Apple*Pineapple
```

- **split**

Empty String Separator: If you pass an empty string as a separator, each character in the string will become an element in the returned array:

```javascript
var str = "abcdefg";
var ar = str.split(""); // empty string separator
console.log(ar); // [ "a", "b", "c", "d", "e", "f", "g" ]
```

- **Includes**

includes retournera vrai ou faux si le tableau comprend l'élément donné.

```javascript
const fruits = ["Kiwi", "Apple", "Pineapple"];
console.log(fruits.includes("Kiwi")); // true
console.log(fruits.includes("Banana")); // false
```

- **lastIndexOf**

lastIndexOf renverra le dernier index (position dans le tableau) où un élément spécifique a été vu.

```javascript
const fruits2 = ["Kiwi", "Apple", "Pineapple", "Kiwi"];
//         0       1        2          3
console.log(fruits2.lastIndexOf("Kiwi"));
// Will return 3
```

- **IndexOf**

indexOf retournera la première position obtenue lorsque l'élément a été vu.

```javascript
const fruits2 = ["Kiwi", "Apple", "Pineapple", "Kiwi"];
//  				 0      1       2       3
console.log(fruits2.indexOf("Kiwi"));
// Will return 0
```

- **sort**
  sort triera le tableau par ordre alphabétique

```javascript
const fruits2 = ["Kiwi", "Apple", "Pineapple", "Kiwi"];
console.log(fruits2.sort());
// ["Apple", "Kiwi", "Kiwi", "Pineapple"]
```

sort triera par ordre alphabétique, même si vous triez des chiffres.

```javascript
const numbers = [1, 20, 45, 2, 3, 5, 8];
console.log(numbers.sort());
// [1, 2, 20, 3, 45, 5, 8]
```

Si tu veux trier par numéro, tu dois prévoir une fonction de callback pour le tri.

```javascript
const numbers = [1, 20, 45, 2, 3, 5, 8];
console.log(
  numbers.sort(function (a, b) {
    return a - b;
  })
);

// 1, 2, 3, 5, 8, 20, 45
```
