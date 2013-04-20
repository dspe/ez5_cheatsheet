Usefull files
=============

eZ 5 default configuration
--------------------------

    eZ/Bundle/EzPublishCoreBundle/Resources/config/default_settings.yml

Declare FieldTypes ( datatypes )
--------------------------------

    vendor/ezsystems/ezpublish/eZ/Bundle/EzPublishCoreBundle/Resources/config/fieldtypes.yml

Template used to render fieldtypes
----------------------------------

    vendor/ezsystems/ezpublish/eZ/Bundle/EzPublishCoreBundle/Resources/views/content_fields.html.twig

Controller used to render content/location
------------------------------------------

    vendor/ezsystems/ezpublish/eZ/Publish/MVC/Symfony/Controller/Content/ViewController.php

Differents configuration files
------------------------------

**ezpublish/config/ezpublish.yml** defines the siteaccess, the database
configuration, the image\_alias, set whether to directly use the legacy or not,
etc...

**ezpublish/config/parameters.yml** (included in config.yml) contains the path
to the pagelayout (ezpublish\_legacy.view.default\_layout)
