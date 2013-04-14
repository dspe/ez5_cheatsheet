Templates
=========


Retrieve a view parameter
-------------------------
    {{ app.request.attributes.get( 'viewParameters' ).offset }}

Name of a content
-----------------
    {{ content.contentInfo.name }}

Get a FieldType
---------------
    {{ content.getField( 'url' ).value.link }}
    
Render a FieldType
------------------

    {{ ez_render_field( <content>, <field_name>, { 
                'template': 'eZDemoBundle:fields:fields.html.twig',
                'lang': 'eng-GB' 
                } ) }}

Render an image with variations
-------------------------------
    <img src="{{ asset(ez_image_alias( <field>, <versionInfo>, <parameter_alias> ).uri) }} alt="{{  <field>.value.alternativeText }}">      
or

    {{ez_render_field(content, 'image', {parameters:{alias:'small'},
    	attr:{class:'maClasse',
        custom_attribute:'value'}
    })}}

Render ezbinaryfile download link with nice file name
-------------------------------
	<a href="{{ path( 'ez_legacy', { 'module_uri': 'content/download/' ~
												   <content>.contentInfo.id ~ '/' ~
												   <field>.id ~
												   '/version/' ~ <content>.contentInfo.currentVersionNo ~
												   "/file/" ~ <field>.value.fileName|escape( 'url' ) }
			 ) }}"/>
	{{ <field>.value.fileName }}
	</a>

Render a content type via "ESI"
-------------------------------

     {% render "ez_content:viewLocation" with { "locationId": 123, "viewMode": "line" }, {standalone: true} %}

=> *ez_content* : service definied on service.yml

=> becarful, don't forget to remove EzPublishCache on index.php

Extends viewbaseLayout
----------------------

    {% extends viewbaseLayout %}

=> *eZ/Bundle/EzPublishCoreBundle/Resources/views/viewbase_layout.html.twig*

Url to legacy module/view
-------------------------

    {{ path( 'ez_legacy', { 'module_uri': 'my_modyle/my_view/(param1)/value1' } ) }}


Link to content
------------------
Relative

	{{ path( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}
	or
	{{ path( location_object ) }}
	
Absolute
	
	{{ url( 'ez_urlalias', {'locationId': content.contentInfo.mainLocationId} ) }}
	or
	{{ url( location_object ) }}

How to know if an user is connected or not
------------------------------------------
    {% if app.security.token.authenticated %}
    ... 
    {% else %}
    ...
    {% endif %}

