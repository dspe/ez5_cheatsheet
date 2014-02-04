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

Exec a legacy function in Symfony 2 controller
=======================================

Add this function in your controller

```php
protected function getLegacyKernel()
{
    $kernelClosure = $this->container->get('ezpublish_legacy.kernel');
    return $kernelClosure();
}
```
Then you can

```php
public function anyFunction()
{
    $foo = 'hello world';
    $bar = 'wazaaa';
    
    $search = $this->getLegacyKernel()->runCallback(function() use ($foo, $bar) {
        // Run any legacy function
        $searchQuery = \eZFunctionHandler::execute('ezfind','search', array(
            'query' => $foo . ' ' . $bar
        ) );
        return $searchQuery;
    });
    
    var_dump($search); // The value from the legacy call
    
    // ... continue to code
}
```
