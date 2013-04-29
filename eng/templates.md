Templates
=========


Retrieve a view parameter
-------------------------
```jinja
{{ app.request.attributes.get( 'viewParameters' ).offset }}
```

Name of a content
-----------------
```jinja
{{ content.contentInfo.name }}
```

Get a FieldType
---------------
```jinja
{{ content.getField( 'url' ).value.link }}
```

Render a FieldType
------------------
```jinja
{{ ez_render_field( <content>, <field_name>, {
            'template': 'eZDemoBundle:fields:fields.html.twig',
            'lang': 'eng-GB'
            } ) }}
```

Render an image with variations
-------------------------------
```jinja
<img src="{{ asset( ez_image_alias( <field>, <versionInfo>, <parameter_alias> ).uri ) }} alt="{{  <field>.value.alternativeText }}">
or

{{ ez_render_field(content, 'image', { 
                                        parameters:{ alias:'small' },
    									attr:{ class:'maClasse', custom_attribute:'value' }
									 }
				  )
}}
```

Render ezbinaryfile download link with nice file name
-------------------------------
```jinja
<a href="{{ path( 'ez_legacy', { 'module_uri': 'content/download/' ~
                                               <content>.contentInfo.id ~ '/' ~
                                               <field>.id ~
                                               '/version/' ~ <content>.contentInfo.currentVersionNo ~
                                               "/file/" ~ <field>.value.fileName|escape( 'url' ) }
         ) }}"/>
{{ <field>.value.fileName }}
</a>
```

Render a content type via "ESI"
-------------------------------

```jinja
 {{ render( controller( "ez_content:viewLocation", { "locationId": 123, "viewMode": "line" }, {"strategy": "esi"} ) }}
```

=> *ez_content* : service definied in service.yml

=> To use Varnish, don't forget to remove EzPublishCache from index.php

Render a content type via Asynchronous method
---------------------------------------------

```jinja
 {{ render( controller( "ez_content:viewLocation", { "locationId": 123, "viewMode": "line" }, {"strategy": "hinclude"} ) }}
```

=> Don't forget to add hinclude.js (http://mnot.github.io/hinclude/)

Extends viewbaseLayout
----------------------

```jinja
{% extends viewbaseLayout %}
```

=> *eZ/Bundle/EzPublishCoreBundle/Resources/views/viewbase_layout.html.twig*

Url to legacy module/view
-------------------------

```jinja
{{ path( 'ez_legacy', { 'module_uri': 'my_modyle/my_view/(param1)/value1' } ) }}
```

Link to content
---------------
Relative

```jinja
{{ path( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}
or
{{ path( location_object ) }}
```
	
Absolute
	
```jinja
{{ url( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}
or
{{ url( location_object ) }}
```

How to know if an user is authenticated
---------------------------------------
```jinja
{% if app.security.token.authenticated %}
...
{% else %}
...
{% endif %}
```

Twig Helper
-----------

Some parameters could help you directly on templates

```
ezpublish.siteaccess
ezpublish.requestedUriString
ezpublish.systemUriString
ezpublish.viewParameters
ezpublish.viewParametersString
ezpublish.siteName
ezpublish.legacy
```
About the legacy …

```
ezpublish.legacy.all
ezpublish.legacy.keys
ezpublish.legacy.get
ezpublish.legacy.has
```

Template inclusion legacy template
----------------------------------

```jinga
{% include "design:my/old_template.tpl" with {"someVar": "someValue"} %}
```
