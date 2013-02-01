Templates
=========


Récupérer des views parameters
------------------------------
    {% app.request.attributes.get( 'viewParameters' ).offset %}

Nom d'un contenu
----------------
    {% content.contentInfo.name %}

Récupérer un FieldType
----------------------
    {% content.getField( 'url' ).value.link %}
    
Rendu d'un FieldType
--------------------

    {{ ez_render_field( <content>, <field_name>, { 
                'template': 'eZDemoBundle:fields:fields.html.twig',
                'lang': 'eng-GB' 
                } ) }}

Rendu d'une image avec variations
---------------------------------
   <img src="{{assets(ez_image_alias( <field>, <versionInfo>, <parameter_alias> ).uri) }}>      
 ou   
   {{ez_render_field(content, 'image', {parameters:{alias:'small'},                                        attr:{class:'maClasse',                                              custom_attribute:'value'}                                        })}}

Rendu de contenu type "ESI"
---------------------------

     {% render "ez_content:viewLocation" with { "locationId": 123, "viewMode": "line" }, {standalone: true} %}

=> *ez_content* : service défini dans service.yml

=> attention, pour l'utilisation avec Varnish des ESI, il ne faut surtout pas charger EzPublishCache dans le index.php car sinon, Symfony va simuler un reverse-proxy et ne renverra pas des bloc ESI. 

Etendre viewbaseLayout
----------------------

    {% extends viewbaseLayout %}

=> *eZ/Bundle/EzPublishCoreBundle/Resources/views/viewbase_layout.html.twig*

Chemin vers module legacy
-------------------------

    {{ path( 'ez_legacy', { 'module_uri': 'my_modyle/my_view/(param1)/value1' } ) }}


Lien vers un contenu
--------------------
    {{ path( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}


