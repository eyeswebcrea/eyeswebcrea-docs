===========================================
       Commandes indispensable
===========================================

1.Se connecter en ligne de commande
-----------------------------------

sqlite3

2.Selection une base de donnée
------------------------------

sqlite3 __DATABASE__

3.Cree une base de donéee
-------------------------

sqlite3 __DATABASE__

4.Suprimmer une base de donnée
------------------------------

Il faut simplement supprimer le fichier de la base de donnée

5.Selectionner des enregistrement
---------------------------------

SELECT * FROM __NOM_TABLE__

6.Sauvegarder une base
--------------------

Il suffit juste de copier le fichier se trouvant dans 

spip/config/bases/dev.sqlite pour la version de développement

spip/config/bases/prod.sqlite pour la version de production

7.Restaurer une base
------------------

Il suffit juste de remplacer le fichier se trouvant dans 

spip/config/bases/dev.sqlite pour la version de développement

spip/config/bases/prod.sqlite pour la version de production

8.Configurer symfony2
---------------------

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
