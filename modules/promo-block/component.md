{% extends 'docs/modules/component-default.md' %}

{% block content %}

* [PromoBlockList](#promoblocklist)
  * [getSorting](#getsorting)
  * [make](#makearelementidlist-null)
* [PromoBlockPage](#promoblockpage)
  * [get](#get)
* [PromoBlockData](#promoblockdata)
  * [get](#getielementid)

## PromoBlockList

Component allows you to render blocks with promo blocks. For example: all promo blocks, promo block list with pagination,
random promo blocks, etc.

Available values of default "sorting" property:
  * default
  * date_begin|asc
  * date_begin|desc
  * date_end|asc
  * date_end|desc

### getSorting()

Get active sorting key value.

### make(_[$arElementIDList = null]_)

Method returns new object of {{ collection.link() }} class.

**Example:** Create simple block with random 5 promo block list on index page.

File: **pages/index.htm**
{% verbatim %}
```twig
title = "Index"
url = "/"
layout = "main"
is_hidden = 0

[PromoBlockList]
==
<div class="promo-block-wrapper">
    {% partial 'promo-block/promo-block-list/random-promo-block-list' %}
</div>
```
{% endverbatim %}

File: **partials/promo-block/promo-block-list/random-promo-block-list.htm**
{% verbatim %}
```twig
{# Get promo block collection #}
{% set obPromoBlockList = PromoBlockList.make().active() %}
{# Get array with random promo blocks #}
{% set arPromoBlockList = obPromoBlockList.random(5) %}

{% if arPromoBlockList is not empty %}
    {# Render promo block list #}
    <ul>
        {% for obPromoBlock in arPromoBlockList %}
            <li>{% partial 'promo-block/promo-block-card/promo-block-card' obPromoBlock=obPromoBlock %}</li>
        {% endfor %}
    </ul>
{% endif %}
```
{% endverbatim %}

## PromoBlockPage

Component allows you to render promo block page.

Available properties:

{% verbatim %}
|Property|Available values|Description|
|---|---|---|
|slug|{{ :slug }}|URL parameter from page settings|
|slug_required|0 or 1|If value is 1, component will generate 404 page, if "slug" parameter is empty|
|smart_url_check|0 or 1|If value is 1, then component will make additional check for full URL of page|
{% endverbatim %}

### get()

Method returns {{ item.link() }} object for current page.

{% verbatim %}
```twig
[PromoBlockPage]
slug = "{{ :slug }}"
==

{# Get promo block item #}
{% set obPromoBlock = PromoBlockPage.get() %}
<div data-id="{{ obPromoBlock.id }}">
    <h1>{{ obPromoBlock.name }}</h1>
    {% if obPromoBlock.preview_image is not empty %}
        <img src="{{ obPromoBlock.preview_image.path }}" title="{{ obPromoBlock.preview_image.title }}" alt="{{ obPromoBlock.preview_image.description }}">
    {% endif %}
    <div>{{ obPromoBlock.description|raw }}</div>
</div>
```
{% endverbatim %}

## PromoBlockData

Component allows you to render blocks with promo block. You can get promo block object by ID.

### get($iElementID)

Method returns {{ item.link() }} object with ID = $iElementID.
{% verbatim %}
```twig
[PromoBlockData]
==

{# Get promo block item with ID = 10 #}
{% set obPromoBlock = PromoBlockData.get(10) %}
{% if obPromoBlock.isNotEmpty() %}
    <div data-id="{{ obPromoBlock.id }}">
        <h1>{{ obPromoBlock.name }}</h1>
        {% if obPromoBlock.preview_image is not empty %}
            <img src="{{ obPromoBlock.preview_image.path }}" title="{{ obPromoBlock.preview_image.title }}" alt="{{ obPromoBlock.preview_image.description }}">
        {% endif %}
        <div>{{ obPromoBlock.description|raw }}</div>
    </div>
{% endif %}
```
{% endverbatim %}
{% endblock %}