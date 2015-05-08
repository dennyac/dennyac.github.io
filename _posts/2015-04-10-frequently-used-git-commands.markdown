---
layout:     post
title:      "Frequently used Git commands"
subtitle:   "Commands that I find handy when working with Git"
date:       2015-04-10 12:00:00
author:     "Denny Abraham Cheriyan"
header-img: "img/post-bg-01.jpg"
---

With my experience using Git so far, which is quite minimal, I have found the following commands to be extremely handy. I’ll keep updating this post from time to time, if I do come across other useful commands. Please note that some of these commands are not recommended as they might re-write history which may not be preferable. Also since I'm relatively new to git, some of these practices may not be advised. I would love to hear feedback regarding this post and about best practices to be followed.


In situations where your local repository is out of sync and you want to get it sync it with the central repository -
{% highlight bash %}
git reset --hard HEAD
git clean -f
git pull
{% endhighlight %}


To remove the most recent commit - 
{% highlight bash %}
git reset --hard HEAD^
{% endhighlight %}


The "Branch-Edit-Commit-Merge" workflow - 
{% highlight bash %}
git checkout -b branch-name
# Make changes
git commit -a -m "Change made"
git checkout master
git merge branch-name
{% endhighlight %}


To combine the last n commits into a single commit -
{% highlight bash %}
git reset --soft HEAD~2 &&
git commit
{% endhighlight %}


Forcefully push to a repository -
{% highlight bash %}
git push heroku master --force
{% endhighlight %}


Rebasing - 
{% highlight bash %}
git checkout new-feature
git rebase master
git checkout master
git merge new-feature
{% endhighlight %}


To undo the local changes made to a repository- 
{% highlight bash %}
git checkout -- .
# If you want to save the changes for later use
git stash save --keep-index
git stash drop
{% endhighlight %}


To clone a specific branch from github - 
{% highlight bash %}
git clone -b <branch> <remote_repo>
{% endhighlight %}