---
layout: post
title:  "Jekyll Installation"
date:   2018-09-08 15:13:12 +0200
categories: jekyll
comments: true
---
So, this is my initial post. Looks like I am going to enjoy Jekyll (:

Before we install Jekyll, we need to make sure we have all the required dependencies.
{% highlight sh %}
sudo apt-get install ruby ruby-dev build-essential
{% endhighlight %}
<!--more-->
It is best to avoid installing Ruby Gems as the root user. Therefore, we need to set up a gem installation directory for your user account. The following commands will add environment variables to your ~/.bashrc file to configure the gem installation path. Run them now:
{% highlight sh %}
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME=$HOME/gems' >> ~/.bashrc
echo 'export PATH=$HOME/gems/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
{% endhighlight %}

Finally, install Jekyll:
{% highlight sh %}
gem install jekyll bundler
{% endhighlight %}

That’s it! You’re ready to start using Jekyll.
The instruction is copied from [Jekyll Documentation][jekyll-docs-installation].

[jekyll-docs-installation]: https://jekyllrb.com/docs/installation/ubuntu/
