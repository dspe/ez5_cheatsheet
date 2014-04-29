Purge viewCache for a specific location
=======================================

```php
$this->container->get( 'ezpublish.http_cache.purger' )->purge( $locationId );
```

Purge all viewCache
===================

```php
$this->container->get( 'ezpublish.http_cache.purger' )->purgeAll();
```

Get location children id
===================

```php
$currentLocation = $locationService->loadLocation( $locationId );
$currentLocationChildren = $locationService->loadLocationChildren(
    $currentLocation, $offset = 0, $limit = -1
);
$childrenLocatinoId = array();
foreach ( $currentLocationChildren->locations as $childLocation )
{
    $childrenLocatinoId[] = $childLocation->contentInfo->mainLocationId;
}
```

Check if a user is authenticated
===================

```php
$securityToken = $this->container->get('security.context')->getToken();
$userAuth = $securityToken->isAuthenticated(); // return true or false
```

Transform Symfony locale to eZ Publish
===================

```php
$symfonyLocale = $this->getRequest()->get( '_locale' );
$localeConverter = $this->container->get( 'ezpublish.locale.converter' );
$ezLocale = $ezLocale = $localeConverter->convertToEz( $symfonyLocale );
```

