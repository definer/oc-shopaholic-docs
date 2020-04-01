## Example {{ i }}: Check access to subscription

### {{ i }}.1 Task

Check user access to subscription.

### {{ i }}.2 Source code

<!-- tabs:start -->
#### ** Lovata.Buddies **

File: **pages/index.htm**
{% verbatim %}
```twig
title = "Index page"
url = "/"
layout = "main"
is_hidden = 0

[UserData]
==

{# Get user object #}
{% set obUser = UserData.get() %}

{# Check access to subscription with product ID == 1 #}
{% if obUser.checkAccessToSubscription(1) %}
  <p>User has access</p>
{% else %}
  <p>User hos not access</p>
{% endif %}
```
{% endverbatim %}

#### ** RainLab.User **

File: **pages/index.htm**
{% verbatim %}
```twig
title = "Index page"
url = "/"
layout = "main"
is_hidden = 0
==

{% if user %}
    <p>Hello {{ user.name }}</p>
    {# Check access to subscription with product ID == 1 #}
    {% if user.checkAccessToSubscription(1) %}
      <p>User has access</p>
    {% else %}
      <p>User hos not access</p>
    {% endif %}
{% else %}
    <p>Nobody is logged in</p>
{% endif %}
```
{% endverbatim %}
<!-- tabs:end -->