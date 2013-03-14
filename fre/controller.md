Vider le cache pour une location précise
========================================

    $this->container->get( 'ezpublish.http_cache.purger' )->purge( $locationId );

Vider tout le cache
==================

    $this->container->get( 'ezpublish.http_cache.purger' )->purgeAll();
