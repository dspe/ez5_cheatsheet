Vider le cache pour une location précise
========================================

```php
$this->container->get( 'ezpublish.http_cache.purger' )->purge( $locationId );
```

Vider tout le cache
==================

```php
$this->container->get( 'ezpublish.http_cache.purger' )->purgeAll();
```
