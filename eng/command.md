Usefull commands
================

Purge Symfony cache
-------------------

```
php ezpublish/console cache:clear
```

Create a new bundle
-------------------

```
php ezpublish/console generate:bundle
```

Generate autoloads from eZ 5 root
---------------------------------

```
php ezpublish/console ezpublish:legacy:script bin/php/ezpgenerateautoloads.php
```

Purge legacy cache from eZ 5 root
---------------------------------

```
php ezpublish/console ezpublish:legacy:script bin/php/ezcache.php --legacy-help
```

Run a legacy script from eZ 5 root
----------------------------------

```
php ezpublish/console ezpublish:legacy:script runcronjobs.php frequent
```
**Be careful**: If you would like to pass parameter to script, please use full name like *--siteaccess* due to a conflict with CLI options.

Get an overview of EzPublishCoreBundle's configuration
------------------------------------------------------

```
php ezpublish/console config:dump-reference ezpublish
```