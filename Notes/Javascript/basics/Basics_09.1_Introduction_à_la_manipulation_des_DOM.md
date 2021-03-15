# **Intro au DOM**

## **quesaco le DOM**

DOM signifie **Document Object Model**. C'est une interface utilisée pour manipuler le contenu d'une page HTML.
Lorsque ton navigateur analyse ton code HTML et CSS, il crée également une représentation sous la forme d'un objet Javascript du document.
Nous utiliserons ce modèle pour manipuler notre page web.

https://developer.mozilla.org/en-US/docs/Web/API/Document

## **Sélectionner et modifier des éléments HTML**

Voyons comment sélectionner un élément du DOM. L'objet document est fourni avec une méthode appelée querySelector.
La méthode querySelector fonctionne de la même manière qu'un sélecteur CSS. Entre parenthèses, il suffit d'écrire le sélecteur souhaité.

Exemples:

```Javascript
const someDivClass = document.querySelector('.my-div');
const someImg = document.querySelector('.my-img');
const someDivId = document.querySelector('#another-div');
const someH1 = document.querySelector('.my-div h1');
```

https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement

```html
<body>
  <h1>Change the image source!</h1>
  <img src="https://placekitten.com/200/287" alt="Happy cat" class="img-cat" />
  <script src="src/index.js"></script>
</body>
```

```javascript
const catImage = document.querySelector(".img-cat");

// We set the source of the image to a new url
catImage.src = "https://placekitten.com/200/286";
```

## **InnerHTML**

La méthode innerHTML est utilisée pour modifier le contenu d'une balise HTML.

```javascript
const title = document.querySelector(".title");
title.innerHTML = "Hello, Bob!";
```

Dans cet exemple, nous sélectionnons le h1 avec la classe title, et nous changeons le contenu par Hello, Bob !

### **D'autres méthodes de sélection des éléments**

- document.getElementById
- document.getElementByTagName

ils sont également pris en charge par les anciens navigateurs tels qu'Internet Explorer 6 - 7 (ce qui n'est pas le cas de querySelector).

```javascript
const title = document.getElementById("title");
const heading = document.getElementsByTagName("h1");
```

exemple:

```HTML
<body>
  <h1>Change image properties</h1>
  <img src="https://placedog.net/800/500" alt="Dog Image" id="dog-img" />
  <script src="src/index.js"></script>
</body>
```

```javascript
const dogImg = document.getElementById("dog-img");
/* dogImgHTMLImageElement.alt = "A sleeping Dog"; */
dogImg.width = "500";
dogImg.alt = "A sleeping dog";
```

### **Sélectionner plusieurs éléments qui ont la même classe/la même balise**

document.querySelector, s'il y a plus d'un élément avec le même sélecteur dans le document
(ex multiple h1), celui sélectionné par défaut sera la première occurrence.

Si tu veux obtenir un tableau avec plusieurs éléments tu peux utiliser document.querySelectorAll.

Ceci créera un tableau avec tous les éléments qui correspondent à ton sélecteur.

```javascript
document.querySelectorAll("h1");
```

Test pour modif 5 images

```html
<body>
  <h1>Replace Bill Murray's pictures by dogs pictures</h1>
  <img src="https://www.fillmurray.com/200/300" />
  <img src="https://www.fillmurray.com/200/300" />
  <img src="https://www.fillmurray.com/200/300" />
  <img src="https://www.fillmurray.com/200/300" />
  <img src="https://www.fillmurray.com/200/300" />
  <script src="src/index.js"></script>
</body>
```

```javascript
const dogsPicture = [
  "https://random.dog/0c021634-cc90-443e-bedb-6f754fcfb7bc.png",
  "https://placedog.net/500/280",
  "https://placedog.net/500/300",
  "https://placedog.net/500/302",
  "https://placedog.net/500/305",
];

const images = document.querySelectorAll("img");

for (let i = 0; i < dogsPicture.length; i++) {
  images[i].src = dogsPicture[i];
}
```

notre const images est un tableau car on sélectionne plusieur élément.

https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents
