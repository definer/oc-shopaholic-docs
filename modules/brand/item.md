{% extends 'docs/modules/item-default.md' %}

{% block method_list %}
{{ parent() }}

### getPageUrl(_[$sPageCode = 'brand']_, _[$arRemoveParamList = \[\]]_)
* $sPageCode - page file name
* $arRemoveParamList - list of optional URL parameters that must be deleted when generating the URL page

Method returns URL of brand page.
Method gets properties of {{ component.link('brand-page') }} component attached on page and compiles parameter :slug to generate page URL.
{% endblock %}