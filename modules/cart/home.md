[Back to modules](modules/home.md)

Home
• [Model](modules/cart/model/model.md)
• [Components](modules/cart/component/component.md)

# Cart {docsify-ignore-all}

!> **Attention!**  We recommend that you read [Architecture](home.md#architecture), [ElementItem class](item-class/item-class.md),
[ElementCollection class](collection-class/collection-class.md) sections for complete understanding of  project architecture.

> Module available with [Orders for Shopaholic](plugins/home#orders-for-shopaholic) plugin.

Using this module you will be able to allow users to add product offers to cart,
display cart positions (for example: mini-cart),
change quantity and remove positions from cart.

![](./../../assets/images/fronend-cart-1.png)

![](./../../assets/images/fronend-cart-2.png)

## How it works?

```plantuml
@startuml
start
:User open page;
if (user is authorized?) then (yes)
    :Get cart object by user ID;
    if (Is cart object?) then (yes)
        :Get cart object
         from database
         or create new
         cart object;
    else (no)
        :Create new
         cart object;
    endif 
    :Get cart ID from cookie;
    if (User cart ID == cart ID from cookie?) then (yes)
    else (no)
        :Get cart object by
         cart ID from cookie;
        :Merge cart positions
         of user cart and cart object
         with ID from cookie;
         :Remove cart object
         with ID from cookie;
    endif
else (no)
    :Get cart ID from cookie;
    if (Cart ID is empty?) then (yes)
        :Create new
         cart object;
    else (no)
        :Get cart object
         from database
         or create new
         cart object;
    endif
endif
:Save cart ID in cookie;
stop
@enduml
```

Home
• [Model](modules/cart/model/model.md)
• [Components](modules/cart/component/component.md)

[Back to modules](modules/home.md)