{% extends 'docs/modules/collection-default.md' %}

{% block method_list %}
{{ parent() }}

* [group](#groupicoupongroupid)
* [hidden](#hidden)
* [notHidden](#nothidden)
* [visibleToUser](#visibletouseriuserid)

### group($iCouponGroupID)
  * $iCouponGroupID - coupon group ID

Method applies filter by coupon group ID.

### hidden()

Method applies filter to field "hidden" = true for elements of collection.

### notHidden()

Method applies filter to field "hidden" = false for elements of collection.

### visibleToUser($iUserID)
  * $iUserID - user ID

Method returns list of coupons visible to user.
{% endblock %}