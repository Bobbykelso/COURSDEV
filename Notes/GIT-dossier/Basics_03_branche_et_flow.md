# **Flow**

Aussi appelé workflow, c'est une suite d'étape qu'une équipe doit suivre pour compléter une tache.

Dans notre cas c'est lorsque on apporte des modifications au code d'un projet web. C'est une organiqation.

Cette approche permet :

- de minimiser les risque de conflit (les devs ne travaillent pas sur la même paritie du code en même temps)

- facilite le controle du code.

## **Créer un repo Branche, pull request et merge sur github**

https://guides.github.com/activities/hello-world/

On peut voir toute les modifs sur **Insight** puis **network** pour avoir un visuel.

petit résumé pour décrire comment faire dans un vrai projet en git et github (tres interessant)
https://www.youtube.com/watch?v=MnUd31TvBoU&ab_channel=TheNetNinja


## **Commande dans l'orde**

0) On créer notre repository sur github (ou on va chercher celui qu'on veut)

1)  git clone https://github.com/gabugim/website-flow.git
prendre le lien dans github 
etre dans le dossier souhaité

2) git init 
ne pas oublier d'etre a l'endroit du clone

3) git branch cheese
on créer une branche si besoin il y a

4) git checkout cheese
on quitte la branche principal pour se mettre dans celle qu'on vien de créer

5) On fait nos changement sur les dossiers

6) git add.
On rajoute nos modif

7) git commit -m notre message pour les autres
ça enregistre et ça ecrit une note

8) git push origin cheese
on envoie notre code sur github via la nouvelle branch cheese avec notre message du 7)

9)Celui qui gére le repo reçoit une pull request sur le repo github il valide ou non, puis il peut merge et supprimmer la branche si tout lui convient. Ou renvoyer et dire qu'il y a des trucs a refaire.