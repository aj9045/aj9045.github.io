---
layout: post
title:  "A bit about Enumerable#cycle"
date:   2014-08-31
categories: jekyll update
<!-- tags: featured -->
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---

This is a pretty cool method, if I do say so myself.  It does exactly what you think it would do based on its name.  Similar to the each method, you can cycle through an array and do something to it using a block.  If no block is given, it will return an enumerator.  However, if there is a block but no argument, it creates an infinite loop.

{% highlight ruby %}
  a = [1,3,7,9]

  a.cycle { |x| print x }
  #=> 13791379137913791379.....infinitely
{% endhighlight %}

The argument is there to say how many times the cycle will run, how many times it will run through the elements in the array.  With each, once you run through each element in the array once, it ends.

{% highlight ruby %}
  a.each { |x| puts x }
  #=> 1
  #=> 3
  #=> 7
  #=> 9
{% endhighlight %}

But you can run through them as many times as you'd like using cycle.

{% highlight ruby %}
  a.cycle(2) { |x| puts x }
  #=> 1
  #=> 3
  #=> 7
  #=> 9
  #=> 1
  #=> 3
  #=> 7
  #=> 9
{% endhighlight %}

This is also true when using other methods in conjunction with cycle, like next.  If you use each to go through the elements, once you hit the last elemnt, it will stop because it's literally gone through each element and will do no more.

{% highlight ruby %}
  b = ["a","b","c"]

  run_once = b.each

  puts run_once.next
  #=> a
  puts run_once.next
  #=> b
  puts run_once.next
  #=> c
  puts run_once.next
  #=> iteration reached an end (StopIteration)
{% endhighlight %}

However, if you use next with cycle, it will just  keep going to the next element even if that means starting from the beginning of the array again.

{% highlight ruby %}
  run_more = b.cycle

  puts run_more.next
  #=> a
  puts run_more.next
  #=> b
  puts run_more.next
  #=> c
  puts run_more.next
  #=> a
{% endhighlight %}

And like each, you can do more than just print out each element.  For example, adding 3 to each element:

{% highlight ruby %}
  a = [1,3,7,9]

  a.cycle(3) { |x| puts x + 3 }
  #=> 4
  #=> 6
  #=> 10
  #=> 12
  #=> 4
  #=> 6
  #=> 10
  #=> 12
  #=> 4
  #=> 6
  #=> 10
  #=> 12
{% endhighlight %}

Another cool thing is that you can cycle through the array backwards without any problem by chaining methods:

{% highlight ruby %}
  a.reverse_each.cycle(2) { |x| puts x + 3 }
  #=> 12
  #=> 10
  #=> 6
  #=> 4
  #=> 12
  #=> 10
  #=> 6
  #=> 4
{% endhighlight %}

I actually hadn't even used this method before I decided to do a post on it.  So, this blog post was also a learning experience for me.  Cool beans, eh?