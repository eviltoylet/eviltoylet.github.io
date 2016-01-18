---
layout: post
title:  "Object-Oriented Developer"
date:   2016-1-17 11:07:00 -0800
tags: programming self-improvement object-oriented
---

# Becoming an Object-Oriented Developer
Given that [object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming) is the best thing since sliced bread, 
we should all strive to incorporate it into our lives. However, I'm not talking just about learning a language like Java or Ruby, I'm talking
about incorporating this phenomenal invention into our everyday lifestyle.

# Don't be a God Object
A [God Object](https://en.wikipedia.org/wiki/God_object) is one of the most despised anti-patterns. It's an object which knows or does too much.
Nobody likes a know-it-all. God objects are subject to the following problems: 

- doing everything poorly
- increased stress from increased responsibility

Where might it pay off? Being the go-to-person does mean that all of the information passes through you. In which case, you'll be privy to
a lot more information and can figure out which things you want to work on. For the ones you don't, intercept the information, and then
[proxy](http://thecodelesscode.com/case/216) it to someone else. Remember, it pays off to become a God interface, but not a God object.

# Be a Well-Documented, Self-Advertising, Dynamic Interface
Whether you like it or not, we're human interfaces for social interaction. Some of us support only the e-mail method, the chat method, 
the phone method, or the in-person method. Given how frustrating it is to interact with someone who *only* communicates via 
instant messaging, I'd recommend that you support all four, and then some.

With programs, it's very easy to get clients to conform to an interface. After all, that's often the client's only route to what it needs done.
In social interaction, people have a lot of choice. It is to your benefit to cater towards a wider variety of clients than you normally would.

Here are the common issues with interfaces and their remedies:

- *too many knobs and levers*. Having too many choices presents [The Paradox of Choice](https://en.wikipedia.org/wiki/The_Paradox_of_Choice).
Wouldn't it be great to have exactly the thing you want? This can be initiated by asking what is needed and when it's needed. This puts bounds on
functionality as well as performance. This would be a perfect interface:

{% highlight java %}
public interface Me {
    NeogtiatedOutput execute(NegotiatedInput input);
}
{% endhighlight %}

- *missing instructions.* Social interactions don't need documentation since they are innate. However, if you do something that
you consider different from the norm, document it every opportunity you get. Do you have additional capabilities? Let people know. 
- *missing functionality*. Often times, if an interface is missing some critical piece of functionality, people swear, then move on.
Even if you add it later, they won't know to come back. Advertise and document that it has been added.
- *useless output*. An interface that doesn't do the right job or gives you improper information is poorly designed. To work around this,
establish expectations on what is to be done and what the optimal output is. The client does not know best, so be open to negotiation.

But, reader beware. I'm not advising you to bend at the beck and call of everyone. Only open your interface up to the business *you* want.

# Abstraction for Tools
Put a uniform interface in front of everything that you interact with. This greatly simplifies your interaction with the world. For example, 
I end up using VIM a lot on remote servers for text operations. However, it's confusing to have to context switch between VIM modes and normal applications.
Therefore, I've opted to incorporate VIM into things like my [terminal](http://vim.wikia.com/wiki/Use_vi_shortcuts_in_terminal), and my 
[IDE](https://github.com/JetBrains/ideavim). Now I can seamlessly switch between tools and keep the same command set. 

For full-stack development, it has become very common to use isomorphic languages like [JavaScript](http://isomorphic.net/) 
to do both server-side and client-side development. Find areas in your life to refactor and simplify behind a common interface.

# Don't Stop There
I've only outlined a few of the strategies you can employ to make your life-style more object-oriented. Don't be afraid to extend
the metaphor and find more exciting optimizations for your life.
