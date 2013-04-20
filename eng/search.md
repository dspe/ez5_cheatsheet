Basic syntax:
=============

```php
$searchService = $this->getRepository()->getSearchService();

$query = new Query();

$query->criterion = new Criterion\LogicalAnd(
    $criterionArray
);

// array( new SortClause\ContentId() )
$query->sortClauses = $sortMethodsArray;

$query->limit = 20;
$query->offset = 0;

$searchService->findContent($query);
```

Criterion Operators:
====================

```php
Criterion\Operator::BETWEEN; // Criterion\Operator::BETWEEN, array( 1033920275, 1033920794 )
Criterion\Operator::EQ; // Criterion\Operator::EQ, 'Members'
Criterion\Operator::GT; // Criterion\Operator::GT,1343140540
Criterion\Operator::GTE;
Criterion\Operator::IN; // Operator::IN, array( 10, 14 )
Criterion\Operator::LIKE; // '*ezpublish*'
Criterion\Operator::LT;
Criterion\Operator::LTE;
```

Logical Criterions:
===================

```php
Criterion\LogicalAnd;
Criterion\LogicalNot;
Criterion\LogicalOr;
```

Search Criterions:
==================

```php
new Criterion\DateMetadata(
    Criterion\DateMetadata::MODIFIED,
    Criterion\Operator::BETWEEN,
    array( 1033920275, 1033920794 )
);

new Criterion\ContentTypeIdentifier( array( 'article', 'folder' ) );

new Criterion\LocationId( array( 1, 2, 5 ) );

new Criterion\Subtree( "/1/2/" );

new Criterion\SectionId( array( 2 ) );

new Criterion\ParentLocationId(  array( 1 ) );

new Criterion\UserMetadata(
    Criterion\UserMetadata::CREATOR,
    Operator::IN,
    array( 10, 14 )
);
Criterion\UserMetadata::CREATOR;
Criterion\UserMetadata::GROUP;
Criterion\UserMetadata::MODIFIER;
Criterion\UserMetadata::OWNER;

new Criterion\Visibility( Criterion\Visibility::VISIBLE );
Criterion\Visibility::VISIBLE;
Criterion\Visibility::HIDDEN;

new Criterion\ContentId(array( 1, 4, 10 ));

new Criterion\ContentTypeId( 4 );

new Criterion\ContentTypeGroupId( 2 );

new Criterion\DateMetadata(
    Criterion\DateMetadata::MODIFIED,
    Criterion\Operator::GT,
    1343140540
);

new Criterion\FullText( 'Contact*' );

new Criterion\Field( 'name', Criterion\Operator::EQ, 'Members' );

new Criterion\Status( array( Criterion\Status::STATUS_PUBLISHED ) );

new Criterion\LocationRemoteId(
    array(
        '3f6d92f8044aed134f32153517850f5a',
        'f3e90596361e31d496d4026eb624c983'
    )
);
```

Sort Clauses:
=============

```php
new SortClause\Field('blog_post', 'publication_date', Query::SORT_DESC);
new SortClause\ContentId();
new SortClause\LocationPathString( Query::SORT_DESC );
new SortClause\LocationDepth( Query::SORT_ASC );
new SortClause\ContentName( Query::SORT_ASC );
new SortClause\LocationPriority( Query::SORT_DESC );
new SortClause\DatePublished();
new SortClause\DateModified();
new SortClause\SectionIdentifier();
new SortClause\SectionName();
new SortClause\ContentName();
new SortClause\Field( "folder", "name" );
```
