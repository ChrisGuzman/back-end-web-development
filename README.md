Course Materials for [Back-End Web Development](http://betamore.com/academy/back-end-web-development)

# Things to install

## Mac OS X Mavericks

On your Mac, click on the Apple icon in the top left (also called the Apple menu), and choose **About this Mac**. If the version is **10.9.0** or higher, you are running the latest version of OS X. If not, launch the Mac App Store (either from the icon in the doc or from the Apple menu), search for Mavericks and install. It is a free upgrade.

## Command-Line Tools

Launch the program called **Terminal**. At the command prompt, type the following command and press enter:

    xcode-select --install

You will see a dialog that says **Would you like to install the tools now?**. Press the install button and wait for the install to complete.

## iTerm 2

[http://www.iterm2.com](http://www.iterm2.com)

This program is a free alternative to Terminal that has some advantages. Install this and use it in place of Terminal. Make the following configuration changes:

Go to *iTerm > Preferences > Profiles > General*. Under **Working Directory**, choose **Advananced Configuration**. Press the edit button next to that. For **Working Directory for New Windows**, leave that as **Home directory**. For **Working Directory for New Tabs** and **Working Directory for New Split Panes**, choose **Reuse previous session's directory**.

Go to *iTerm > Preferences > Profiles > Terminal*. Under **Notifications**, check **Silence bell**.

## Homebrew

[Homebrew](http://brew.sh/) makes it easier to install command-line programs on a Mac. To install Homebrew, run this command from iTerm:

    ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"

## Sublime Text 3

[Sublime Text](http://www.sublimetext.com/3) is a text editor. It has lots of great features, works on Windows, Mac and Linux. It has an unlimited free trial, but does cost $70 to buy. You can use the trial indefinately, it will just occassionally bug you to go purchase it while you are using the free trial.

Once you have downloaded and installed Sublime Text, make it so that you can launch Sublime Text from command line. In iTerm, run these commands:

    cd /usr/local/bin
    ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl

For the last command, don't try to type it all out or copy and paste it. Type `/` then the first few letters of the path "App", then press tab. It will complete the rest of the word. Do this for each part of the path. Doing it this way will verify that these directories actually exist on your computer and you have typed it correctly.

## rbenv

[rbenv](https://github.com/sstephenson/rbenv), *arr-bee-env*, is a ruby installer similar to, but in my opinion [better than RVM](https://github.com/sstephenson/rbenv/wiki/Why-rbenv%3F), so you should use rbenv for this class. If you have RVM installed, unless you need it specifically for some other reason, I recommend [uninstalling it](http://rvm.io/support/faq#where-is-everything-installed-to-) with:

    rm -rf ~/.rvm

To use rbenv, replace the contents of your `~/.bash_profile` to look like this:

```bash
export EDITOR='subl -w'
export VISUAL='subl -w'

# my bin
PATH=~/bin

# rbenv
PATH+=:~/.rbenv/bin

# postgres
export PGHOME=/Applications/Postgres93.app/Contents/MacOS
PATH+=:$PGHOME/bin

# heroku
PATH+=:/usr/local/heroku/bin

# homebrew
PATH+=:/usr/local/bin

# unix
PATH+=:/usr/bin:/bin:/usr/sbin:/sbin:/usr/X11/bin

export PATH

# Load rbenv
if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi
```

Replace the entire contents of your `~/.bash_profile` with this. You can leave other things in your `~/.bash_profile` if you know what they do and you are sure you need them. If you are unsure, ask me.

Also make sure to start a new terminal tab or window once you have modified your `~/.bash_profile` so the settings take effect.

Now you can install `rbenv` by running these commands

    git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
    git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
    git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash

## Ruby 2.1

With rbenv properly installed, you just need to run this command to install Ruby 2.1:

    rbenv install 2.1.0

To make Ruby 2.1 be the default, run this command:

    rbenv global 2.1.0

Now, if you check which verison of ruby is being used, you should see something like this:

    $ which ruby
    /Users/paul/.rbenv/shims/ruby
    $ ruby -v
    ruby 2.1.0p0 (2013-12-25 revision 44422) [x86_64-darwin13.0]

## Postgres

Download and install [Postgres.app](http://postgresapp.com/). Make sure to run the application. Once you do, you will see an elephant icon in the menu bar in the top right, to the left of things like the wifi, the time, etc.

From that menu, uncheck *Open documentation at Start* and check *Automatically Start at Login*.

## Configure Rubygems

Before we start installing Rubygems, run the following command to use Sublime Text to create a file called `.gemrc` in your home directory:

    subl ~/.gemrc

Put the following one line into that file:

    gem: --no-rdoc --no-ri

This will prevent rdoc and ri from being created for each gem that is installed, which isn't needed and significantly slows down the process of installing gems.

## Rails

Now that we have everything in place, installing Rails is as simple as installing the gem, which you can do by running the following command:

    gem install rails

