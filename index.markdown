---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

# Features
{% assign characteristics = site.characteristics | sort: "label" %}
{% for characteristic in characteristics %}
  - [{{ characteristic.label }}]({{ characteristic.url | relative_url }})
{% endfor %}

# SA4s
{% for sa4 in site.sa4s %}
  - [SA4 {{ sa4.name }}]({{ sa4.url | relative_url }})
  {% for outcome in site.data.outcomes %}
    - {{ outcome.label }}
    {% for year in site.data.years %}
      - Year {{ year }}
    {% endfor %}
  {% endfor %}
{% endfor %}