---
layout: default
title: Presentations
permalink: /presentations/
---

# Presentations

Tech talks and presentations by Konstantinos Chatzinikolakis.

{% for presentation in site.presentations %}
## [{{ presentation.title }}]({{ presentation.url }})
*{{ presentation.date }} • {{ presentation.category }}*

{{ presentation.description }}

---
{% endfor %}

*Presentations are built with Reveal.js*