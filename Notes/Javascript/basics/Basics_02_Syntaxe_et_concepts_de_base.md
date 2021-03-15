# **Comment ajouter du JS dans une page web?**

```HTML
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>My website</h1>
    <script>
        // JAVASCRIPT GOES HERE!
    </script>
  </body>
</html>
```

## **Ajouter un fichier externe**

Comme en CSS, c'est une bonne pratique d'écrire ton JS dans un fichier séparé .js

```javascript
<script src="script.js"></script>
```

### **La console du navigateur**

Ouvrir la console

- Chrome
  Pour ouvrir la console dans Chrome, clic-droit dans la page > inspecter, puis cliques sur le l'onglet Console, that's it !
  P.S. : Tu peux aussi simplement appuyer sur F12

- Firefox
  Pour ouvrir la console dans Firefox, clic-droit dans la page > Examiner l'élément, puis cliques sur l'onglet Console, that's it !
  P.S. : Tu peux aussi simplement appuyer sur F12

### **Syntaxe de base**

Le code Javascript se termine avec un point-virgule

#### **String**

Les strings en Javascript sont des chaînes de caractères. Elles doivent être entourées de guillemets (quotes 🇬🇧) (simple ou double)

```javascript
console.log("Hello, world");
console.log("Hello, world");
```

### **Sensibilité à la casse**

Javascript est sensible à la casse. Écrire console.log et console.Log n'est pas la même chose !

### **Écrire des commentaires**

Commentaire simple ligne:

```javascript
// This is a comment
Commentaire multiple lignes:
```

```javascript
/* This comment
is on multiple lines */
```

Commentaire pour documentation:

```javascript
/**
 * This comment
 * is used for
 * documentation
 */
```

### **Opérations arithmétiques**

- Addition:

  1 + 1
  // => 2

- Soustraction:

  2 - 2
  // => 0

- Multiplication

  2 \* 3
  // => 6

- Division:

  6 / 2
  // => 3

- Modulo (donne le reste d'une division euclidienne):

  6 % 2
  // => 0

### **Comparaison**

Tu peux aussi utiliser Javascript pour comparer des valeurs
Javascript te donnera une réponse (true ou false, aussi appelés booléens).

#### **Valeur égale et type égal**

Dans ce cas, on va regarder si les valeurs sont strictement égales.

```javascript
1 === 1; // true ✅
"Bob" === "Bob"; // true ✅
"Bob" === "bob"; // false ❌
1 === "1"; // false ❌
```

#### **Valeur égale**

Dans ce cas, on regarde seulement si les valeurs sont égales.

```javascript
1 == 1; // true ✅
1 == "1"; // true ✅
```

##### **Differentes valeurs**

```javascript
1 != 2; // true ✅
1 != "1"; // false ❌
```

#### **Valeur différente ou type différent**

```javascript
1 !== "1";
// true ✅

1 !== 1;
// faux ❌
```

#### \*\*Supérieur à, supérieur ou égal

```javascript
2 > 1; // true ✅
2 >= 2; // true ✅
```

#### \*\*Inférieur à, inférieur ou égal

```javascript
2 < 3; // true ✅
2 <= 2; // true ✅
```
