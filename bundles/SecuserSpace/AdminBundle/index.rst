
Bundle de l'espace d'aministration des sites internet
=====================================================

Installation :
--------------

## Installation

### Etape 1) Recuperer le bundle

Deux méthodes existe:

#### Méthode a) Utiliser le fichier `deps`

Ajoutez ces ligne au fichier `deps` et lancer la commande ``php bin/vendors
install``

::

	[EyeswebcreaBundles]
	git=https://github.com/eyeswebcrea/EyeswebcreaBundles.git
	target=bundles/Eyeswebcrea


#### Méthode b) Utiliser sous modules

Lancer ces commandes pour récupérer le bundle en tant que sous module

::

	git submodule add https://github.com/eyeswebcrea/EyeswebcreaBundles.git vendor/bundles/Eyeswebcrea


### Etape 2) Enregistrer les namespaces

Ajouter cette entrée namespace dans l'appel ``registerNamespaces`` dans l'autoloader:

::

	<?php
	// app/autoload.php
	$loader->registerNamespaces(array(
	    // ...
	    'Eyeswebcrea' => __DIR__.'/../vendor/bundles/Eyeswebcrea',
	    // ...
	));


### Etape 3) Enregistrer le bundle

Pour commencer à utiliser le bundle, Enregistrer le dans le kernel:

::

	<?php
	// app/AppKernel.php
	
	public function registerBundles()
	{
	    $bundles = array(
	        // ...
	        new Eyeswebcrea\SecuserSpace\AdminBundle\EyeswebcreaSecuserSpaceAdminBundle(),
	    );
	    // ...
	}


Comment est composée l'espace d'aministration ?
-----------------------------------------------

L'espace d'administration est composée de :
	- Un menu dynamique sur lequel les autres bundles peuvent venir 
	  se greffer en point d'entrer de leur administration.
	- Un layout dont les layout d'administration des bundles tiers 
	  Peuvent hérité afin de s'integrer dans l'espace d'aministration
	- Une authentification/Desauthentification déja développer permettant
	  à l'administrateur de venir se loguer via celle ci 
	
	
Comment étendre le menu d'administration depuis un autre Bundle ? 
-----------------------------------------------------------------

Le bundle KnpMenuBundle est utilisée ici pour gerer le menu.
	
	Il faut cela crée un listener qui va venir alimentée le menu
	
## Crée un listener listener

Vous pouvez enregister autan de listener pour votre event que vous voulez Ajouter juste.

::

	<?php
	// src/Acme/OtherBundle/EventListener/ConfigureMenuListener.php
	
	namespace Acme\OtherBundle\EventListener;
	
	use Acme\DemoBundle\Event\ConfigureMenuEvent;
	
	class ConfigureMenuListener
	{
	    /**
	     * @param \Acme\DemoBundle\Event\ConfigureMenuEvent $event
	     */
	    public function onMenuConfigure(ConfigureMenuEvent $event)
	    {
	        $menu = $event->getMenu();
	
	        $menu->addChild('Matches', array('route' => 'versus_rankedmatch_acp_matches_index'));
	        $menu->addChild('Participants', array('route' => 'versus_rankedmatch_acp_participants_index'));
	    }
	}


Vous pouvez maintenant déclarer el listener.

::

	services:
	    acme_other.configure_menu_listener:
	        class: Acme\OtherBundle\EventListener\ConfigureMenuListener
	        tags:
	          - { name: kernel.event_listener, event: acme_demo.menu_configure, method: onMenuConfigure }


**Note:** Si vous utiliser symfony 2.1, Vous pouvez aussi crée un listener avec un subscriber
Et utiliser le tag ``kernel.event_subscriber``

Comment étendre ses templates tiers au layout de l'interface d'administration :
-------------------------------------------------------------------------------

Pour ceci c'est très simple, Utiliser le code Ci-dessous dans le layout de l'administration de votre bundle: 

::

	{% extends "EyeswebcreaSecuserSpaceAdminBundle::layout.html.twig" %}
	{% block body %}
	Contenu de l'administration du bundle
	{% endblock %}
	
Les blocks disponibles sonts : 
	- title (Titre du site) 
	- header (Entete de l'espace d'aministration contenant le menu)
	- body (Contenu à remplir dans l'espace admin)
	- footer (Pied de page de l'espace d'admnistration)
	
Autres informations utiles :
----------------------------

Diférentes routes sont disponible par défault :
 - EyeswebcreaSecuserSpaceAdminBundle_login (La page de connection à l'espace d'administration)
 - EyeswebcreaSecuserSpaceAdminBundle_logout (La page de déconnection à l'espace d'aministration)
 - EyeswebcreaSecuserSpaceAdminBundle_homepage (La page d'acceuil de l'espace d'administration pouvant regrouper quelques information utiles)
 
 
