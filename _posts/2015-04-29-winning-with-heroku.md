---
layout: post
title:  "Winning With Heroku"
date:   2015-04-29
tags: heroku unicorn errors
---

Well I am certainly learning today.  I decided to deploy my app that I'm working on, called PhotoFinish, on Heroku today using Unicorn.

Let's just list some of the things that I forgot.

1. <a href="https://devcenter.heroku.com/articles/procfile">Procfiles</a> are a thing.

2. Bundling is important.

3. If you're getting a "We're sorry but something went wrong" message, and you feel like you haven't done anything wrong, it's probably because you <a href="http://stackoverflow.com/questions/20924389/heroku-were-sorry-but-something-went-wrong">forgot to migrate your shit</a>. So run: <span class="keyword">heroku run rake db:migrate</span>, and then try to <span class="keyword">heroku open</span> again.


4. if you CSS isn't showing up, you might need <a href="https://devcenter.heroku.com/articles/ruby-support#injected-plugins">this</a>: <span class="keyword">gem 'rails_12factor'</span>



I haven't deployed anything to Heroku in a bit, so some of these things made me feel like this:
<img src="/assets/images/idiot.gif">
Just some things to remember for next time, I reckon.