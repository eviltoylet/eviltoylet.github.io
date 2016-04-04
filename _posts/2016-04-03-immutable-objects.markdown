---
layout: post
title:  "Immutable Objects"
date:   2016-04-03 7:30:00 -0700
tags: immutable best-practice java
---

> "Perfection is immutable. But for things imperfect, change is the way to perfect them."
> - Owen Feltham

Given this, can we also say that immutability is perfection? In the world of programming, I'd like to think so. 
When things are immutable, they become easier to analyze, reason about, and plan for. 

# The Misused JavaBean
Unfortunately, most of the objects that programmers create are not immutable. They are in fact, highly mutable.
The most commonly used paradigm for Java objects is the [JavaBean.](https://en.wikipedia.org/wiki/JavaBeans) 
Here's an example:

{% highlight java %}
public class Employee {
    private String firstName;
    private String lastName;
    
    public Employee() {
    }
    
    public String getFirstName() {
        return firstName;
    }
    
    public String getLastName() {
        return lastName;
    }
    
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }
    
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }
}
{% endhighlight %}

The object has a zero-argument constructor and the appropriate methods to set the first and last names of the employee.
This pattern is most useful for programs in which users are interactively modifying the object, like in a WYSIWYG editor. 
For example, a `Button` class may represent an object that can be dragged and positioned on a page and then assigned 
some text and color.

However, outside of this domain, the JavaBean causes several problems. Here are just a few:

- the object can be constructed in an uninitialized and invalid state.
- code can perform inadvertent state modification.
- multi-threaded code needs synchronization to prevent race conditions on setters.

These may seem like minor issues, but they begin to snowball quickly into larger problems in complex systems. Fortunately,
it's very straightforward to make an object immutable.

# Making Objects Immutable
To make an object immutable, we can leverage Java's language features. The steps are:

1. Use the `final` keyword in the class declaration to prevent it from being overridden.
2. Declare all member variables as `private` and `final`.
3. List all of the required data to fully initialize the object in the constructor's argument list. Perform all initialization
at construction time.
4. Don't provide any methods that mutate state. For example, `public void initialize(...)` or `public void setValue(...).`
5. Return defensive copies of objects.

# Immutable Hash
One of my favorite outcomes of immutable objects is the fact that their hashes become immutable. 
Since hashes are computed from object fields, and these fields won't change, it's guaranteed that the hash of an 
immutable object does not change. Therefore, it is prudent to calculate and cache the hash during object construction.

{% highlight java %}
public final class Employee {
    private final String firstName;
    private final String lastName;
    private final int hashCode;
    
    public Employee(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
        this.hashCode = calculateHashCode();
    }
    
    private int calculateHashCode() {
        return Objects.hash(firstName, lastName);
    }
    
    @Override
    public int hashCode() {
        return hashCode;
    }
}
{% endhighlight %}

This reduces the additional overhead from calculating `hashCode()` to simply returning the cached value. Note that if
`hashCode()` isn't expected to be called, it will be more performant to use 
[lazy initialization](https://en.wikipedia.org/wiki/Lazy_initialization).

Immutable hashes also helps programmers skirt issues with data structures that employ `hashCode()`.
Often times, an object will be modified after being inserted into such a structure. For example, in a `HashSet`, the
table location for insertion is determined via the object hash. If the object changes after the fact, lookup of this
object will not work as expected.

Immutable objects really are perfect. And, as they say, perfection is immutable.

# References
- [Immutable Object - Wikipedia](https://en.wikipedia.org/wiki/Immutable_object)
