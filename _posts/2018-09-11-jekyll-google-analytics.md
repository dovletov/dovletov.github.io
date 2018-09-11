---
layout: post
title:  "Google analytics for Jekyll"
date:   2018-09-11 10:28:42 +0200
categories: jekyll
comments: true
---

Jekyll [Minima theme][minima-git] already contains Google Analytics module, which is inluded in the header file.

In order to start using analytics, we have to create an account at [Google Analytics][google-analytics] and get Tracking ID for our website.
For simplification, we add obtained Tracking ID in our `_config.yml` file:
{% highlight ruby %}
title: Your awesome title
...
google_analytics: UA-123456789-0
{% endhighlight %}

[minima-git]: https://github.com/jekyll/minima
[google-analytics]: https://analytics.google.com/
