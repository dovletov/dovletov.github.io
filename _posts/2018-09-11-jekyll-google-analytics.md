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
