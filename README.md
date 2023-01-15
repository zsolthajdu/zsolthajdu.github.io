# zsolthajdu.github.io
Simple static webpage available at https://zsolthajdu.github.io .

## Requirements
To install Jekyll and dependencies on a Ubuntu system

{% highlight bash %}
sudo apt install ruby-full build-essential zlib1g-dev
{% endhighlight %}

Set up a gem installation directory for your user account. The following commands will add environment variables to your ~/.bashrc file to configure the gem installation path:

{% highlight bash %}
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
{% endhighlight %}

