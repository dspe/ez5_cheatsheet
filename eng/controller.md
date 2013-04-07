Purge viewCache for a specific location
=======================================

    $this->container->get( 'ezpublish.http_cache.purger' )->purge( $locationId );

Purge all viewCache
===================

    $this->container->get( 'ezpublish.http_cache.purger' )->purgeAll();

Get location children id
===================

    $currentLocation = $locationService->loadLocation( $locationId );
    $currentLocationChildren = $locationService->loadLocationChildren( $currentLocation, $offset = 0, $limit = -1 );
    $childrenLocatinoId = array();
    foreach ( $currentLocationChildren->locations as $childLocation )
    {
	    $childrenLocatinoId[] = $childLocation->contentInfo->mainLocationId;
    }
