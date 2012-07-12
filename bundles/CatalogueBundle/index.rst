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
	Si ce paramètre n'est pas défini dans les paramètre de l'application il vaudra par défaut ``Default``
	
.. note::

	Ce parametre est optionel
	
id_catalogue
~~~~~~~~~~~~

	Le paramètre id_catalogue permet de définir l'identifiant de la rubrique qui contient le catalogue par défaut

.. warning::

	Ce paramètre sera bientot obsolète
	Ce paramètre est obligatoire
	
item_par_page
~~~~~~~~~~~~~

	Ce paramètre permet de spécifié le nombre d'item que l'on shouaite afficher au maximum par page
	Si ce paramètre n'est pas défini dans les paramètre de l'application il vaudra par défaut ``10``
		
.. note::
	
	Ce paramètre est optionelle
		

keywork_categorie
~~~~~~~~~~~~~~~~~

	Ce paramètre permet de définir le mot clé qui permettera de savoir quel catégorie est du type catégorie de produit
	
.. warning::

	Ce parametètre sera bientot obsolète
	Ce paramètre est obligatoire
	
keywork_produit
~~~~~~~~~~~~~~~

	Ce paramètre permet de définir le mot clé qui permettera de savoir quel catégorie est du type produit
	
.. warning::

	Ce parametètre sera bientot obsolète
	Ce paramètre est obligatoire
	
simulaite_bot
~~~~~~~~~~~~~

	Ce paramètre permet de faire afficher les pages des produit de la facon dont le catalogue les affiche pour le moteur de recherche google
	Cette affichage est un affichage optimisé pour le référencement
	
.. info::

	Ce paramètre est optionelle
	
catalogue_manager
~~~~~~~~~~~~~~~~~

	Ce paramètre à été introduit récément afin de permettre de préciser un catalogue manager
	
	Un Catalogue Manager est un provider de donée qui est fourni les donnée au catalogue
	Ce Catalogue Manager permet d'adapter le catalogue à n'importe quel source pourvu que son
	provider est été développer.
	
	S'il n'est pas renseigné dans les paramètre de l'application ce paramètre prend par défaut la valeur ``eyeswebcrea_catalogue.catalogue_manager``
	
.. info::
	
   Ce paramètre est optionelle
	
	
