Fichiers utiles
===============

Configuration eZ 5 par défaut
-----------------------------

eZ/Bundle/EzPublishCoreBundle/Resources/config/default_settings.yml

Délclaration des fieldstypes ( datatype ) l'équivalent de datatype.ini
-----------------------------------------------------------------------

vendor/ezsystems/ezpublish/eZ/Bundle/EzPublishCoreBundle/Resources/config/fieldtypes.yml

Visualisation des fieldstypes
---------------------------

vendor/ezsystems/ezpublish/eZ/Bundle/EzPublishCoreBundle/Resources/views/content_fields.html.twig

Le contrôleur de la vue content/location
-----------------------------------------

vendor/ezsystems/ezpublish/eZ/Publish/MVC/Symfony/Controller/Content/ViewController.php

La configuration des settings dans EZ5
--------------------------------------

ezpublish/config/ezpublish.yml contient la déclaration des siteaccess, la configuration de la base de données,  image_alias, l'activation ou non du mode legacy, etc...

ezpublish/config/parameters.yml (ce fichier étant inclut dans config.yml) contient le path de la pagelayout par défaut (ezpublish_legacy.view.default_layout)