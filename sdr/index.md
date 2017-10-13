---
layout: archive
title: "Latest Posts in *sdr*"
excerpt: "Intresting things in the linux world"

---

<div class="tiles">
{% for post in site.categories.sdr %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
