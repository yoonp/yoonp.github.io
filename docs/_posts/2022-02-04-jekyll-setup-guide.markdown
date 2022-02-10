---
layout: post
title:  "How I setup a GitHub Pages site with Jekyll in Windows"
date:   2022-02-04 02:39:24 -0500
categories: jekyll update
---

Prerequities
Create a github repository using your Github username. For example, if your github id is johndoe, then create a repository in which the repository name is "johndoe.github.io". It should be public to be able to publish.

Download and install [Ruby][ruby]. I downloaded "rubyinstaller-devkit-2.7.5-1-x64" as it's the latest amongst the recommended version. As of February 4th 2022, the latest available version failed the installation of jekyll.

Check all checkboxes and proceed during the installation wizard.

After the installation is complete, the Ruby Installer command prompt automatically opens and asks to run one of the three options. Run 1, 2, 3 consecutively.

Open "Start Command Prompt with Ruby" and confirm Ruby and Bundler are installed by running the following commands. You are good to move on as long as you see the versions of the both.

{% highlight powershell %}
C:\>ruby -v
ruby 2.7.5p203 (2021-11-24 revision f69aeb8314) [x64-mingw32]
    
C:\>bundler -v
Bundler version 2.3.6
{% endhighlight %}


Execute the following :

>gem install jekyll bundler


 can check whether jekyll is installed properly

{% highlight powershell %}
C:\>bundler -v
Bundler version 2.3.6

C:\>jekyll -v
jekyll 4.2.1
{% endhighlight %}

Open git bash or command promot and go to the folder you want to locate your Github page site files

Clone your github repository from prerequisite

Go into the repository folder. Optionally you can create a folder to publish your GitHub page

Go to the folder you want to create site files and execute the following :
{% highlight powershell %}
C:\>jekyll new --skip-bundle
{% endhighlight %}

Open Gemfile and modify as following. Version '223' chosen from https://pages.github.com/versions/.

{% highlight ruby %}
#gem "jekyll", "~> 4.2.1" <-- Comment this line
gem "github-pages", "~> 223", group: :jekyll_plugins
#Uncomment the line above and configure the version number (223 from the example).
{% endhighlight %}

run 'bundle install' from the command line.

Push the changes to the remote git repository. It will take a few minutes to publish to the web.

From GitHub repository, go to Settinngs -> Pages. If everything is successful, there will be a messsage "Your site is published at <YOUR GITHUB PAGE URL>".


[ruby]: https://rubyinstaller.org/downloads/
