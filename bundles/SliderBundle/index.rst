	
Bundle pour les slider
=======================

Ce bundle permet de générer le code html d'un slider jquery en passant simplement une liste d'items
que le bundle s'occupera d'afficher.

Ce bundle nécessite la librairie jquerySlider qui est à inclure dans le template désiré.

``@Eyeswebcrea/SliderBundle/Resources/public/js/slides.min.jquery.js``

Il est bien entendu nécessaire d'inclure également et avant cette lib la librarie jquery.

Pour le design en plus de la précision du design dans l'appel du slider il est nécessaire d'inclure le css.

``@Eyeswebcrea/SliderBundle/Resources/public/css/{NOM_THEME}/{NOM_THEME}.css``

A venir : Ce bundle supportera également bientôt les articles provenant d'articleProvider

Voir la documentation du bundle ``Eyeswebcrea/AliasContent/ViewerBundle``

Créer un slider depuis des articles spip
----------------------------------------

On appelle la fonction getSpipJquerySlider avec en paramètre `l'identifiant de la rubrique`
puis les options.

Options : 
	- limit : Limite du nombre d'items par défaut illimité.
	- order : Ordronance des items par défaut par le titre
	- theme : Nom du thème
	- texte_truncate : Nombre de caractères affiché dans la description.
	- texte : Affichage de la description ou non.
	- forceResize : Force le ratio de l'image ou non.

::

	{{ getSpipJquerySlider(5, { "theme" : "3D" , ... }) }}
	
	
Créer un slider depuis une liste d'items 
----------------------------------------

Cette liste doit être un tableau d'items étant eux-même des tableaux.

Tableau d'éléments dans la forme [ 1 => 'image_url', 'titre', 'descript', 'link_url', 2 => ...]

	 - Si aucun thème n'est précisé alors ce sera le thème de la configuration de l'application qui est utilisée.
	 - Si aucun tronquage de textes n'est précisé alors il est par défaut fixé à 550 caractères.
	 - Par défaut le texte est utilisé sauf si l'option texte est à ``false``. 
	 - Par défaut les images redimensioner conserve leur ratio sauf si l'option forceResize est à ``true``.

Options : 
	- theme : Nom du thème
	- texte_truncate : Nombre de caractères affiché dans la description.
	- texte : Affichage de la description ou non.
	- forceResize : Force le ratio de l'image ou non.
	
:: 

	{{ getJquerySlider(mesitems, { "theme" : "3D" , ... ) }}


Ajouter un thème : 
------------------

Il n'est pas actuellement possible d'ajouter un thème dans toucher le bundle lui même

Pour cela il faut crée un dossier dans ``Resources/views/__NOM__THEME__/``

Et prendre pour modèle les autres thèmes




	

	 