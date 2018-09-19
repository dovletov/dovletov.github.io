---
layout: post
title:  "Add google analytics to your Jekyll website"
author: "Key Dee"
date:   2018-09-11 10:28:42 +0200
categories: jekyll
comments: true
---

Jekyll [Minima theme][minima-git] already contains analytics snippet in `_include/google-analytics.html` file:
{% highlight html %}
<script>
if(!(window.doNotTrack === "1" || navigator.doNotTrack === "1" || navigator.doNotTrack === "yes" || navigator.msDoNotTrack === "1")) {
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
  
  {% raw %}ga('create', '{{ site.google_analytics }}', 'auto'); {% endraw %}
  ga('send', 'pageview');
}
</script>
{% endhighlight %}
Thus, this file can be easily included into all pages of your website, such as done by default using `_include/head.html`.
<!--more-->

However, in order to start using analytica the `site.google_analytics`  variable in `_config.yml`  have to be defined.
This variable should contain your Tracking ID for your website, which you can get after creating an account at [Google Analytics][google-analytics].
{% highlight yaml %}
title: Your awesome title
...
google_analytics: UA-123456789-0
{% endhighlight %}

Of course, obtained Tracking ID can be explicitly added into the snippet itself:
{% highlight html %}
<script>
  ...
  ga('create', 'UA-123456789-0', 'auto');
  ...
</script>
{% endhighlight %}

Now you can see all of your traffic.

If you're experienced with [analytics.js][analytics], you can replace it with [gtag.js][gtag] snippet, which provides most flexibility with other Google products:
{% highlight html %}
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-123456789-0"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  {% raw %}gtag('config', '{{ site.google_analytics }}'); {% endraw %}
</script>
{% endhighlight %}



[minima-git]: https://github.com/jekyll/minima
[google-analytics]: https://analytics.google.com/
[analytics]: https://developers.google.com/analytics/devguides/collection/analyticsjs/
[gtag]: https://developers.google.com/analytics/devguides/collection/gtagjs/
