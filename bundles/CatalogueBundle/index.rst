Bundle du catalogue
===================

Le catalogue est composée d'un :
--------------------------------
	- Espace d'administration permetant de gerer le catalogue de produit (En cours) 
	- Espace utilisateur permettant de gerer ces achats si l'option boutique à été activée dans les paramètre de l'application (A implémentée)
	- Espace public pour la consultation du catalogue sur le site
	
	
Configuration 
-------------

Plusieur parametre de configuration s'offre à nous :
	
	- theme 
	- id_catalogue
	- item_par_page
	- keywork_categorie
	- kaywork_produit
	- simulaite_bot
	- catalogue_manager
	
theme
~~~~~

	Le paramètre thème permet de définir un thème pour le catalogue parmis ceux disponible
	
.. note::

	- Ce parametre est optionel
	- Ce paramètre prend par défaut ``Default``
	
id_catalogue
~~~~~~~~~~~~

	Le paramètre id_catalogue permet de définir l'identifiant de la rubrique qui contient le catalogue par défaut

.. warning::

	- Ce paramètre sera bientot obsolète
	- Ce paramètre est obligatoire
	
item_par_page
~~~~~~~~~~~~~

	Ce paramètre permet de spécifié le nombre d'item que l'on shouaite afficher au maximum par page
		
.. note::
	
	- Ce paramètre est optionelle
	- Ce paramètre prend par défaut ``10``
		

keywork_categorie
~~~~~~~~~~~~~~~~~

	Ce paramètre permet de définir le mot clé qui permettera de savoir quel catégorie est du type catégorie de produit
	
.. warning::

	- Ce parametètre sera bientot obsolète
	- Ce paramètre est obligatoire
	
keywork_produit
~~~~~~~~~~~~~~~

	Ce paramètre permet de définir le mot clé qui permettera de savoir quel catégorie est du type produit
	
.. warning::

	- Ce parametètre sera bientot obsolète
	- Ce paramètre est obligatoire
	
simulaite_bot
~~~~~~~~~~~~~

	Ce paramètre permet de faire afficher les pages des produit de la facon dont le catalogue les affiche pour le moteur de recherche google
	Cette affichage est un affichage optimisé pour le référencement
	
.. info::

	- Ce paramètre est optionelle
	- Ce paramètre prend par défaut ``false``
	
catalogue_manager
~~~~~~~~~~~~~~~~~

	Ce paramètre à été introduit récément afin de permettre de préciser un catalogue manager
	
	Un Catalogue Manager est un provider de donée qui est fourni les donnée au catalogue
	Ce Catalogue Manager permet d'adapter le catalogue à n'importe quel source pourvu que son
	provider est été développer.
	
.. info::
	
   - Ce paramètre est optionelle
   - Ce paramètre prend par défaut ``eyeswebcrea_catalogue.catalogue_manager``
	
Personaliser son catalogue Manager
----------------------------------

Afin de personaliser la source il est possible de crée son propre catalogue manager

Si vous désirez utiliser un cms comme source alors nous vous conseillont d'utiliser 
Un ``ContentManager`` fourni par le bundle ``AliasContentManager``

Si un provider existe pour votre cms pour le bundle ``AliasContentManager`` et qu'il est configurée dans les paramètre du bundle
Alors vous pourez communiquer par l'interface ``ContentManager`` Fourni par le bundle ``AliasContentManager``
	
Un provider pour le catalogueManager doit être composée de plusieur choses :
	- Un Catalogue Manager
	- Un Categorie Entity
	- Un Categorie Manager
	- Un EntityListTransform
	- Un ProductEntity
	- Un ProductManager
	- Un TagEntity
	- UN TagManager
	
Voici une schématique de la structure
	