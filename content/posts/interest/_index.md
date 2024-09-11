+++
title='有趣的事情'
sort_by = "date"
+++

{% set posts_by_year = section.pages | group_by(attribute="year") %}
{% set_global years = [] %}
{% for year, ignored in posts_by_year %}
    {% set_global years = years | concat(with=year) %}
{% endfor %}
{% for year in years | reverse %}
    {% set posts = posts_by_year[year] %}
    {# (same as the previous snippet) #}
{% endfor %}
