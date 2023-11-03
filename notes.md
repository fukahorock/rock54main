---
title: "雑記"
permalink: /notes
layout: page
---
雑記など。  
旅行記やコラム？など、特定のカテゴリのコンテンツはピックアップしてまとめます。

## 海外旅行記
一部のものはPIXIV FANBOXから移設（予定）

- [【ベトナム】2019年1月 ベトナム縦断旅行記](https://fukahorock.rock54.net/notes/2019vietnam/)

## 雑記

<div id="archives">
  <section id="archive">
      {%for post in site.posts %}
      {% unless post.next %}
      <ul class="this">
          {% else %}
          {% capture month %}{{ post.date | date: '%B %Y' }}{% endcapture %}
          {% capture nmonth %}{{ post.next.date | date: '%B %Y' }}{% endcapture %}
          {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
          {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
          {% if year != nyear %}
      </ul>
      <h2 style="text-align:left;">{{ post.date | date: '%Y' }}</h2>
      <ul class="past">
          {% endif %}
          {% endunless %}
          <li><b><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></b> ({% if post.date and post.date != "" %}{{ post.date | date: "%Y/%m/%d" }}{%endif%})</li>
          {% endfor %}
      </ul>
  </section>
</div>
