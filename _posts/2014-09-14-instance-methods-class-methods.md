---
layout: post
title:  "Instance Methods? Class Methods?"
date:   2014-09-14
categories: jekyll update
tags: technical
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---

In an earlier post, I talked a bit about classes in Ruby.  And now I'm going to talk about instance methods and class methods.

Classes are great for organizing and collecting objects.  These objects can include instance methods (instances of a class), which just means methods inside classes.  They function in a similar way as methods outside of a class, except they will only work on objects of the class they are in. For example:

{% highlight ruby %}
  class Cat
    def initialize(breed, name)
      @breed = breed
      @name = name
    end

    def list
      "#{@breed} -- #{@name}"
    end
  end

  lola = Cat.new("Ragdoll", "Lola")

  puts lola.list
    #=> Ragdoll -- Lola
{% endhighlight %}

Notice that the method 'list' works with the new Cat object 'lola' because that method exists within the Cat class.

Also, you may have noticed the initialize method.  This is one of Ruby's built-in instance methods that runs every time a new object of that class is created. So in this case, once 'lola' was created, instance variables for both arguments were made in order to be used with the other instance methods.

Class methods are different than instance methods because they are called on a class, not an instance of a class.  Here we can see the difference between the two, as a class method will use either the class name or 'self.'

{% highlight ruby %}
  class Cat
    def self.name(name)
      puts name
    end

    def breed(breed)
      puts breed
    end
  end

  puts Cat.name("Lola")
    #=> Lola
  puts Cat.breed("Ragdoll")
    #=>undefined method `breed' for Cat:Class (NoMethodError) Lola
{% endhighlight %}

You might have noticed that the instance method 'breed' is in the Cat class. Because the method 'breed' is not a class method, calling it on the class will not work. However, the opposite will happen if we try to create a new object for the Cat class.

{% highlight ruby %}
  class Cat
    def self.name(name)
      puts name
    end

    def breed(breed)
      puts breed
    end
  end

  puts Cat.new.name("Lola")
    #=> undefined method `name' for #<Cat:0x007fec598aa848> (NoMethodError)
  puts Cat.new.breed("Ragdoll")
    #=> Ragdoll
{% endhighlight %}

So when would you use a class method?  Here's an example, where this class method ('count') tells you information about the class objects (how many have been created).

{% highlight ruby %}
  class Cat
    @@count = 0

    def initialize(breed, name)
      @breed = breed
      @name = name
      @@count += 1
    end

    def list
      "#{@breed} -- #{@name}"
    end

    def self.count
      p @@count
    end
  end

  lola = Cat.new("ragdoll", "lola")
  dakota = Cat.new("savannah cat", "dakota")

  Cat.count
    #=> 2
{% endhighlight %}

The class Cat is an object (like most everything in Ruby), and therefore, it gets its own methods to look across itself, which is made up of multiple instances.  This is why a class method is used instead of an instance method to count all new instances of the class.