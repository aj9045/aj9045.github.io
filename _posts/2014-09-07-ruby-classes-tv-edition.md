---
layout: post
title:  "Ruby Classes: TV Edition"
date:   2014-09-07
categories: jekyll update
tags: technical
image: /assets/article_images/black-and-white-storm.jpg
---

Classes in Ruby are a good way to organize and create a collection of methods that will only work inside that class.  We may also make objects that will work for all of these various methods within the same class called instance variables.

To create a class, we start with the keyword 'class' followed by the name we want to give our class.  This name follows the CamelCase convention, where the first letter of each word is uppercase, and there are no spaces between words.  Like methods, when creating a class, it must end with the 'end' keyword.

{% highlight ruby %}
  class FavTVShows
    def initialize(show_title, num_of_seasons, start_date, end_date)
      @show_title = show_title
      @start_date = start_date
      @end_date = end_date
    end
  end
{% endhighlight %}

The initialize method allows us to create a new instance of an object in the FavTVShows class.  It can also create instance variables (they start with an @ symbol) from the arguments so that we can use them throughout in other methods in the class.  We can create a new instance by simply using '.new' along with the right number of arguments needed from the initialize method.

{% highlight ruby %}
  supernatural = FavTVShows.new("Supernatural", 10, 2005, "ongoing")
{% endhighlight %}

After the initialize method, you will want to create other methods in order to access/change/sort/whatever information about new instances of that class.  So for example, I want to be able to access the show's name, how many seasons there are/were, the starting date, and the end date, as well as a summary of the information given.  And if the show hasn't ended yet, I want it to return "This show has not ended yet."

{% highlight ruby %}

class FavTVShows
  def initialize(show_title, num_of_seasons, start_date, end_date="This show has not ended
  yet.")
    @show_title = show_title
    @num_of_seasons = num_of_seasons
    @start_date = start_date
    @end_date = end_date
  end

  def show_title
    @show_title
  end

  def num_of_seasons
    @num_of_seasons
  end

  def start_date
    @start_date
  end

  def end_date
    @end_date.is_a?(Integer) ? @end_date : "This show has not ended yet."
  end

  def about_show
    if @end_date.is_a?(Integer)
      "The TV show #{@show_title} started in #{@start_date}, ended in #{@end_date}, and has
      aired #{@num_of_seasons} season(s)."
    else
      "#{@show_title} is an ongoing TV series that started in #{@start_date}, and has aired
      #{@num_of_seasons} season(s)."
    end
  end
end

{% endhighlight %}

The show\_title, start\_date, and num\_of\_seasons methods are very simple.  They return the value of the corresponding arguments when called.  The end\_date method and about\_show method are a little more complicated.  For the end\_date method, I used the ternary operator for the if/else statement which says if the argument for end\_date is an integer, then it will return the value for end\_date.  If it not, then it will return a string saying that the show hasn't ended.  For the about\_show method, I put in another if/else statement in order to summarize the info about the show.  If the end\_date is an integer, that means that the show must have ended.  Therefore, it will return a string with the end\_date.  If it's not a string, then the string will not contain the end\_date, and instead say that it's an ongoing show.

Notice I was able to use the arguments from the new instance in the other methods in the class. This is what is returned when I call each of the methods:

{% highlight ruby %}
  puts supernatural.show_title
   #=> Supernatural
  puts supernatural.num_of_seasons
   #=> 10
  puts supernatural.start_date
   #=> 2005
  puts supernatural.end_date
   #=> This show has not ended yet.
  puts supernatural.end_date
   #=> Supernatural is an ongoing TV series that started in 2005, and has aired 10 season(s).
{% endhighlight %}

I also set the end\_date argument to a string.  The reason I did this was to have supernatural.end\_date return that string if that argument wasn't included in the new instance. Notice that for this next example, I don't put in the argument for end\_date.

{% highlight ruby %}
  castle = FavTVShows.new("Castle", 7, 2009)

  puts castle.show_title
   #=> Castle
  puts castle.num_of_seasons
   #=> 7
  puts castle.start_date
   #=> 2009
  puts castle.end_date
   #=> This show has not ended yet.
  puts castle.about_show
   #=> Castle is an ongoing TV series that started in 2009, and has aired 7 season(s).
{% endhighlight %}

So both Castle and Supernatural are ongoing shows.  So what about a show that has ended?

{% highlight ruby %}
  psych = FavTVShows.new("Psych", 8, 2006, 2014)

  puts psych.show_title
   #=> Psych
  puts psych.num_of_seasons
   #=> 8
  puts psych.start_date
   #=> 2006
  puts psych.end_date
   #=> 2014
  puts psych.about_show
   #=> The TV show Psych started in 2006, ended in 2014, and has aired 8 season(s).
{% endhighlight %}

Because I have created this class, I can add Leverage and Breakout Kings and Lost Girl--I can actually add as many new objects to the FavTVShows class that I want without having to use repetitive and unnecessary code.  Pretty cool, huh?