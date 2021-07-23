## DV2021 Daily Visa Statistics

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