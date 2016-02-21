Vagrant file for a GitHub Pages-compatible Jekyll environment
====================

Simple Vagrant file to build a GitHub Pages-compatible Jekyll environment. Uses the "official" github-pages gem. Use this environment to build and test your GitHub Pages-based Jekyll sites without polluting your host box.

How to use
--------------------

First, make sure you've installed [Vagrant](http://docs.vagrantup.com/v2/getting-started/index.html) and [VirtualBox](https://www.virtualbox.org/).

Next, clone this repo:

```
git clone git@github.com:rjsilk/vagrant-github-pages.git
```

Now, `cd` into that directory and start up the Vagrant vm:

```
cd vagrant-github-pages
vagrant up
```

Finally, you can ssh into the vm and do all your Jekyll-related work in there:

```
vagrant ssh
```

Port forwarding
---------------------
The Vagrant vm is configured to forward port 8124 by default. So you can start a Jekyll server like so:

```
jekyll server --watch -P 8124 -H 0.0.0.0 --incremental
```

Note that you need to set host to 0.0.0.0 to access ```localhost:8124``` outside the VM. And then navigate to localhost:8124 on your host box.

Note on SSH-forwarding
---------------------
The Vagrantfile enables ssh-forwarding so that you can use your host ssh keys to authenticate with github. Make sure to add you keys to the agent with ```ssh-add``` before running ```vagrant ssh``` if your keys aren't automatically added to the agent.
