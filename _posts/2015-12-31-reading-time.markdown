---
layout: post
title:  "Reading Time"
date:   2015-12-31 19:21:00 -0800
tags: reading programming optimization jekyll
---

A majority of readers and writers are now utilizing a side called [Medium](http://www.medium.com). One of the most interesting metrics that they have at the top of every page
is [reading time](https://medium.com/the-story/read-time-and-you-bc2048ab620c). It's quite clever since it allows a reader to decide whether or not they want to make that time commitment.
This is similar to the estimated time remaining present on Amazon Kindles. Seeing as this type of calculation might be useful for my blog posts, I decided to set out to do it.

# Reading Speed Calculation

Let's completely disregard the numbers in the Medium article on reading time, because it's funner to do things ourselves! A cursory internet search reveals that the average reading speed is 300 words per minute.
So, let's use that for the basis of our calculation. So, all we have to do is take the number of words in each of our posts and divide it by 300 to get the number of minutes it would take the average reader.

# Jekyll Code
How do we do this in Jekyll? The default layout has each blog post templated by `_layouts/post.html`. Simply add the following code snippet to the section that you want it to appear in. It takes advantage of using filters to perform the calculation.
Note that I'm also just getting started with Jekyll, so I have no idea if this is the idiomatic way to do this.

{% highlight liquid %}
{% raw %}
{{ content | number_of_words | divided_by: 300.0 | ceil }} min read
{% endraw %}
{% endhighlight %}

I decided to round the final result up to handle the case where the number of words is less than the average reading speed. This is to prevent text like `0.34 min read` from being mistaken as a 34 minute read. 
Plus, who really cares about those fractional minutes anyway?!

# Now What?
Adding the reading speed is quick and valuable to the user. However, further improvements don't seem as necessary, especially for short form content. Nonetheless, here are some other thoughts I had:

- Use the calculated reading speed as just a seed. Start using real user data to provide a better number since reading speed and comprehension speed are different.
- Provide a range for reading speed. There are definitely speed readers and sloth readers out there.
