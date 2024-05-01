---
layout: page
title: Past Officers
permalink: /past-officers/
published: true
---

{% for board in site.data.yearly-positions %}  
  {% if board.year != site.data.sitewide.current-year %}[{{ board.year }} Officers ]({{ site.baseurl }}/officers/{{ board.year }}){% endif %}
{% endfor %}