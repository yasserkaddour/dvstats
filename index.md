## DV2021 Daily Visa Statistics Summary Table

```markdown
Last updated on {{ site.data.stats.updated_date }}
```

Region | AP      | Issued      | Ready       | Refused   | Transit | Total       | Regional<br />Quota | %2NL
-------|---------|-------------|-------------|-----------|---------|-------------|---------------------|-----
{% for region in site.data.stats.summary -%}
**{{ region.label }}** | {{ region.ap.cases }} <br /> **{{ region.ap.visas }}** | {{ region.issued.cases }} <br /> **{{ region.issued.visas }}** | {{ region.ready.cases }} <br /> **{{ region.ready.visas }}** | {{ region.refused.cases }} <br /> **{{ region.refused.visas }}** | {{ region.transit }} | {{ region.total.cases }} <br /> **{{ region.total.visas }}** | **{{ region.quota }}** | **{{ region.quota_percentage }}**
{% endfor %}

When the field has two lines, the first line represents the number of cases, and the second line
represents the number of visas. Values for number of visas are displayed in **bold** font.
The **Regional Quota** represents number of visas. The cases in **Transit** represents the number of cases.

## Second Notification Letters (2NLs)

These are the second notification letters sent out for each region:

{% if site.data.stats.2nl.af == 0 %}
- There are no new 2NLs for the AF region today.
{% elsif site.data.stats.2nl.af == 1 %}
- There is **1 new 2NL for the AF** region today.
{% else %}
- There are **{{ site.data.stats.2nl.af }} new 2NLs for the AF** region today.
{% endif %}

{% if site.data.stats.2nl.as == 0 %}
- There are no new 2NLs for the AS region today.
{% elsif site.data.stats.2nl.as == 1 %}
- There is **1 new 2NL for the AS** region today.
{% else %}
- There are **{{ site.data.stats.2nl.as }} new 2NLs for the AS** region today.
{% endif %}

{% if site.data.stats.2nl.eu == 0 %}
- There are no new 2NLs for the EU region today.
{% elsif site.data.stats.2nl.eu == 1 %}
- There is **1 new 2NL for the EU** region today.
{% else %}
- There are **{{ site.data.stats.2nl.eu }} new 2NLs for the EU** region today.
{% endif %}

{% if site.data.stats.2nl.na == 0 %}
- There are no new 2NLs for the NA region today.
{% elsif site.data.stats.2nl.na == 1 %}
- There is **1 new 2NL for the NA** region today.
{% else %}
- There are **{{ site.data.stats.2nl.na }} new 2NLs for the NA** region today.
{% endif %}

{% if site.data.stats.2nl.oc == 0 %}
- There are no new 2NLs for the OC region today.
{% elsif site.data.stats.2nl.oc == 1 %}
- There is **1 new 2NL for the OC** region today.
{% else %}
- There are **{{ site.data.stats.2nl.oc }} new 2NLs for the OC** region today.
{% endif %}

{% if site.data.stats.2nl.sa == 0 %}
- There are no new 2NLs for the SA region today.
{% elsif site.data.stats.2nl.sa == 1 %}
- There is **1 new 2NL for the SA** region today.
{% else %}
- There are **{{ site.data.stats.2nl.sa }} new 2NLs for the SA** region today.
{% endif %}

{% if site.data.stats.2nl.af > 0 or site.data.stats.2nl.as > 0 or site.data.stats.2nl.eu > 0 or site.data.stats.2nl.na > 0 or site.data.stats.2nl.oc > 0 or site.data.stats.2nl.sa > 0 %}
Congratulations to everyone who received their 2NL!!!
{% endif %}

{% if site.data.stats.accepted.size > 0 %}
## Accepted cases by consular post

The following summarizes the posts that have accepted cases today.

Region |                Country              |  Cases |  Visas
-------|-------------------------------------|--------|-------
{% for accepted in site.data.stats.accepted -%}
**{{ accepted.region }}** | {{ accepted.country }} | {{ accepted.cases }} | **{{ accepted.visas }}**
{% endfor %}
{% endif %}

## Statistics per consular post

The following tables show statistics per consular post. There is one summary table
per region.

#### Africa (AF) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in site.data.stats.country_stats.af -%}
 **{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = site.data.stats.country_stats.af.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the AF region.

#### Asia (AS) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in site.data.stats.country_stats.as -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = site.data.stats.country_stats.as.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the AS region.

#### Europe (EU) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in site.data.stats.country_stats.eu -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = site.data.stats.country_stats.eu.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the EU region.

#### North America (NA) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in site.data.stats.country_stats.na -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = site.data.stats.country_stats.na.size | minus: 1 %}
{{ posts }} consular post has accepted cases for the NA region.

#### Oceania (OC) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in site.data.stats.country_stats.oc -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = site.data.stats.country_stats.oc.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the OC region.

#### South America (SA) region

Post |                Country              | Issued | AP | Ready | Refused | Total
-----|-------------------------------------|--------|----|-------|---------|-------
{% for country in site.data.stats.country_stats.sa -%}
**{{ country.post }}** | {{ country.country }} | {{ country.issuedCases }} <br /> **{{ country.issuedVisas }}** | {{ country.apCases }} <br /> **{{ country.apVisas }}** | {{ country.readyCases }} <br /> **{{ country.readyVisas }}** | {{ country.refusedCases }} <br /> **{{ country.refusedVisas }}** | {{ country.totalCases }} <br /> **{{ country.totalVisas }}**
{% endfor %}

{% assign posts = site.data.stats.country_stats.sa.size | minus: 1 %}
{{ posts }} consular posts have accepted cases for the SA region.