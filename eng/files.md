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

**ezpublish/config/ezpublish.yml** declare siteaccess, database configuration,  image_alias, use directly legacy or not, etc...

**ezpublish/config/parameters.yml** (include via config.yml) contains path for pagelayout (ezpublish_legacy.view.default_layout)
