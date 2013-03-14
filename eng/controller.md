Purge viewCache for a specific location
=======================================

    $this->container->get( 'ezpublish.http_cache.purger' )->purge( $locationId );

Purge all viewCache
===================

    $this->container->get( 'ezpublish.http_cache.purger' )->purgeAll();
