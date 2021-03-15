# **Flexbox**

### **Créer un conteneur flex**

```css
.parent {
  display: flex;
}
```

Par défaut, le conteneur flexible est réglé sur rang. Cette ligne a deux axes :

- Le main axis (axe principal) (horizontal)
- Le cross axis (axe transversal) (vertical)

### **Aligner élément sur axe principal**

```css
.parent {
  justify-content: center;
}
```

- **flex-start** alignera les éléments au début du conteneur
- **flex-end** alignera les éléments à la fin du conteneur
- **center** alignera les éléments au centre du conteneur
- **space-between** repartiras les éléments du conteneur (sur l'axe principal)
- **space-around** repartiras les éléments du conteneur et ajoutera un espace avant le premier et après le dernier élément.

### **Aligner élément sur l'axe transversal**

```css
.parent {
  align-items: center;
}
```

- **stretch** étirera les éléments le long de l'axe transversal
- **flex-start** alignera les éléments au départ
- **flex-end** alignera les éléments à la fin
- **center** alignera les éléments au centre
- **baseline** s'alignera sur la ligne de base du conteneur

### **Aligner sur axe trasversal 1 seul élement**

    align-self.

Accepte les mêmes valeurs que **align-items**, mais s'applique seulement à l'élément ciblé.

### **Définir espace entre les lignes**

```css
.parent {
  align-content: flex-start;
}
```

Cette propriété prend les valeurs suivantes :

- **flex-start** : Les lignes sont amassées dans le haut du conteneur.
- **flex-end**: Les lignes sont amassées dans le bas du conteneur.
- **center** : Les lignes sont amassées dans le centre vertical du conteneur.
- **space-between** : Les lignes s'affichent avec un espace égal entre eux.
- **space-around** : Les lignes s'affichent avec un espace égal autour d'eux.
- **stretch** : Les lignes sont étirées pour s'adapter au conteneur.

Ceci peut être mélangeant, mais align-content détermine l'espace entre les lignes, alors que align-items détermine comment les éléments dans leur ensemble sont alignées à l'intérieur du conteneur. Quand il n'y a qu'une seule ligne, align-content n'a aucun effet.

### **propriété flex**

```css
    .bloc-container {
    display: flex;
    justify-content: center;
    }
    .blocs {
    height: 100px;
    }
    .box-1 {
    flex: 1;
    background-color: peru;
    }

    .box-2 {
    flex: 2;
    background-color: paleturquoise;
```

La box 1 prend 1/3 de la place la box 2 prend 2/3 de la place en LARGEUR ( axe prencipal)

### **changer de direction**

    flex-direction

Lorsque **tu changes la direction du flex, les axes changent, en mode column, l'axe principal est vertical et l'axe transversal est horizontal.**
Cela signifie que si tu veux centrer horizontalement, tu dois maintenant utiliser align-items.

justify-content alignera les éléments sur l'axe principal et align-items sur l'axe transversal

- Si la direction est row l'axe principal est horizontal
- si la direction est row-reverse les éléments s'afficheront de droite à gauche
- si la direction est colonne l'axe principal est vertical
- si la direction est colonne-reverse, les éléments s'afficheront de bas en haut

```css
ex: .parent {
  flex-direction: column;
}
```

#### **flex-direction**

Cette propriété CSS définit la **direction** dans laquelle les éléments sont placés dans le conteneur, et accepte les valeurs suivantes :

- row : Les éléments sont disposés dans la même direction que le texte.
- row-reverse : Les éléments sont disposés dans la direction opposée au texte.
- column : Les éléments sont disposés de haut en bas.
- column-reverse : Les éléments sont disposés de bas en haut.

#### **order**

```css
order: -1;
```

change la disposition des box

#### **WRAP**

    flex-wrap

flex-wrap, accepte les valeurs suivantes :

- nowrap : Tous les éléments sont tenus sur une seule ligne.
- wrap : Les éléments s'enveloppent sur plusieurs lignes au besoin.
- wrap-reverse : Les éléments s'enveloppent sur plusieurs lignes dans l'ordre inversé.

#### **flex-flow**

Les deux propriétés **flex-direction** et **flex-wrap** sont utilisées tellement souvent ensembles que le raccourci **flex-flow** a été créé pour les combiner. Ce raccourci accepte les valeurs des deux propriétés séparées par un espace.

Par exemple, vous pouvez utiliser flex-flow: row wrap pour configurer les colonnes et les faire s'envelopper.
