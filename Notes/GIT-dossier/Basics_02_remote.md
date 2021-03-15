# **config Git avec son compte github**

        git config --global user.name "Gaetan"
        git config --global user.email "gabu-g@hotmail.fr"

Nous permet de nous relier, prendre meme mail que github.

On créer un dossier puis on navigue dedans on peu faire cd (glisser dossier)

## **Créer un repository**

        git init

## **Ajouter modif de dossié**

git add.

## **faire un commit**

        git commit -m 'My first commit'

## **Revenir au dernier commit**

    git checkout -- .

## **rajouter username**

        git config --global user.username gabugim

## **push**

    git push origin main

## **historique des dernier push**

        git log
        git log --graph
        git log --graph --oneline      ( pour avoir des vu plus graphique)

        gitk --all&

## **push en rajoutant une branche**

        git push -u origin master

-u servant a créer la blranch s'il elle n'existe pas.

        git branch <BRANCHNAME>

         si on push une branch

         git push origin <branchName>
## **ajouter un télecommande nommé origin au dépot**

        git remote add origin <URLFROMGITHUB>

ou (dépend du systéme)

        git remote set-url origin <URLFROMGITHUB>

## **cloner un dossier de github dans son github**

        git clone <URLFROMGITHUB>

- renommer clone

        git clone httpsetc.. nouveaunomdudossier



