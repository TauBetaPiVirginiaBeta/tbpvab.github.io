---
layout: page
title: AutoOfficers-testList
permalink: /officers-temp-test-list/
published: true
---

<!-- Scratchpad, this was what worked originally -->
<!-- Data format:
- id: id
  name: name
  email: email -->
<!-- {% for officer in site.data.officers %} -->
  <!-- <img class="headshot" src="{{ site.baseurl }}/uploads/headshots/{{ officer.id }}.jpg"> -->
  <!-- <h2>
    {{ officer.name }} - {{ officer.email }}
  </h2> -->

  <!-- [{{ officer.name }} - {{ officer.email }}]({{ site.baseurl }}/officer/{{ officer.id }}) -->
  <!-- [{{ officer.name }}]({{ site.baseurl }}/officer/{{ officer.id }}) -->
  <!-- <p>{{ staff_member.content | markdownify }}</p> -->
<!-- {% endfor %} -->

<!-- Tutorial for Jekyll+Liquid for future maintainers: -->
<!-- Over here, I wanted to show stuff on individual lines,
and Jekyll+Liquid apparently wanted the logic to be all on one line to
format everything properly as a hyperlink; hence readability took a hit.
For the future, write it out indented, and if you're able to see the raw
output printed, then collapse it all back on one line. Worst case,
send me an email (arinjoyb@vt.edu)/pull request and I'll take a look. -->

<!-- Tutorial for Jekyll+Liquid for future maintainers: -->
<!-- Also, you can't nest expressions, like dict[another_dict[key]] for some reason.-->
<!-- Instead, Liquid needs the value to be assigned to a variable first and then used.-->
<!-- No wonder Liquid code looks like a maze at first; but I think I'm getting the hang of it. -->

{% for board in site.data.yearly-positions %}
  {% if board.year == site.data.sitewide.current-year %}
  {% for position in board.positions %}
  {% assign position-name = position[0] %}
  {% assign person-name = position[1] %}
  <img class="headshot" src="{{ site.baseurl }}/uploads/headshots/{{ person-name }}.jpg">
  
  [{{ site.data.sitewide.positions-details[position-name] }} - {{ site.data.officers[person-name].name }}]({{ site.baseurl }}/officer/{{ person-name }})

  {% endfor %}
  {% endif %}
{% endfor %}

<!-- {{ site.data.sitewide.positions-details[position[0]] }} {{ site.data.officers[position[1]] }} -->

## Past Officers:

{% for board in site.data.yearly-positions %}  
  {% if board.year != site.data.sitewide.current-year %}[{{ board.year }} Officers ]({{ site.baseurl }}/officers/{{ board.year }}){% endif %}
{% endfor %}

<!-- Tutorial for Jekyll+Liquid for future maintainers -->
<!-- Proof that anything in the yml files in the _data folder is accessible from anywhere -->
<!-- <p>{{site.data.sitewide.current-year}}</p> -->