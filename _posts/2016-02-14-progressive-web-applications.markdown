---
layout: post
title:  "Progressive Web Applications"
date:   2016-02-14 11:53:00 -0800
tags: progressive web-application mobile user-experience
---

Everywhere you go, progressive seems to be all the rage. Progressive politicians, progressive relationships, and of course
progressive web applications. What are progressive web applications, and why should you care? 

<center>
    <img src="/assets/2016-02-14-progressive-web-applications/progressive-comic.jpg" style="border: 1px solid black; margin-bottom: 5px"/>
</center>

# What Are Progressive Web Applications?
Progressive web applications seem to have hit the mainstream in late 2015. They are applications that progressively morph
to provide you a more seamless experience as they become more and more important in your life. That is, they start
life as a simple webpage. On repeated visits, you may be prompted by your browser to "Add to Homescreen." Upon doing so, 
an application icon will be created on your homescreen. Tapping that will direct you straight back to the application.

So what's the difference versus going back to the website's URL? These types of applications have some nifty features. They:

- **look and feel like native applications.** A progressive web application can remove all of the browser chrome and be displayed
in landscape or portrait orientations.
- **are kept up-to-date and available offline.** Previously viewed content can be cached and displayed without connectivity. 
Updated content can be fetched and stored offline for later viewing.
- **can send notifications.** For example, a web application may tell you that an item you'e been watching has gone on sale or
that your friend has sent you a message asking to meet-up for coffee.

As of this writing, the only browsers that fully support progressive web applications are Chrome, Firefox, and Opera. 

# Benefits and Drawbacks of Progressive Web Applications
Progressive web applications are helpful for both the developer and the user. The user has a means to quickly evaluate
the utility of an application to them. No more searching, downloading, running, and uninstalling applications from the 
app stores. Evaluating an application is as easy as visiting a website. From the developer's perspective, applications 
can now just be written for the web and work across a variety of platforms. The barrier to entry is now much lower than
previously possible with cross-platform tools.
 
As the platform evolves, browsers will begin providing more tools to address cross cutting concerns. It's delightful to
envision consistent interfaces for monitoring, logging, and error reporting across all web applications. The browser
can be the steward for good application citizenship and warn you and the developer when applications start chewing
through battery life. That's good reason enough to abandon a power hungry native application like 
[Facebook](http://www.theguardian.com/technology/2016/feb/01/uninstalling-facebook-app-saves-up-to-20-of-android-battery-life)
and strictly use the web version.

Despite the numerous benefits, there are some downsides I'd like to highlight. Browsers are updated much more frequently
than your mobile operating systems and if the latest version introduces some bugs, your users may not be able to use
your application until a fix is rolled out. Native applications might also be the only way to utilize cutting-edge 
device features such as the fingerprint sensor.

# What Are Some Examples of Progressive Web Applications?
One of the best examples right now is Flipkart. Check out information about [Flipkart Lite](http://stories.flipkart.com/introducing-flipkart-lite/).
Facebook and eBay do as well.

# How Do I Make One?
Given that mobile is becoming [ever more dominant](http://www.smartinsights.com/mobile-marketing/mobile-marketing-analytics/mobile-marketing-statistics/),
it makes sense to jump on this progressive web application bandwagon now! The basic steps for making your website a progressive application are the following:

- create a [manifest file](https://www.w3.org/TR/appmanifest/) that contains metadata for your web application
- reference that manifest file in your HTML (i.e. `<link rel="manifest" href="path/to/manifest.json">`)
- start incorporating [service workers](https://www.w3.org/TR/service-workers/) and other features.

For more detailed instructions, check some of the links below.

# Further Reading
- [Progressive Web Apps (Google)](https://developers.google.com/web/progressive-web-apps?hl=en)
- [Progressive Web Apps: Escaping Tabs Without Losing Our Soul](https://infrequently.org/2015/06/progressive-apps-escaping-tabs-without-losing-our-soul/)

