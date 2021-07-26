## DV2021 Daily Visa Statistics Summary Table

```markdown
Last updated on {{ site.data.stats.updated_date }}
```

Region | AP      | Issued      | Ready       | Refused   | Transit | Total       | Regional<br />Quota | %2NL
-------|---------|-------------|-------------|-----------|---------|-------------|---------------------|-----
{% for region in site.data.stats.summary -%}
{{ region.label }} | {{ region.ap.cases }} <br /> {{ region.ap.visas }} | {{ region.issued.cases }} <br /> {{ region.issued.visas }} | {{ region.ready.cases }} <br /> {{ region.ready.visas }} | {{ region.refused.cases }} <br /> {{ region.refused.visas }} | {{ region.transit }} | {{ region.total.cases }} <br /> {{ region.total.visas }} | {{ region.quota }} | {{ region.quota_percentage }}
{% endfor %}

When the field has two lines, the first line represents the number of cases, and the second line
represents the number of visas. The **Regional Quota** represents number of visas. The cases in
**Transit** represents the number of cases.

## Second Notification Letters (2NLs)

These are the second letter notifications for each region:

{% if site.data.stats.2nl.af == 0 %}
- There are no new 2NLs for the AF region today.
{% elsif site.data.stats.2nl.af == 1 %}
- There is 1 new 2NL for the AF region today.
{% else %}
- There are **{{ site.data.stats.2nl.af }} new 2NLs for the AF** region today.
{% endif %}

{% if site.data.stats.2nl.as == 0 %}
- There are no new 2NLs for the AS region today.
{% elsif site.data.stats.2nl.as == 1 %}
- There is 1 new 2NL for the AS region today.
{% else %}
- There are **{{ site.data.stats.2nl.as }} new 2NLs for the AS** region today.
{% endif %}

{% if site.data.stats.2nl.eu == 0 %}
- There are no new 2NLs for the EU region today.
{% elsif site.data.stats.2nl.eu == 1 %}
- There is 1 new 2NL for the EU region today.
{% else %}
- There are **{{ site.data.stats.2nl.eu }} new 2NLs for the EU** region today.
{% endif %}

{% if site.data.stats.2nl.na == 0 %}
- There are no new 2NLs for the NA region today.
{% elsif site.data.stats.2nl.na == 1 %}
- There is 1 new 2NL for the NA region today.
{% else %}
- There are **{{ site.data.stats.2nl.na }} new 2NLs for the NA** region today.
{% endif %}

{% if site.data.stats.2nl.oc == 0 %}
- There are no new 2NLs for the OC region today.
{% elsif site.data.stats.2nl.oc == 1 %}
- There is 1 new 2NL for the OC region today.
{% else %}
- There are **{{ site.data.stats.2nl.oc }} new 2NLs for the OC** region today.
{% endif %}

{% if site.data.stats.2nl.sa == 0 %}
- There are no new 2NLs for the SA region today.
{% elsif site.data.stats.2nl.sa == 1 %}
- There is 1 new 2NL for the SA region today.
{% else %}
- There are **{{ site.data.stats.2nl.sa }} new 2NLs for the SA** region today.
{% endif %}

{% if site.data.stats.2nl.af > 0 or site.data.stats.2nl.as > 0 or site.data.stats.2nl.eu > 0 or site.data.stats.2nl.na > 0 or site.data.stats.2nl.oc > 0 or site.data.stats.2nl.sa > 0 %}
Congratulations to everyone who received their 2NL!!!
{% endif %}
