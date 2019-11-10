[Back to modules](modules/home.md)

[Home](modules/promo-block/home.md)
• [Model](modules/promo-block/model/model.md)
• [Item](modules/promo-block/item/item.md)
• [Collection](modules/promo-block/collection/collection.md)
• [Components](modules/promo-block/component/component.md)
• Events
• [Examples](modules/promo-block/examples/examples.md)
• [Extending](modules/promo-block/extending/extending.md)

# Event list: Promo block {docsify-ignore-all}

!> **Attention!**  We recommend that you read [Architecture](home.md#architecture), [ElementItem class](item-class/item-class.md),
[ElementCollection class](collection-class/collection-class.md) sections for complete understanding of  project architecture.

## **shopaholic.promo_block.get.promo-block.list**

The event allows you to extend list of products for promo block

For example:
```php
Event::listen(\Lovata\Shopaholic\Models\PromoBlock::EVENT_GET_PRODUCT_LIST, function($obPromoBlock) {
    /** @var \Lovata\Shopaholic\Models\PromoBlock $obPromoBlock */
    //to get produt ID list with using $obPromoBlock object
    $arProductIDList = ...
    
    return $arProductIDList;
});
```

## **shopaholic.promo_block.get.type.list**

The event allow you to extend list with available types of promo blocks.
You can set type of promo block in backend and use it in your templates.

![](./../../../assets/images/backend-promo-block-3.png)

For example:
```php
Event::listen(\Lovata\Shopaholic\Models\PromoBlock::EVENT_GET_TYPE_LIST, function() {
    $arResult = [
        'my_type_1' => 'My custom type 1',
        'my_type_2' => 'My custom type 2',
    ];
    
    return $arResult;
});
```


[Home](modules/promo-block/home.md)
• [Model](modules/promo-block/model/model.md)
• [Item](modules/promo-block/item/item.md)
• [Collection](modules/promo-block/collection/collection.md)
• [Components](modules/promo-block/component/component.md)
• Events
• [Examples](modules/promo-block/examples/examples.md)
• [Extending](modules/promo-block/extending/extending.md)

[Back to modules](modules/home.md)