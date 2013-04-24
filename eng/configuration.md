If you don't have a notice, all configuration should be added to **ezpublish.yml**

Custom local configuration
==========================

    ezpublish:
        # Locale conversion map between eZ Publish format to POSIX. 
        # Check locale.yml in EzPublishCoreBundle to see natively supported locales.
        locale_conversion:
            eng-DE: en_DE
            
Base layout for legacy fallback
===============================

=> Second parameter is to define where to inject data
=> Third parameter is to define which pagelayout should use the system for module rendering

    parameters:
        ezpublish_legacy.my_siteaccess.view_default_layout: AcmeDemoBundle::my_layout.html.twig
        ezpublish.content_view.content_block_name: content
        ezpublish_legacy.my_siteaccess.module_default_layout: AcmeDemoBundle::layout_legacy.html.twig