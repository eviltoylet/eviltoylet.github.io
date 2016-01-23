---
layout: post
title:  "How to Future-Proof Your Code"
date:   2016-1-23 13:36:00 -0800
tags: programming code future-proof 
---

Computer code is much like written literature. The excellent ones are kept around to be studied and revered by 
generations to come while the remainder are sentenced to obscurity. Perhaps you're working on a coding project of
Shakespearian importance. What steps should you take to make sure your ingenuity and forward-thinking are preserved?

# The Difficulty of Future-Proofing
It's hard to anticipate the next trendy language, framework, or coding paradigm. Therefore, even though you
may write a masterpiece, subsequent readers may have difficulty understanding it. Take
[William Shakespeare](https://en.wikipedia.org/wiki/William_Shakespeare) for example. He's widely regarded as the
greatest writer in the English language, yet many now have difficulty reading his works. The primary reason is that 
they're written in [Early Modern English](https://en.wikipedia.org/wiki/Early_Modern_English) which differ in vocabulary 
and grammar when compared to contemporary English. However, for those well versed in the language, Shakespeare's works 
are very accessible.

"How does that pertain to code?" you might ask. And you would be correct in questioning that. Like it or not, even
programming languages evolve. Here are some C++ snippets to multiply a list of numbers by 2:

**C++03**
{% highlight c++ %}
int numbers[5] = {1, 2, 3, 4, 5};

for (int x = 0; x < sizeof(numbers)/sizeof(numbers[0]); x++) { 
    numbers[x] *= 2;
} 
{% endhighlight %}

**C++11**
{% highlight c++ %}
int numbers[5] = {1, 2, 3, 4, 5};

for (auto &number : numbers) {
    numbers *= 2;
}
{% endhighlight %}

For those who have witnessed the evolution of C++, there is no cognitive dissonance. However, for a young whippersnapper,
the C++03 syntax is clearly baffling and inferior.

# Difference Between Code and Literature
Literature is read by humans. Code is read by machines. Humans care if their reading material is enlightening, profound,
exciting, and entertaining. Machines, not so much. So, for a machine, there isn't any functional difference between 
these two code fragments that multiply the number 16 by 2.

{% highlight c++ %}
int number = 16;
number *= 2;
{% endhighlight %}
{% highlight c++ %}
int number = 0x10;
number <<= 1;
{% endhighlight %}

# Make Code Simple
Code is read by humans but only strictly for adding or fixing functionality. Sure, sure, for some people the more 
obscure version of number multiplication is more stimulating, but it isn't for most. The code you write should not
be for entertainment. It should be pedestrian and easy to understand. Always default to using the most basic of building
blocks, even if it means more verbosity. The point here is that your code should be the literary equivalent of:

{% highlight plaintext %}
This is John. John is fat. John is always hungry. 
John eats 100 slices of bread. 
John is still hungry.
{% endhighlight %}

instead of:
{% highlight plaintext %}
John, a rather portly fellow, has never been able to satiate his stomach. 
Despite eating a hundred slices of wheat byproduct, he was still famished.
{% endhighlight %}

This makes it more straightforward to translate into another language. Because one day your language of choice will 
become obsolete. Do you want to be a relic of the past, or do you want to modernize for the future?

