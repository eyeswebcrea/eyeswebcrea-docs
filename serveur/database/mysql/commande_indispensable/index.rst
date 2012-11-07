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

6.Sauvegarder une base
--------------------

Pour sauvegarder (dump) une base mysql dans un fichier texte on utilise la fonction mysqldump :

La syntaxe de la commande mysqldump est la suivante :


mysqldump [OPTIONS] ma_base_de_donnee [ma_table1, ma_table2,...]
Modifier le fichier app/config/parameters.ini de votre application

::

	; These parameters can be imported into other config files
	; by enclosing the key with % (like %database_user%)
	; Comments start with ';', as in php.ini
	[parameters]
	    database_driver   = pdo_sqlite
	    database_host     = localhost
	    database_port     =
	    database_user     = john
	    database_password = 147258
	    database_name     = default.sqlite
	    database_path     = %kernel.root_dir%/../spip/config/bases/prod.sqlite
	
	    mailer_transport  = smtp
	    mailer_host       = localhost
	    mailer_user       =
	    mailer_password   =
	
	    locale            = fr
	
	    secret            = ThisTokenIsNotSoSecretChangeIt
	    

database_driver : le drivers correspond au type de base de donnée ici 'pdo_sqlite' pour 'sqlite'
database_host : mettre 'localhost' cela n'a pas de sens pour une base sqlite mais c'est obligatoire
database_name : mettez le nom de votre base peut importe
database_path : mettez le path vers le fichier de votre base %kernel.root_dir% symbolyse
le répertoire app/ de votre application

Voici la ligne de commande pour sauveagarder la base entière :


mysqldump -u login -p password -h nom_serveur_rmysql --opt nom_base > sauvegarde_de_ma_base.sql

Voici la ligne de commande pour sauveagarder une table de la base :


mysqldump -u login -p password -h nom_serveur_rmysql --opt nom_base nom_table > sauvegarde_dune_seule_table_de_la_base.sql

7.Restaurer une base
------------------

mysql ma_base < sauvegarde_de_ma_base.sql

P.S : Il faut que la base de donnée existe sinon il faut la crée avec

CREATE DATABASE IF NOT EXISTS nom_base__

8.Configurer symfony2
---------------------

Modifier le fichier app/config/parameters.ini de votre application

::

	; These parameters can be imported into other config files
	; by enclosing the key with % (like %database_user%)
	; Comments start with ';', as in php.ini
	[parameters]
	    database_driver   = pdo_mysql
	    database_host     = localhost
	    database_port     = 
	    database_user     = john
	    database_password = 147258
	    database_name     = default.sqlite
	    database_path     = 
	
	    mailer_transport  = smtp
	    mailer_host       = localhost
	    mailer_user       =
	    mailer_password   =
	
	    locale            = fr
	
	    secret            = ThisTokenIsNotSoSecretChangeIt
	    

database_driver : le drivers correspond au type de base de donnée ici 'pdo_mysql' pour 'mysql'
database_host : mettre 'localhost' car la base de donée est sur le meme pc que l'application
database_port : mettre le port 3306 de préférence celui par défaut de mysql
database_name : mettez le nom de la base de donnée
database_path : laisser vide

le répertoire app/ de votre application

