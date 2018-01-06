---
layout: post
title: RUBY and RAILS INSTALLATION
subtitle: WEB DEVELOPMENT!
bigimg: /img/rails.png

---

**Installation of Ruby usin rbenv**
> open ur terminal on ur linux machine
First, we should update apt-get since this is the first time we will be using apt in this session. This will ensure that the local package cache is updated

```
sudo apt-get update

```
Next, let’s install the dependencies required for rbenv and Ruby with apt-get:
```
sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev
```

Once we have all of the required system dependencies installed, we can move onto the installation of rbenv itself.

**Install rbenv**
Now we are ready to install rbenv. Let's clone the rbenv repository from git. You should complete these steps from the user account from which you plan to run Ruby.
```
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
```
From here, you should add ~/.rbenv/bin to your $PATH so that you can use rbenv's command line utility. Also adding ~/.rbenv/bin/rbenv init to your ~/.bash_profile will let you load rbenv automatically.
```
    echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(rbenv init -)"' >> ~/.bashrc
```
Next, source rbenv by typing:
```
 source ~/.bashrc
 ```
 
 You can check to see if rbenv was set up properly by using the type command, which will display more information about rbenv:
 ```
 type rbenv
 ```
 Your terminal window should output the following:
 ```
 Output
rbenv is a function
rbenv () 
{ 
    local command;
    command="$1";
    if [ "$#" -gt 0 ]; then
        shift;
    fi;
    case "$command" in 
        rehash | shell)
            eval "$(rbenv "sh-$command" "$@")"
        ;;
        *)
            command rbenv "$command" "$@"
        ;;
    esac
}
```
In order to use the rbenv install command, which simplifies the installation process for new versions of Ruby, you should install ruby-build, which we will install as a plugin for rbenv through git:

```
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

**Install Ruby**
With the ruby-build rbenv plugin now installed, we can install whatever versions of Ruby that we may need through a simple command. First, let's list all the available versions of Ruby:
```
rbenv install -l
```
We'll now install a particular version of Ruby. It's important to keep in mind that installing Ruby can be a lengthy process, so be prepared for the installation to take some time to complete.

As an example here, let's install Ruby version 2.3.1, and once it's done installing, we can set it as our default version with the global sub-command:
```
rbenv install 2.3.1 //dependent of the latest version
```
```
rbenv global 2.3.1 //dependent of the latest version
```
To configure the rbenv ruby version with default ruby version 
```
rbenv rehash
```
Verify that Ruby was properly installed by checking your version number:
```
ruby -v 
```
It will show 
```
ruby 2.3.1p112 (2016-04-26 revision 54768) [x86_64-linux]
```

There are many ways to install rails like **Rvm and Rbnv**. But the simplest way and the coolest way to install the stable version of ruby and rails please follow the below steps.
> open ur terminal on ur linux machine
> Copy paste the code to install ruby on linux machine
```
sudo apt-get install build-essential patch ruby-dev zlib1g-dev liblzma-dev libsqlite3-dev
```
> check the ruby version by typing
```
ruby -v
```
> To install rails 
 ```
 sudo gem install rails –v 5.0.0.1 \\dependent upon the rails version
 ```
