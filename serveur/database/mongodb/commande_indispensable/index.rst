===========================================
       Commandes indispensable
===========================================

1.Se connecter en ligne de commande
-----------------------------------

mongo	

2.Selection une base de donnée
------------------------------

show dbs

use db_name

3.Cree une base de donéee
-------------------------

4.Suprimmer une base de donnée
------------------------------

Il faut déjà selectioner une base de donnée 

Reporter vous au point 2 puis fait ce qui suit.

db.remove();

5.Selectionner des enregistrement
---------------------------------

db.__nom_table__.find();

6.Sauvegarder une base
----------------------

mongodump --db __DATABASE__ --out __OUT_FILE__

7.Restaurer une base
--------------------

mongorestore __backup_file__


8.Configurer symfony2
---------------------

Modifier le fichier app/config/config.yml de votre application

::

	doctrine_mongodb:
	    connections:
	        default:
	            server: mongodb://localhost:27017
	            options:
	                connect: true
	                
Mettre dans serveur mongodb://__ip_serveur__:__port_serveur__

Lexique 
-------
database : database
table : collection
index : index 
row : BSON document
column : BSON field
join : embedding and linking
primary key : _id field
group by : aggregation
