Call a Symfony service through a eZ4 module
===========================================

```php
$Module = $Params['Module'];
$Result = array();
 
$container = ezpKernel::instance()->getServiceContainer();
/** @var \Acme\TestBundle\Controller\AdminController $controller */
$controller = $container->get( 'my.admin.controller' );
$Result['content'] = $controller->myAdminAction( 'blabla' )->getContent();
```

More informations is on: https://gist.github.com/lolautruche/5694727

Get configuration from your siteaccess
======================================

```php
$configResolver = $this->container->get( 'ezpublish.config.resolver' );
$rootLocationId = $configResolver->getParameter( 'content.tree_root.location_id' );