{% extends "docs/modules/home-default.md" %}

{% block content %}
{{ parent() }}

## Introduction

Using "Subscriptions for Shopaholic" plugin you can sell products with a subscription sales model.
User will be able to buy products for a certain period, renew their current subscription, and see their purchased subscriptions.

You can give access to any custom model (for example "Article" model). This will give you opportunity to give access to paid content, such as an article in paid journal.

## Backend

You can set product as subscription by going to **Backend -> Catalog -> Products -> Edit product -> "Settings" tab -> "Is subscription" checkbox**

![](./../../assets/images/backend-product-5.png ':class=medium-image')

You can set an access period for offers of subscription by going to **Backend -> Catalog -> Products -> Edit product -> Edit offer -> "Settings" tab -> "Period" select**

![](./../../assets/images/backend-offer-5.png ':class=medium-image')

You can create and edit access period to subscriptions by going to **Backend -> Settings -> Access period to subscriptions**

![](./../../assets/images/backend-subscription-period-1.png ':class=medium-image')

You can change sorting of access period to subscriptions by going to **Backend -> Settings -> Access period to subscriptions -> Reorder records**

![](./../../assets/images/backend-subscription-period-2.png ':class=medium-image')

You can view, manage access to subscriptions by going to **Backend -> Users -> User access to subscriptions**

![](./../../assets/images/backend-subscription-access-1.png ':class=medium-image')

## Settings

You can set logic for creating access to subscriptions.

Go to **Backend -> Settings -> Basic settings -> "Subscriptions" tab**

![](./../../assets/images/backend-settings-15.png ':class=medium-image')
{% endblock %}
