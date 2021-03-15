# **install with windows**

https://www.sitepoint.com/how-to-install-php-on-windows

## **Executer du PHP avec un serveur**

PHP integre en interne son propre serveur en HTTP, on l'utilise pour tester son code.
Ce serveur n'est a utiliser que durant la phase de développement. En prod on utilisera des serveur plus robuste.

#### **lancer son serveur:**

- Dans le terminal se placer dans le dossier qu'on souhaite executer sur le serveur et taper la commande:

```
php -S localhost:8000
```

- Ensuite ouvrir la page sur un navigateur avec

```
http://localhost:8000/leNomDeMonDossierPhp.php

```

-le serveur php ne fonctionne que qd tu as ton terminal ouvert ou jusqu'a ce que tu le stoppe avec : `ctr+c`

## **premier script php**

En premier lieu il faut créer un dossier se terminant par php.

```php
<?php
echo 'Hello Wilders';
```
