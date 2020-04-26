{% extends "docs/modules/home-default.md" %}

{% block content %}
{{ parent() }}

Payment method allows the user to choose their preferred payment method before creating an order.
The payment method can be different: cash, card, online payment.
The payment method may be linked with one of the payment gateways (For example: PayPal, Stripe, etc.).
Link of payment methods and a payment gateway will allow you to redirect the user to the online payment page, after creating the order.

## Backend

You can create and edit payment methods by going to **Backend -> Settings -> Payment methods**

![](./../../assets/images/backend-payment-method-1.png ':class=medium-image')

You can change sorting of payment methods by going to **Backend -> Settings -> Payment methods -> Reorder records**

![](./../../assets/images/backend-payment-method-2.png ':class=medium-image')
{% endblock %}
