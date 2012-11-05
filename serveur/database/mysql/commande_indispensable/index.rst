===========================================
       Commandes indispensable
===========================================

1.Se connecter en ligne de commande
-----------------------------------

mysql

2.Selection une base de donnée
------------------------------

USE __DATABASE__

3.Cree une base de donéee
-------------------------

CREATE __DATABASE__;

4.Suprimmer une base de donnée
------------------------------

Il faut déjà selectioner une base de donnée 

Reporter vous au point 2 puis fait ce qui suit.

DROP __DATABASE__;

5.Selectionner des enregistrement
---------------------------------

SELECT * FROM __NOM_TABLE__

Sauvegarder une base
--------------------

Pour sauvegarder (dump) une base mysql dans un fichier texte on utilise la fonction mysqldump :

La syntaxe de la commande mysqldump est la suivante :


mysqldump [OPTIONS] ma_base_de_donnee [ma_table1, ma_table2,...]

Voici la ligne de commande pour sauveagarder la base entière :


mysqldump -u login -p password -h nom_serveur_rmysql --opt nom_base > sauvegarde_de_ma_base.sql

Voici la ligne de commande pour sauveagarder une table de la base :


mysqldump -u login -p password -h nom_serveur_rmysql --opt nom_base nom_table > sauvegarde_dune_seule_table_de_la_base.sql

Restaurer une base
------------------

mysql ma_base < sauvegarde_de_ma_base.sql

P.S : Il faut que la base de donnée existe sinon il faut la crée avec

CREATE DATABASE IF NOT EXISTS nom_base__