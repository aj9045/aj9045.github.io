---
layout: post
title:  "Margin, Border, or Padding?"
date:   2014-08-17
tags: technical
categories: jekyll update
---

So how do we tell the difference between these three?  To aid our understanding, behold, the box model:

<img src="/assets/images/box-model.jpg" class="inline"><a style="display:none;">box model pic from http://www.w3schools.com/css/box-model.gif</a>


If we take a look at the model, in the middle we see <em>content</em>.  This one speaks for itself.  <em>Content</em> is where our text , like paragraphs, or images appear.

The next one out is <em>padding</em>. This is the area between our <em>content</em> and our <em>border</em>.  It literally "pads" the area around the <em>content</em> so the <em>content</em> doesn't reach the border (that is, if the <em>padding</em> isn't equal to zero.

Next, we have the <em>border</em>.  In the above image, it is represented by a thick, lime green line. This is exactly what you would think of when you hear the word "border."  It outlines the <em>padding</em>.  There are a lot of things you can do with the <em>border</em>.  For example, you could make the <em>border</em> small (1px), big (10px), dahsed, solid, different colors, etc.

Then on the outside, we have the <em>margin</em>.  This is the space that is between the <em>border</em> this element from those around it.

We can think of this kind of like a framed photograph.  The <em>content</em> is the actual photograph.  This could also be framed text, like song lyrics or a quote.  Surrounding the photo is the matting. This matting aroung the photo is the <em>padding</em>.  Of course, we don't always need matting to display a photo, and just like that, we can set the <em>padding</em> to zero, and the <em>border</em>, or frame, will touch the <em>content</em>, or photo.  <em>Borders</em> and <em>margins</em> may also be set to zero if we don't wish to use them.  So the <em>border</em>, in this analogy, is the frame, and so what would the <em>margin</em> be then?  Well, think about a row of three framed pictures hanging in a horizontal or vertical line on a wall.  How do they look?  Usually, they are a few inches apart so that the frames do not touch.  That space in between the frames is the <em>margin</em>.  It keeps the elements, the framed photos, from touching.

I hope this helped you understand margins, borders, and padding a little better!
