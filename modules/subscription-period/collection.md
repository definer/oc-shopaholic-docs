{% extends 'docs/modules/collection-default.md' %}

{% block method_list %}
{{ parent() }}

* [sort](#sort)

### sort()

Method sorts elements of collection by "sort_order" field.
You can change sorting of access period to subscriptions by going to **Backend -> Settings -> Access period to subscriptions -> Reorder records**

![](./../../../assets/images/backend-subscription-period-2.png ':class=medium-image')
{% endblock %}
