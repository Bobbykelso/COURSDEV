## **Responsive Design**

Le terme "responsive design" (conception réactive ou adaptative) ne se réfère pas à une technologie spécifique. Il fait plutôt référence à un ensemble d'outils et de pratiques pour créer des mises en page qui "s'adaptent" à la taille des écrans.
Le terme "responsive design" a été apposé par Ethan Matcotte en 2010.

### **Mobile-first**

Un concept qui est également apparu avec le responsive design (et surtout à la "révolution mobile") est le concept de mobile-first.

La philosophie du mobile-first est de toujours commencer à travailler sur la version mobile avant de construire la version de bureau.

Non seulement les utilisateurs auront une meilleure expérience sur mobile, mais il est également plus facile de commencer à travailler sur une version mobile.

### **La balise Meta viewport**

Pour indiquer au navigateur que ta page s'adapte à tous les appareils, tu dois ajouter une balise meta dans le head de votre document :

```html
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
```

### **media query**

```css
@media <media_types> and (<media_features>) {
  /* put your CSS here */
}
```

#### Types de media

- all
  Tu peux utiliser all pour appliquer la règle à tous les types d'appareils.

- print
  Utilisé pour un document destiné à être imprimé (papier)

- screen
  Utilisé pour tous les types d'écran.

- speech
  Pour les synthétiseurs de parole

Le plus utilisé est généralement screen.

Les features les plus courantes sont la largeur minimale min-width et la largeur maximale max-width.

Tu peux trouver une liste complète\* sur le site w3schools :
https://www.w3schools.com/cssref/css3_pr_mediaquery.asp

```css
@media screen and (max-width: 500px) {
  .menu {
    display: none;
  }
}
```

### **Taille approximative d'écran**

- Mobile en portrait **(320px à 414px)** - Pour les appareils avec des écrans de 4" à 6,9".
- Mobile en paysage **(568px à 812px**)\*\* - Idem, mais en paysage.
- Tablette en portrait **(768px à 834px)** - Pour les appareils de 7" à 10".
- Tablette en paysage **(1024px à 1112px)** - Idem, mais aussi tablettes 12" en portrait.
- Ecrans d'ordinateurs portables et de bureau **(>1200px)** - Varie beaucoup, mais généralement de 1200px et plus.

### **Image**

Un autre concept important en responsive design est celui des images.
Nous voulons aussi que les images s'adaptent à la taille de l'écran.

Nous pouvons utiliser ce code pour nous assurer que l'élément image ne prend pas plus de 100% de la taille du parent

```css
img {
  max-width: 100%;
  height: auto;
}
```
