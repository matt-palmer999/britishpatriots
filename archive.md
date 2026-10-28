---
layout: default
title: Archive
description: Every Daily Patriot story published so far, newest first and grouped by month.
permalink: /archive/
---
<div class="container">
<div style="max-width:720px;margin:40px auto;">

<h2 style="font-family:'Playfair Display',serif;font-weight:900;font-size:36px;margin-bottom:6px;text-align:center;">The Archive</h2>
<p style="font-family:'Barlow Condensed',sans-serif;font-size:13px;letter-spacing:.15em;text-transform:uppercase;color:#B8860B;text-align:center;margin-bottom:30px;">Every story we have published, newest first</p>

{% assign months = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for month in months %}
<h3 style="font-family:'Barlow Condensed',sans-serif;font-weight:800;font-size:13px;letter-spacing:.2em;text-transform:uppercase;color:var(--mid-grey);border-bottom:1px solid var(--border);padding-bottom:6px;margin:28px 0 8px;">{{ month.name }}</h3>
<ul style="list-style:none;padding:0;margin:0 0 8px;">
  {% for post in month.items %}
  <li style="padding:10px 0;border-bottom:1px solid var(--border);">
    <div style="font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gold);margin-bottom:3px;">{{ post.category }} &middot; {{ post.date | date: "%-d %B %Y" }}</div>
    <a href="{{ post.url }}" style="font-family:'Playfair Display',serif;font-weight:700;font-size:18px;line-height:1.25;color:var(--navy);text-decoration:none;">{{ post.title }}</a>
  </li>
  {% endfor %}
</ul>
{% endfor %}

</div>
</div>
