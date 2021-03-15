# **DOM Manipulation - gestion des événements**

Maintenant il est temps d'apprendre comment réagir à un événement en utilisant Javascript.

## **Gestionnaires d'événements**

Ajouter un peu d'interactivité

### **gestion des clics**

Pour la gestion des clics, tu peux modifier la propriété onclick en y affectant une fonction.

```javascript
someDiv.onclick = function () {
  someDiv.style.backgroundColor = "red";
};
```

### **AddEventListener**

addEventLlistener est une méthode qui accepte comme premier paramètre le type d'événement, et le second est une fonction de callback.

```javascript
someDiv.addEventListener("click", function () {
  someDiv.style.backgroundColor = "red";
});
```

addEventListener peut être utilisé pour écouter un grand nombre d'événements différents, tels que:

- click
- mousedown
- mouseup
- mousemove
- mouseover
- mouseleave
- ...

Exemple

modifier quelques éléments de ce code.

- Lorsque l'utilisateur clique sur l'image, cela doit changer la source de l'image et le texte de la propriété alt
- Lorsque l'utilisateur survole le titre, la couleur du texte doit changer
- Lorsque la souris quitte le titre, la couleur doit revenir au noir

```Html
<!DOCTYPE html>
<html>
  <head>
    <title>Parcel Sandbox</title>
    <meta charset="UTF-8" />
  </head>

  <body>
    <div id="app"></div>
    <h1 class="title">Hover me</h1>
    <img src="https://placedog.net/500" class="img-dogs" alt="picture of dog" />
    <script src="src/index.js"></script>
  </body>
</html>
```

```javascript
const changeImg = document.querySelector(".img-dogs");

changeImg.addEventListener("click", function () {
  changeImg.src =
    "https://www.wanimo.com/veterinaire/wp-content/uploads/2018/11/chat-jaloux-e1574672723199.jpg";
  changeImg.alt = "cat";
});

const title1 = document.querySelector(".title");
title1.addEventListener("mouseover", function () {
  title1.style.color = "green";
```

resultat:

https://codesandbox.io/s/laughing-brook-xd2mm-forked-c1u7u?file=/index.html

### **Travailler avec un formulaire form**

Nous pouvons ajouter une fonction lorsqu'un formulaire est envoyé en utilisant la propriété onsubmit sur l'élément form

```javascript
const form = document.querySelector("#form");

form.onsubmit = function () {
  console.log("Hello world!");
};
```

Le problème avec cette approche est que lorsque l'on appelle onsubmit, la page se rafraîchit.

Pour empêcher la page de se rafraîchir, nous pouvons utiliser une méthode que nous obtenons dans l'objet event appelée preventDefault.

preventDefault empêchera la page de se recharger.

```javascript
const form = document.querySelector("#form");

form.onsubmit = function (event) {
  event.preventDefault();
  console.log("Hello, world!");
};
```

nous pourrions obtenir la valeur de l'input afin de pouvoir afficher le nom que l'utilisateur a tapé.

```javascript


``const form = document.querySelector("#form");
const firstName = document.querySelector("#firstname");
const lastName = document.querySelector("#lastname");

form.onsubmit = function(event) {
  event.preventDefault();
  console.log(`Hello, ${firstName.value} ${lastName.value}`);
};

```

exercice/exemlpe

Crée les variables pour le form, l'input et la todolist (ul)
Ajoute une fonction anonyme au form onsubmit (avec event en paramètre)
Dans la fonction, utilise event.preventDefault pour éviter le reload de la page
Ensuite, crée une variable et utilise createElement pour créer un nouveau noeud li
À l'intérieur de cet élément li, ajoute la valeur de l'input (en utilisant innerHTML et input.value)
Ajoute à l'élément ul l'élément juste créé
Efface la valeur de la saisie pour que le texte ne reste pas (input.value = "")

```html
  <body>
    <h1>Todo list App</h1>
    <form id="form">
      <label for="todo">Todo:</label>
      <input
        type="text"
        name="todo"
        placeholder="Flight to the moon"
        id="todoInput"
        value=""
      />

      <input type="submit" value="send" />
    </form>
    <h2>Todo:</h2>
    <ul id="todolist">
      <li>Build a spaceship</li>
    </ul>
    <script src="src/index.js"></script>
  </body>
</html>
```

ma version

```javascript
const form = document.querySelector("#form");
const input = document.querySelector("#todoInput");
const toDoList = document.querySelector("#todolist");
form.onsubmit = function (event) {
  event.preventDefault();
  const newElement = document.createElement("li");
  newElement.innerHTML = input.value;
  toDoList.appendChild(newElement);
  input.value = "";
};
```

version du cours

```javascript
const inputTodo = document.querySelector("#todoInput");
const todolist = document.querySelector("#todolist");

// Onsubmit we will run a function
form.onsubmit = function (event) {
  // We want to prevent the page to reloas
  event.preventDefault();

  // We create a variable that we set to a new li node
  const newTodo = document.createElement("li");
  // We add the text to the li
  newTodo.innerHTML = inputTodo.value;
  // We add the li to the ul
  todolist.appendChild(newTodo);
  // We clear the value of the input
  inputTodo.value = "";
};
```

### **Changer une classe**

Changer une classe
L'utilisation de la méthode classList.toggle sur un élément ajoutera la classe si la classe n'est pas là, si la classe est déjà présente alors elle la supprimera.
C'est utile, par exemple, dans le cas où tu veux créer un menu déroulant. Lorsque l'utilisateur clique dessus, cela supprime ou ajoute la classe visible.

```javascript
element.classList.toggle("mystyle");
```

- EXEMPLE:

Dans cet exemple, nous avons un bouton et une liste d'animaux emoji. Cette liste a la propriété display: none.
L'ajout de la classe visible sur l'élément la transformera en display : block.

En utilisant ce que nous avons appris, crée un listener sur le bouton; en cliquant, ajoute ou supprime la classe visible sur le contenu du dropdown-menu-content (en utilisant la méthode toggle).

```javascript
const dropBtn = document.querySelector(".dropdown-btn");
const dropContent = document.querySelector(".dropdown-menu-content");

dropBtn.addEventListener("click", function () {
  dropContent.classList.toggle("visible");
});
```

### **Obtenir des informations sur l'événement event**

La fonction de callback que tu donnes à un addEventListener peut accepter un paramètre; ce paramètre est l'objet event.

L'objet event contient beaucoup de propriétés et de méthodes concernant l'événement qui vient de se produire.

```javascript
const title = document.querySelector(".title");

title.addEventListener("click", function (event) {
  console.log(event);
  title.style.color = "red";
});

document.body.addEventListener("mousemove", function (event) {
  console.log(event);
});
```

exemple:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Parcel Sandbox</title>
    <meta charset="UTF-8" />
    <link rel="stylesheet" href="./src/styles.css" />
  </head>

  <body>
    <div id="app"></div>
    <h1 class="title">Move the mouse on the screen</h1>
    <h2>Mouse position:</h2>
    <h3 id="title-cursor-position">X: ?? - Y:??</h3>
    <script src="src/index.js"></script>
  </body>
</html>
```

```javascript
// We create a variable set to the title with the cursor position
const titleCursorPosition = document.querySelector("#title-cursor-position");
// We listen to mouse movement on the body
document.body.addEventListener("mousemove", function (event) {
  // Everytime the mouse move we change what's between the two title tags
  titleCursorPosition.innerHTML = `x:${event.clientX}, y:${event.clientY}`;
});
```

### **Les petits plus**

https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents

**exo Sur DOM a revoir**

https://codepen.io/1Gabu1/pen/mdOQzbr?editors=1010
