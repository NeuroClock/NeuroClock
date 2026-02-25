---
title: "Clock Lab - Team"
layout: gridlay
excerpt: "Clock Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

 **We are  looking for new PhD students, Postdocs, and Master students to join the team** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!**

Jump to [PI](#pi), [Postdoc](#postdoc), [PhD](#phd), [master](#master), [visitor](#visitor), [honorary](#honary), [alumni](#alumni)

## PI
{% assign pi = site.data.team_members | where: "role", "pi" | first %}
{% if pi %}
<div class="row" style="margin-bottom: 50px; border-bottom: 1px solid #ddd; padding-bottom: 20px;">
  <div class="col-sm-12">
    <h3>Principal Investigator</h3>
    <div class="clearfix">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ pi.photo }}" class="img-responsive" width="15%" style="float: left; margin-right: 20px;" />
      <h4>{{ pi.name }}</h4>
      <p style="line-height: 1.2;">
        {% if pi.email %}<strong>email:</strong> {{ pi.email }}<br>{% endif %}
        {% if pi.orcid %}<strong>orcid:</strong> {{ pi.orcid }}<br>{% endif %}
        {% if pi.linkedin %}<strong>linkedin:</strong> <a href="{{ pi.linkedin }}">Profile</a>{% endif %}
      </p>
    </div>
  </div>
</div>
{% endif %}

<h3>Team Members</h3>
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
  {% if member.role != "pi" %}
    {% assign even_odd = number_printed | modulo: 2 %}

    {% if even_odd == 0 %}
    <div class="row" style="margin-bottom: 30px;">
    {% endif %}

    <div class="col-sm-6 clearfix">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left; margin-right: 15px;" />
      <h4>{{ member.name }}</h4>
      <p style="font-size: 0.9em; line-height: 1.2;">
        {% if member.email %}<strong>email:</strong> {{ member.email }}<br>{% endif %}
        {% if member.orcid %}<strong>orcid:</strong> {{ member.orcid }}<br>{% endif %}
        {% if member.linkedin %}<strong>linkedin:</strong> <a href="{{ member.linkedin }}">Profile</a>{% endif %}
      </p>
    </div>

    {% assign number_printed = number_printed | plus: 1 %}
    {% if even_odd == 1 or forloop.last %}<div style="clear:both;"></div></div>{% endif %}
  {% endif %}
{% endfor %}

## Master and Bachelor Students
{% assign number_printed = 0 %}
{% for member in site.data.students %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }} <!-- <br>email: <{{ member.email }}></i> -->
  <ul style="overflow: hidden">

  {% if member.number_educ == 1 %}
  <li> {{ member.education1 }} </li>
  {% endif %}

  {% if member.number_educ == 2 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  {% endif %}

  {% if member.number_educ == 3 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  <li> {{ member.education3 }} </li>
  {% endif %}

  {% if member.number_educ == 4 %}
  <li> {{ member.education1 }} </li>
  <li> {{ member.education2 }} </li>
  <li> {{ member.education3 }} </li>
  <li> {{ member.education4 }} </li>
  {% endif %}

  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}


## Alumni

{% assign number_printed = 0 %}
{% for member in site.data.alumni_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4>{{ member.name }}</h4>
  <i>{{ member.duration }} <br> Role: {{ member.info }}</i>
  <ul style="overflow: hidden">

  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

## Former visitors, BSc/ MSc students
<div class="row">

<div class="col-sm-4 clearfix">
<h4>Visitors</h4>
{% for member in site.data.alumni_visitors %}
{{ member.name }}
{% endfor %}
</div>

<div class="col-sm-4 clearfix">
<h4>Master students</h4>
{% for member in site.data.alumni_msc %}
{{ member.name }}
{% endfor %}
</div>

<div class="col-sm-4 clearfix">
<h4>Bachelor Students</h4>
{% for member in site.data.alumni_bsc %}
{{ member.name }}
{% endfor %}
</div>

</div>


## Administrative Support
<a href="mailto:Rijsewijk@Physics.LeidenUniv.nl">Ellie van Rijsewijk</a> is helping us (and other groups) with administration.
