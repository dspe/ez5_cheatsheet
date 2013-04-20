Templates
=========


Récupérer des views parameters
------------------------------
```jinja
{{ app.request.attributes.get( 'viewParameters' ).offset }}
```

Nom d'un contenu
----------------
```jinja
{{ content.contentInfo.name }}
```

Récupérer un FieldType
----------------------
```jinja
{{ content.getField( 'url' ).value.link }}
```

Rendu d'un FieldType
--------------------

```jinja
{{ ez_render_field( <content>, <field_name>, {
            'template': 'eZDemoBundle:fields:fields.html.twig',
            'lang': 'eng-GB'
            } ) }}
```

Rendu d'une image avec variations
---------------------------------
```jinja
<img src="{{ asset(ez_image_alias( <field>, <versionInfo>, <parameter_alias> ).uri) }}>
ou

{{ez_render_field(content, 'image', {parameters:{alias:'small'},
    attr:{class:'maClasse',
    custom_attribute:'value'}
})}}
```

Rendu de contenu type "ESI"
---------------------------

```jinja
 {% render "ez_content:viewLocation" with { "locationId": 123, "viewMode": "line" }, {standalone: true} %}
```

=> *ez_content* : service défini dans service.yml

=> attention, pour l'utilisation avec Varnish des ESI, il ne faut surtout pas
charger EzPublishCache dans le index.php car sinon, Symfony va simuler un
reverse-proxy et ne renverra pas des bloc ESI.

Etendre viewbaseLayout
----------------------

```jinja
{% extends viewbaseLayout %}
```

=> *eZ/Bundle/EzPublishCoreBundle/Resources/views/viewbase_layout.html.twig*

Chemin vers module legacy
-------------------------

```jinja
{{ path( 'ez_legacy', { 'module_uri': 'my_modyle/my_view/(param1)/value1' } ) }}
```


Lien vers un contenu
--------------------
Relatif

```jinja
{{ path( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}
ou
{{ path( location_object ) }}
```
	
Absolu
	
```jinja
{{ url( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}
ou
{{ url( location_object ) }}
```

Connaître si l'utilisateur est connecté ou non
----------------------------------------------
```jinja
{% if app.security.token.authenticated %}
...
{% else %}
...
{% endif %}
```

