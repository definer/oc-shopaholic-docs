{% extends 'docs/modules/collection-default.md' %}

{% block method_list %}
{{ parent() }}

* [active](#active)
* [available](#availableardata-)
* [sort](#sort)

### active()

Method applies filter to field "active" = true for elements of collection.

### available($arData = [])

Method removes payment methods from collection that are not approved via restrictions.
```php
$obList = PaymentMethodCollection::make([1,2,10,15])->available(['state' => 'NY']);
```

### sort()

Method sorts elements of collection by "sort_order" field. You can change sorting of payment methods by going to **Backend -> Settings -> Payment methods -> Reorder records**

![](./../../../assets/images/backend-payment-method-2.png ':class=medium-image')
{% endblock %}
