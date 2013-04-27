If you don't have a notice, all configuration should be added to **ezpublish.yml**

Custom local configuration
==========================

```yml
    ezpublish:
        # Locale conversion map between eZ Publish format to POSIX. 
        # Check locale.yml in EzPublishCoreBundle to see natively supported locales.
        locale_conversion:
            eng-DE: en_DE
```
            
Base layout for legacy fallback
===============================

=> Second parameter is to define where to inject data

=> Third parameter is to define which pagelayout should use the system for module rendering

```yml
    parameters:
        ezpublish_legacy.my_siteaccess.view_default_layout: AcmeDemoBundle::my_layout.html.twig
        ezpublish.content_view.content_block_name: content
        ezpublish_legacy.my_siteaccess.module_default_layout: AcmeDemoBundle::layout_legacy.html.twig
```


Multisite with single repository
================================

```yml
ezpublish:
    system:
        my_siteaccess:
            content:
                tree_root:
                    # Root locationId. Default is top locationId
                    location_id: 123
                    # Every URL aliases starting with those prefixes will be considered 
                    # being outside of the subtree starting at root_location.
                    # Default value is an empty array.
                    # Prefixes are not case sensitive.
                    excluded_uri_prefixes:
                        - media
                        - users
```

Siteaccess matching: matchers
=============================

URIElement
----------

```yml
ezpublish:
    siteaccess:
        match:
            URIElement: 1
```

URIText
-------

```yml
ezpublish:
    siteaccess:
        match:
            URIText:
                prefix: foo
                suffix: bar
```

HostElement
-----------

```yml
ezpublish:
    siteaccess:
        match:
            HostText:
                prefix: www.
                suffix: .com
```

Map\Host
--------

```yml
ezpublish:
    siteaccess:
        match:
            Map\Host:
                www.foo.com: foo_front
                adm.foo.com: foo_admin
                www.stuff.fr: bar_front
                adm.stuff.fr: bar_admin

```

Map\URI
-------

```yml
ezpublish:
    siteaccess:
        match:
            Map\URI:
                something: ezdemo_site
                foobar: ezdemo_site_admin
```

Map\Port
--------

```yml

ezpublish:
    siteaccess:
        match:
            Match\Port:
                80: foo
                8080: bar
```

Regex\Host
----------

```yml
ezpublish:
    siteaccess:
        match:
            Regex\Host:
                regex: "^(\\w+_sa)$"
                # Default is 1
                itemNumber: 1
```

Regex\URI
---------

```yml
ezpublish:
    siteaccess:
        match:
            Regex\URI:
                regex: "^/foo(\\w+)bar"
                # Default is 1
                itemNumber: 1
```