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
    <a href="https://drive.google.com/file/d/0BynilUjCLRF9ekRIV0o3YXk1bUE/view?usp=sharing" target="_blank">Resume</a>
  </div>
</div>

<p></p>

<img src="/assets/images/me.jpg" class="inline-blog-img">
Hey all! My name is AJ Stuhrenberg. I recently  graduated from Dev Bootcamp, an 18 week web development intensive learning experience, in December of 2014, where I learned a good amount of Ruby, Rails, JavaScript, HTML5, and CSS3.  And most recently, I worked at Texts.com, a small startup in NYC.  I developed the first versions of their iOS and Android apps using React Native.  And I am always looking to learn more!  Right now, I'm brushing up on JavaScript, ReactJS, and learning Redux.  Please feel free to contact me with questions, comments, or anything else.