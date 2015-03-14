---
layout: page
title: About
permalink: /about/
---

<div class="page-content">
  <div class="wrapper">
    {% for social in site.social %}
      {% if social.url %}
        <a class="icon-{{ social.icon }} social" href="{{ social.url }}">
          <i class="fa fa-{{ social.icon }}"></i>
        </a>
        &nbsp;&nbsp;&nbsp;
      {% endif %}
    {% endfor %}
  </div>
</div>

<p></p>

<img src="/assets/images/me.jpg">
Hey all! My name is AJ Stuhrenberg. I'm a 22-year old recent graduate from Hobart & William Smith Colleges where I graduated with a BA in Asian studies and a minor in studio art. Although my school was in upsate New York, I've lived in Atlanta, GA most of my life. I also recently just graduated from Dev Bootcamp, an 18 week web development intensive learning experience, this past December. This is all very, very new to me, but I'm ready to learn even more! Please feel free to contact me with questions, comments, or anything else!



