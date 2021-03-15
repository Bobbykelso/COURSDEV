# **GIT**

Git est une console qui permet d'obtenir un terminal linux.

- gist-github
  Permet de déposer du code en ligne
  https://gist.github.com/

## **quelques ligne de commandes**

- Pour savoir ou tu es dans ton terminal, faire

```
pwd
```

## **changer de répertoire avec CD**

- pour se déplacer dans le terminal

```
cd ../images
```

../ pour revenir dans le dossier parent puis aller dans le dossier image.

"cd .." = aller au dessus

**relative path**

"cd bureau" = change direction bureau SOIT va dans le dossier bureau ce moyen sapelle le relative path il fait donc en fonction de la ou on est

**absolute path**

"cd /c/Users" = absolute path to users / en gros on lui fait tout le chemin pour acceder ou en veux aller il ne fait donc pas attention d'ou on est

cd /opt : aller sous un répertoire en précisant son chemin absolu. L'emplacement de l'arborescence, c'est-à-dire sa position par rapport à la racine de l'arborescence.

cd ../home/wilder : d'abord, retourne à la racine (via ..) et de là, retourne au fichier /home/wilder.

cd ~ retour racine.

## **la tilde ~**

correspond aux répertoire perso de l'utilisateur, sa racine

utile pour revenir rapidement a la base de l'arborescence.

## **Lister les dossiers**

- pour faire la liste des dossier qu'on peut trouver la ou je suis

```

ls

```

```

$ ls
Bureau/ Images/ 'Prise en main de OneDrive.pdf'
Documents/ 'Pièces jointes'/ desktop.ini

```

"ls ."
fait la même chose ! Le symbole . signifie"le répertoire actuel".

"ls -a" affiche le contenu du répertoire, mais en incluant les fichiers cachés. Ceux-ci sont précédés du caractère . pour les différencier des fichiers "normaux". Attention, ici, le . est annexé au nom du fichier, il n'a pas la même signification que le symbole . pris isolément.

"ls Images" et "ls ./Images" affiche le contenu du dossier Images.

"ls /home/wilder" est une autre façon d'afficher le contenu de ton répertoire personnel, qui se trouve être le répertoire par défaut au lancement du terminal.

"ls /home" te permet d'afficher la liste des répertoires associés à chaque utilisateur du système.

"ls .." te donnera le même résultat ! Le .. signifie le répertoire parent. Celui qui se trouve juste au-dessus dans l'arborescence. /home est au-dessus de /home/wilder.

"ls /bin" affiche le contenu d'un répertoire contenant les commandes de base du système (par exemple, la commande ls elle-même !).

"ls -l /bin" fait la même chose, mais donne plus de détails, comme par exemple qui possède les fichiers, quand ils ont été modifiés pour la dernière fois, et ainsi de suite.

## **Fichiers et Dossiers**

- creer un repertoire (dossier)

  mkdir =

ex:

```
mkdir quests
mkdir -p quests/shell/vegetables quests/shell/fruits
mkdir quests/shell/remove-me quests/shell/delete-me
ls quests/shell
```

la commande échourait sans le flag -p
car le répertoire dans lequelq on le met n'existe pas.

le -p indique donc a mkdir de créer les répertoire intermediaire si il n'existe pas.

- créer des fichiers

  touch apple courgette
  va m créer deux fichiers vide apple et courgette la ou je suis
  "touch modifie le timestamp du fichier (l'heure de dernier modif )

* Supprimer des répertoires

  rmdir

  rmdir quests/shell/remove-me quests/shell/delete-me

rmdir ne fonctionne que sur des répertoires vides!

rm  
attention suppression immediate et définitive (pas de corbeille))

1. suppreimer les doublons

   "rm ap\* banana"

2. supprimer récursivement un répertoire

   "rm -r copy-of-fruits"

Comme le rm est immédiat et définitif, tu dois faire attention lorsque tu l'utilises avec le -r et/ou avec la wildcard \*.
Il est en effet trop facile de se tromper et d'effacer par inadvertance tout un répertoire et son contenu.

- le 'et'

  ;

il te permet de lancer plusieur commande en meme temps sur une seul ligne.

- copier

"cp" = copy a utilisé avec deux paramétre , source et destination
cp apple banana
cp apple fruits/orange
ls ; ls fruits

Nous créons ici deux copies du fichier apple, qui est la source dans les deux cas, la destination étant à chaque fois un nouveau fichier : banana or orange, chacun étant une copie exacte de apple.

Copier plusieurs fichiers dans un repertoire
Ici, nous créons une copie de chacun des fruits dans le répertoire fruits :

        cp ap* banana fruits/
        ls fruits
        Remarques :

Lorsque l'ordre cp reçoit plus de deux arguments, il s'attend à ce que le dernier, la destination, soit un répertoire.

Le **/** ajouté aux fruits est optionnel (même sans lui, cp déterminera si la cible est un fichier ou un répertoire).
Le concept des caractères wildcard: des caractères spéciaux permettent de spécifier simplement des ensembles de fichiers. Le caractère \* seul signifie "tous les fichiers" **; ap\*** signifie "tous les fichiers commençant par ap" (donc "apple" et "apricot" correspondent).

    cp -R fruits copy-of-fruits /tmp/

Grâce à l'argument -R, si le répertoire source contient des fichiers, ceux-ci sont copiés. S'il contient des répertoires, il les copie aussi, puis "descend" dans chacun de ces répertoires, et copie leur contenu, et ainsi de suite.

- **déplacement de dossier ou fichier**

      mv

  move sert a Déplacer et/ou renommer

  Déplacer:

        mv ca* parsnip courgette vegetables/

  Renommer:

         mv fruits/orange fruits/grapefruit

  Déplacer et renommer :

          mv vegetables/courgette fruits/kiwi

mv est utilisé avec deux ou plusieurs arguments, tout comme cp - le dernier étant la destination, et le(s) précédent(s) la (ou les) source(s).

- **écrire et lire du texte**

"echo" = permet d'ecrire du texte

        echo "Je suis moisi" > vieuxtacos.txt

"cat" = permet de lire le fichier text

        cat vieuxtacos.txt
        donne = Je suis moisi

- **Authorisation admin**

"sudo" = authorisation admin / il faut la mettre avant tout n'importe quel ligne qd ça bloque pour ça

## **raccourcis**

- Ctrl + A et Ctrl + E pour aller au début et a la fin de la ligne de commande.

- tab

permet de finir un mots en fonction des dossier existant la ou je suis.
