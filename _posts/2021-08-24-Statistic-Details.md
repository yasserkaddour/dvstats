---
layout: posts
title:  "DV2021 Statistic Details for 2021-08-24"
pageScript: |
  var el = document.querySelector('div#updated_date').nextElementSibling.querySelector('span.gs');
  var m = moment(el.innerHTML.replaceAll('*', ''));
  el.innerHTML = m.format('LLL');
---
{% assign data = site.data.posts.stats1629831604500 %}

## 2021-08-24 Statistics Summary Table

<div id="updated_date"></div>
```markdown
Last updated on **{{ data.updated_date }}**
```

Region | AP      | Issued      | Ready       | Refused   | Transit | Total       | Regional<br />Quota | %2NL
-------|---------|-------------|-------------|-----------|---------|-------------|---------------------|-----
{% for region in data.summary -%}
**{{ region.label }}** | {{ region.ap.cases }} <br /> **{{ region.ap.visas }}** | {{ region.issued.cases }} <br /> **{{ region.issued.visas }}** | {{ region.ready.cases }} <br /> **{{ region.ready.visas }}** | {{ region.refused.cases }} <br /> **{{ region.refused.visas }}** | {{ region.transit }} | {{ region.total.cases }} <br /> **{{ region.total.visas }}** | **{{ region.quota }}** | **{{ region.quota_percentage }}**
{% endfor %}

When the field has two lines, the first line represents the number of cases, and the second line
represents the number of visas. Values for number of visas are displayed in **bold** font.
The **Regional Quota** represents number of visas allocated for each region.
The number in the **Transit** column represent the number of cases.

## Second Notification Letters (2NLs)

These are the second notification letters sent out for each region:

{% for region in data.2nl %}
{% if region.cases %}
{% if region.cases.size == 1 %}
- There is **1 new 2NL for the {{ region.region }}** region today.
{% else %}
- There are **{{ region.cases.size }} new 2NLs for the {{ region.region }}** region today.
{% endif %}
{% else %}
- There are no new 2NLs for the {{ region.region }} region today.
{% endif %}
{% endfor %}

{% if data.2nl[0].cases or data.2nl[1].cases or data.2nl[2].cases or data.2nl[3].cases or data.2nl[4].cases or data.2nl[5].cases %}
Congratulations to everyone who received their 2NL!!!
{% endif %}

{% if data.accepted.size > 0 %}
## Accepted cases by consular post

The following table summarizes the consular posts that have accepted cases **today**.

Region |                Country              |  Cases |  Visas
-------|-------------------------------------|--------|-------
{% for accepted in data.accepted -%}
**{{ accepted.region }}** | {{ accepted.country }} | {{ accepted.cases }} | **{{ accepted.visas }}**
{% endfor %}
{% endif %}

{% if data.2nl[0].cases or data.2nl[1].cases or data.2nl[2].cases or data.2nl[3].cases or data.2nl[4].cases or data.2nl[5].cases %}

## Second Notification Letter Details

{% for region in data.2nl %}
{% if region.cases %}
#### {{ region.region }} region

{% for case in region.cases %}
- {{ case }}
{% endfor %}
{% endif %}

{% endfor %}
{% endif %}

## Statistics per consular post

The following tables show statistics per consular post. There is one summary table
per region.

#### Africa (AF) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in data.country_stats.af -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = data.country_stats.af.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the AF region.

#### Asia (AS) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in data.country_stats.as -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = data.country_stats.as.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the AS region.

#### Europe (EU) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in data.country_stats.eu -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = data.country_stats.eu.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the EU region.

#### North America (NA) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in data.country_stats.na -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = data.country_stats.na.size | minus: 1 %}
{{ posts }} consular post has accepted cases for the NA region.

#### Oceania (OC) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in data.country_stats.oc -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = data.country_stats.oc.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the OC region.

#### South America (SA) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in data.country_stats.sa -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = data.country_stats.sa.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the SA region.