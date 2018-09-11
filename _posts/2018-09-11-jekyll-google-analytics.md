---
layout: post
title:  "Google analytics for Jekyll"
date:   2018-09-11 10:28:42 +0200
categories: jekyll
comments: true
---

Jekyll [Minima theme][minima-git] already contains Google Analytics module (`_include/google-analytics.html`), which is inluded in `_include/head.html`:
{% highlight html %}
<script>
if(!(window.doNotTrack === "1" || navigator.doNotTrack === "1" || navigator.doNotTrack === "yes" || navigator.msDoNotTrack === "1")) {
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', '{{ site.google_analytics }}', 'auto');
  ga('send', 'pageview');
}
</script>
{% endhighlight %}

In order to start using analytics, we have to create an account at [Google Analytics][google-analytics] and get Tracking ID for our website.
For simplification, we add obtained Tracking ID in our `_config.yml` file:
{% highlight yaml %}
title: Your awesome title
...
google_analytics: UA-123456789-0
{% endhighlight %}

If you're experienced with [analytics.js][analytics], you can replace it with [gtag.js][gtag] snippet, which provides most flexibility with other Google products:
{% highlight html %}
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id={{ site.google_analytics }}"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', '{{ site.google_analytics }}');
</script>
{% endhighlight %}

[minima-git]: https://github.com/jekyll/minima
[google-analytics]: https://analytics.google.com/
[analytics]: https://developers.google.com/analytics/devguides/collection/analyticsjs/
[gtag]: https://developers.google.com/analytics/devguides/collection/gtagjs/
