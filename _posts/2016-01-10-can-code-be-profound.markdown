---
layout: post
title:  "Can Code Be Profound?"
date:   2016-1-10 15:33:00 -0800
tags: code improvement profound philosophy
---

It isn't unusual to see adjectives adorn the word *code*. Clean, testable, spaghetti, [ravioli](https://en.wikipedia.org/wiki/Spaghetti_code#Ravioli_code),
and maintainable are some of the most common that I've seen. But what about profound? Can code be profound?

# What makes profound?
Something that is profound contains significance and meaning far below its superficial one. For example:

> "It does not matter how slowly you go so long as you do not stop." - Confucius

On the surface, it is most assuredly common sense. However, given more thought, underlying stories begin to emerge. Was Confucius inferring
that tenacity is what's important? Whatever emotional response this quote provokes, it certainly is more than that from:

> "Brian drank water."

The largest difference between the two is that the former is more abstract than the latter. It's unclear what subject matter is being spoken about. 
Therefore, it's easy to map this into many different contexts. Yet, a statement that is too vague is easily overlooked, and may be disregarded as 
having no value.

> "Be like water."

But when given *just enough* details, it becomes surprisingly relevant.

> "Be like water making its way through cracks. Do not be assertive, but adjust to the object, and you shall find a way 
> around or through it. If nothing within you stays rigid, outward things will disclose themselves. - Bruce Lee

I assert that the following form the basis of profundity:

- can be applied to different contexts
- vague enough to be portable
- specific enough to be applicable
- elicit an emotional response

# Making code profound
At the outset, it would seem like code can't be deep. How can a very mathematical sequence of statements be interpreted otherwise?
It can't, not by machine at least. But by humans? Save for poorly written confusing code, there's little room for alternative
interpretations.

The following is code that counts from 1 to a given number. It does only that, and nothing else. 

{% highlight java %}
static void countFromOneTo(final int number) {
    final int startingNumber = 1;
    if (number < startingNumber) {
        throw new IllegalArgumentException("number needs to be >=: " 
        + startingNumber.toString());
    }
    
    for (int x = startingNumber; x <= number; x++) {
        System.out.println(number);
    }
}
{% endhighlight %}

From this starting point, we can *try* to make it more meaningful. Perhaps, if we switched the loop to take advantage of Java 8
`IntStream`s.

{% highlight java %}
IntStream.rangeClosed(startingNumber, number).forEach(i -> System.out.println(i));
{% endhighlight %}

Sure it introduced a new concept, but it isn't profound. This is just syntactic sugar and is no different than consulting
a thesaurus and writing "Brian quaffed water."

Perhaps this is too specific, let's find something more abstract. The granddaddy of all that is abstract, the Java `Object`, seems
like a great place to start. Yet, in object-oriented programming, everything is an object. So, we've gained no ground. Maybe we
aren't specific enough.

{% highlight java %}
interface Electronic {
    void turnOn();
    void turnOff();
}

public static void wasteElectricity(List<Electronic> electronics) {
    for (Electronic e : electronics) {
        e.turnOn();
    }
}

public static void main() {
    List<Electronic> electronics = new ArrayList<>();
    for (Object o : allObjects) {
        if (o instanceof Electronic) {
            electronics.add((Electronic) o);
        }
    }
    
    wasteElectricity(electronics);
}

{% endhighlight %}

I find the above code amazingly simple and deep at the same time. It allows me to sort out all the electronics from my bag
of objects, and turn them on. This `Electronic` interface can be applied to many contexts simply by augmenting it. It is vague enough to
be portable (e.g. it isn't `BatteryPoweredElectronic`) but specific enough to be applicable. In an object-oriented language,
well-abstracted and encapsulated code is profound. 

# Why should I care?

At the end of the day, a computer doesn't care if code is profound or not. It is a cold and calculating machine. It may 
very well remain this way until the [singularity](https://en.wikipedia.org/wiki/Technological_singularity). But until 
then, we the developers, are the very way that programs improve.

Profound statements invite change. They inspire and illuminate alternative ways to tackle problems. We must voraciously find, read, and share profound code.
